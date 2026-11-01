# LAB 01 — Configuration d'un routeur Linux avec NAT

## 🎯 Objectif du laboratoire

L'objectif de ce laboratoire est de mettre en place un environnement réseau permettant à une machine située sur un réseau LAN privé d'accéder à Internet via un routeur Linux.

À la fin du LAB, la configuration doit rester fonctionnelle après un redémarrage.

---

# 🏗️ Architecture réseau

```text
                    INTERNET
                       │
                       │
                 10.0.2.2
                       │
                 ┌───────────┐
                 │ ROUTER-01 │
                 │           │
WAN enp0s3 ──────│ 10.0.2.15 │
                 │           │
LAN enp0s8 ──────│192.168.10.1│
                 └───────────┘
                       │
              192.168.10.0/24
                       │
                 ┌──────────────┐
                 │ SRV-LINUX-01 │
                 │ 192.168.10.2 │
                 └──────────────┘
```

---

# 🖥️ Machines utilisées

## ROUTER-01

| Élément | Configuration |
|---|---|
| Rôle | Routeur Linux |
| Interface WAN | `enp0s3` |
| Adresse WAN | `10.0.2.15/24` |
| Passerelle WAN | `10.0.2.2` |
| Interface LAN | `enp0s8` |
| Adresse LAN | `192.168.10.1/24` |

## SRV-LINUX-01

| Élément | Configuration |
|---|---|
| Rôle | Serveur Linux |
| Interface réseau | `enp0s3` |
| Adresse IP | `192.168.10.2/24` |
| Passerelle | `192.168.10.1` |
| DNS | `1.1.1.1` |

---

# 1. Vérification du routage IPv4

Le routeur possède :

- une interface WAN connectée au réseau extérieur ;
- une interface LAN connectée au réseau `192.168.10.0/24` ;
- une route par défaut vers la passerelle WAN.

Le transfert IPv4 doit être activé pour permettre au routeur de transmettre les paquets entre ses interfaces.

---

# 2. Activation du routage IPv4

Paramètre utilisé :

```text
net.ipv4.ip_forward
```

Activation temporaire :

```bash
sysctl -w net.ipv4.ip_forward=1
```

Vérification :

```bash
cat /proc/sys/net/ipv4/ip_forward
```

La valeur attendue est :

```text
1
```

---

# 3. Configuration du NAT avec nftables

Le réseau LAN utilise des adresses privées :

```text
192.168.10.0/24
```

Pour permettre aux machines du LAN d'accéder à Internet, une règle NAT de type `masquerade` est utilisée.

La règle se trouve dans une table :

```text
table ip nat
```

avec une chaîne :

```text
chain postrouting
```

La règle NAT utilisée est :

```nft
ip saddr 192.168.10.0/24 oifname "enp0s3" masquerade
```

### Fonctionnement

- `ip saddr 192.168.10.0/24` : trafic provenant du LAN ;
- `oifname "enp0s3"` : trafic sortant par l'interface WAN ;
- `masquerade` : traduction de l'adresse IP privée source en adresse IP du routeur.

---

# 4. Configuration persistante de nftables

Le fichier de configuration utilisé est :

```text
/etc/nftables.conf
```

La configuration finale contient :

```nft
#!/usr/sbin/nft -f

flush ruleset

table inet filter {
    chain input {
        type filter hook input priority filter;
        policy accept;
    }

    chain forward {
        type filter hook forward priority filter;
        policy accept;
    }

    chain output {
        type filter hook output priority filter;
        policy accept;
    }
}

table ip nat {
    chain postrouting {
        type nat hook postrouting priority srcnat; policy accept;
        ip saddr 192.168.10.0/24 oifname "enp0s3" masquerade
    }
}
```

---

## Vérification de la syntaxe

Avant le chargement :

```bash
nft -c -f /etc/nftables.conf
```

Puis chargement :

```bash
nft -f /etc/nftables.conf
```

Vérification :

```bash
nft list ruleset
```

---

# 5. Persistance du routage IPv4

Après un premier redémarrage, un problème a été identifié : le NAT était chargé, mais `ip_forward` était revenu à `0`.

La solution a été de créer le fichier :

```text
/etc/sysctl.d/99-router.conf
```

avec :

```text
net.ipv4.ip_forward = 1
```

Application :

```bash
sysctl --system
```

---

# 6. Validation finale après redémarrage

Le routeur a ensuite été redémarré afin de vérifier la persistance complète de la configuration.

Les éléments suivants ont été validés :

- `ip_forward` activé ;
- règles `nftables` restaurées ;
- règle NAT `masquerade` présente ;
- service `nftables` actif ;
- service `nftables` activé au démarrage ;
- accès Internet depuis `SRV-LINUX-01` ;
- résolution DNS fonctionnelle.

---

# 📸 Preuve 1 — IP Forwarding après redémarrage

Commande exécutée :

```bash
cat /proc/sys/net/ipv4/ip_forward
```

Résultat :

```text
1
```

Cela confirme que le transfert IPv4 est bien **persistant après le redémarrage**.

![Preuve IP Forwarding](sandbox:/mnt/data/image(20261031-130251).png)

---

# 📸 Preuve 2 — Règles nftables restaurées

Commande exécutée :

```bash
sudo nft list ruleset
```

La sortie montre notamment :

- `table inet filter` ;
- `table ip nat` ;
- `chain postrouting` ;
- la règle NAT pour `192.168.10.0/24` ;
- la sortie par `enp0s3` ;
- l'action `masquerade`.

![Preuve règles nftables](sandbox:/mnt/data/image(20261031-130331).png)

---

# 📸 Preuve 3 — Service nftables actif et persistant

Commande exécutée :

```bash
systemctl status nftables
```

Résultat observé :

```text
Active: active
enabled
```

Le service charge automatiquement :

```text
/etc/nftables.conf
```

au démarrage du système.

![Preuve service nftables](sandbox:/mnt/data/image(20261031-130355).png)

---

# 📸 Preuve 4 — Accès Internet depuis SRV-LINUX-01

Depuis `SRV-LINUX-01`, le test suivant a été effectué :

```bash
ping -c 4 8.8.8.8
```

Les quatre requêtes ont reçu une réponse.

Cela confirme que :

```text
SRV-LINUX-01
        ↓
ROUTER-01
        ↓
NAT / MASQUERADE
        ↓
Internet
```

fonctionne correctement.

![Preuve accès Internet](sandbox:/mnt/data/image(20261031-130411).png)

---

# 📸 Preuve 5 — Résolution DNS

Commande exécutée sur `SRV-LINUX-01` :

```bash
getent ahosts google.fr
```

Des adresses IPv4 et IPv6 ont été retournées.

Cela confirme que la résolution DNS fonctionne correctement.

![Preuve DNS](sandbox:/mnt/data/image(20261031-130455).png)

---

# 🧪 Résumé des tests finaux

| Test | Résultat |
|---|---|
| Ping vers `192.168.10.1` | ✅ |
| Routage IPv4 | ✅ |
| `ip_forward` après reboot | ✅ |
| NAT / Masquerade | ✅ |
| nftables chargé | ✅ |
| nftables au démarrage | ✅ |
| Ping vers Internet | ✅ |
| Résolution DNS | ✅ |

---

# 🏆 Compétences acquises

Au cours de ce laboratoire, les compétences suivantes ont été mises en pratique :

- Analyse des interfaces réseau Linux ;
- Lecture des tables de routage ;
- Configuration d'une passerelle ;
- Diagnostic réseau avec `ip`, `ping` et `getent` ;
- Compréhension du routage IPv4 ;
- Activation de `ip_forward` ;
- Utilisation de `nftables` ;
- Configuration du NAT ;
- Utilisation de `masquerade` ;
- Persistance des règles firewall ;
- Persistance des paramètres kernel avec `sysctl` ;
- Tests de connectivité LAN → Internet ;
- Configuration et diagnostic DNS ;
- Validation d'une infrastructure après redémarrage.

---

# ✅ Conclusion

Le LAB 01 est entièrement fonctionnel.

L'infrastructure finale permet à `SRV-LINUX-01`, situé sur le réseau privé :

```text
192.168.10.0/24
```

d'accéder à Internet via `ROUTER-01`.

La configuration est persistante après redémarrage :

```text
✅ nftables
✅ NAT
✅ masquerade
✅ ip_forward
✅ accès Internet
✅ DNS
```

# 🏁 LAB 01 — TERMINÉ
