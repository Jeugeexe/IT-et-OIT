# Cybersecurity IT/OT — Infrastructure, Security & Industrial Systems

\<p align="center">
&#x20; \<strong>Parcours personnel de formation en administration systèmes, réseaux et cybersécurité industrielle\</strong>
\</p>

\<p align="center">
&#x20; \<img src="[https://img.shields.io/badge/Domain-IT%20%2F%20OT-blue](https://img.shields.io/badge/Domain-IT%20%2F%20OT-blue)" />
&#x20; \<img src="[https://img.shields.io/badge/Focus-Cybersecurity-red](https://img.shields.io/badge/Focus-Cybersecurity-red)" />
&#x20; \<img src="[https://img.shields.io/badge/Linux-Debian-orange](https://img.shields.io/badge/Linux-Debian-orange)" />
&#x20; \<img src="[https://img.shields.io/badge/Status-In%20Progress-yellow](https://img.shields.io/badge/Status-In%20Progress-yellow)" />
\</p>

---

## Présentation du projet

Ce dépôt GitHub regroupe un parcours personnel d'apprentissage et de mise en pratique consacré à l'administration des systèmes et réseaux, à la cybersécurité et à la sécurité des environnements industriels IT/OT.

L'objectif est de développer progressivement des compétences techniques à travers la réalisation de laboratoires pratiques, la configuration d'infrastructures virtualisées, l'analyse de vulnérabilités, la mise en place de mécanismes de sécurité et l'application de référentiels professionnels.

Ce projet s'inscrit dans une démarche d'approfondissement des connaissances acquises durant mon parcours en informatique et dans la préparation de ma spécialisation en cybersécurité industrielle.

**Objectif professionnel :** évoluer vers les métiers de la cybersécurité, avec une spécialisation dans la sécurisation des infrastructures industrielles et des systèmes IT/OT.

## Objectifs techniques

Ce parcours vise à développer les compétences suivantes :

- Administration de systèmes Linux et Windows.
- Administration des services réseau et des infrastructures.
- Gestion des identités et des accès.
- Conception et sécurisation des architectures réseau.
- Segmentation réseau et filtrage des communications.
- Déploiement de solutions de supervision et de centralisation des journaux.
- Détection, analyse et réponse aux incidents de sécurité.
- Compréhension des techniques d'attaque et des mécanismes de défense.
- Connaissance des normes et référentiels de cybersécurité.
- Analyse et sécurisation des architectures industrielles.
- Compréhension des protocoles et systèmes industriels.
- Application des principes de sécurité dans les environnements IT/OT.

---

## Architecture du parcours

Le programme est organisé en **8 niveaux progressifs**, comprenant 30 laboratoires principaux, 9 laboratoires complémentaires et 7 modules consacrés aux normes et à la conformité.

| Niveau | Domaine                          | Objectif                                        |
| ------ | -------------------------------- | ----------------------------------------------- |
| 01     | Fondations informatiques         | Virtualisation, Linux et réseaux                |
| 02     | Services et infrastructures      | Déploiement des services informatiques          |
| 03     | Environnement d'entreprise       | Active Directory, identités et PKI              |
| 04     | Réseaux et sécurité              | Pare-feu, VLAN, VPN et IDS/IPS                  |
| 05     | SOC et détection                 | Supervision, SIEM et réponse à incident         |
| 06     | Offensive et défensive           | Tests de sécurité et mécanismes de défense      |
| 07     | Gouvernance et conformité        | ISO, IEC, NIST et réglementation                |
| 08     | Cybersécurité industrielle IT/OT | Automates, SCADA et architectures industrielles |

---

# Niveau 01 — Fondations informatiques

**Objectif :** acquérir les bases nécessaires à la construction et à l'administration d'une infrastructure informatique.

| Lab     | Sujet                            | Technologies et compétences                       |
| ------- | -------------------------------- | ------------------------------------------------- |
| LAB 01  | Infrastructure de virtualisation | VirtualBox, machines virtuelles, réseaux virtuels |
| LAB 02  | Serveur Linux                    | Debian, utilisateurs, groupes et services         |
| LAB 03  | Sécurisation Linux               | SSH, permissions, sudo, pare-feu                  |
| LAB 04  | Réseaux TCP/IP                   | IPv4, masques, routage et passerelles             |
| LAB 04B | Dépannage réseau                 | Diagnostic et résolution de pannes                |

**Compétences visées :**

- Installer et administrer une machine Linux.
- Comprendre le fonctionnement d'un réseau IP.
- Configurer des interfaces réseau.
- Diagnostiquer des problèmes de connectivité.
- Comprendre les bases de la virtualisation.

# Niveau 02 — Services et infrastructures

**Objectif :** déployer et administrer les services fondamentaux d'une infrastructure informatique.

| Lab     | Sujet               | Technologies et compétences             |
| ------- | ------------------- | --------------------------------------- |
| LAB 05  | DNS                 | BIND9, zones directes et inverses       |
| LAB 06  | DHCP                | Attribution automatique des adresses IP |
| LAB 07  | Serveur Web         | Apache, Nginx, HTTP et HTTPS            |
| LAB 08  | Partage de fichiers | Samba et permissions                    |
| LAB 09  | Sauvegardes         | Automatisation et restauration          |
| LAB 09B | Disaster Recovery   | PRA, PCA, RTO et RPO                    |

**Compétences visées :**

- Déployer les services réseau essentiels.
- Administrer les services Linux.
- Configurer les mécanismes de résolution de noms.
- Gérer les partages et les permissions.
- Mettre en place une stratégie de sauvegarde.
- Organiser la reprise après incident.

# Niveau 03 — Environnement d'entreprise

**Objectif :** comprendre et administrer une infrastructure centralisée d'entreprise.

| Lab     | Sujet                   | Technologies et compétences                    |
| ------- | ----------------------- | ---------------------------------------------- |
| LAB 10  | Active Directory        | Domaine, contrôleur de domaine et utilisateurs |
| LAB 11  | Group Policy Objects    | GPO et stratégies de groupe                    |
| LAB 12  | Active Directory avancé | OU, délégation et administration               |
| LAB 12B | Identités et privilèges | Gestion des comptes, moindre privilège         |
| LAB 13  | PKI                     | Autorité de certification et certificats       |

**Compétences visées :**

- Déployer un domaine Active Directory.
- Administrer les comptes et groupes.
- Gérer les stratégies de sécurité.
- Appliquer le principe du moindre privilège.
- Comprendre le fonctionnement d'une infrastructure à clés publiques.

# Niveau 04 — Réseaux et sécurité

**Objectif :** concevoir une architecture réseau sécurisée et maîtriser les mécanismes de protection des communications.

| Lab     | Sujet               | Technologies et compétences          |
| ------- | ------------------- | ------------------------------------ |
| LAB 14  | Pare-feu            | nftables, NAT et filtrage            |
| LAB 15  | VLAN                | 802.1Q et segmentation logique       |
| LAB 16  | Segmentation réseau | DMZ et zones de confiance            |
| LAB 16B | Matrice des flux    | Identification et contrôle des flux  |
| LAB 17  | VPN                 | WireGuard et accès distant sécurisé  |
| LAB 18  | IDS/IPS             | Suricata et détection des intrusions |

**Compétences visées :**

- Configurer un pare-feu.
- Contrôler les communications réseau.
- Concevoir une segmentation adaptée.
- Sécuriser les connexions distantes.
- Détecter les activités réseau suspectes.

# Niveau 05 — SOC, supervision et détection

**Objectif :** surveiller les infrastructures, détecter les incidents et réaliser des investigations techniques.

| Lab     | Sujet                       | Technologies et compétences    |
| ------- | --------------------------- | ------------------------------ |
| LAB 19  | Collecte Windows            | Sysmon et événements système   |
| LAB 20  | Centralisation des journaux | Graylog et collecte des logs   |
| LAB 21  | Détection                   | Règles, alertes et corrélation |
| LAB 22  | Réponse à incident          | Investigation et confinement   |
| LAB 22B | Threat Hunting              | Recherche proactive de menaces |

**Compétences visées :**

- Collecter et analyser des journaux.
- Centraliser les événements de sécurité.
- Identifier des comportements suspects.
- Construire des règles de détection.
- Réaliser une première investigation.
- Documenter les incidents de sécurité.

# Niveau 06 — Sécurité offensive et défensive

**Objectif :** comprendre les techniques d'attaque afin de mieux identifier les vulnérabilités et renforcer les mécanismes de défense.

| Lab    | Sujet                               | Technologies et compétences            |
| ------ | ----------------------------------- | -------------------------------------- |
| LAB 23 | Environnement de test               | Kali Linux et laboratoire isolé        |
| LAB 24 | Sécurité Web                        | OWASP et vulnérabilités applicatives   |
| LAB 25 | Attaque et défense Active Directory | Analyse des attaques AD et remédiation |

**Compétences visées :**

- Comprendre les phases d'un test d'intrusion.
- Identifier les vulnérabilités.
- Comprendre les risques liés aux identités.
- Analyser les traces d'une attaque.
- Mettre en place des contre-mesures.

Les exercices offensifs sont exclusivement réalisés dans des environnements de laboratoire isolés et autorisés.

# Niveau 07 — Gouvernance, normes et conformité

**Objectif :** comprendre les référentiels de cybersécurité utilisés dans les organisations et les environnements industriels.

| Module | Référentiel                  | Compétences                                         |
| ------ | ---------------------------- | --------------------------------------------------- |
| S01    | ISO 27001                    | SMSI, analyse des risques et amélioration continue  |
| S02    | ISO 27002                    | Mesures et bonnes pratiques de sécurité             |
| S03    | IEC 62443                    | Sécurité des systèmes d'automatisation industrielle |
| S04    | NIST Cybersecurity Framework | Gouvernance, protection et réponse                  |
| S05    | NIST SP 800-82               | Sécurité des systèmes de contrôle industriels       |
| S06    | Réglementation               | NIS2, Cyber Resilience Act, RGPD et ANSSI           |
| S07    | Audit de cybersécurité       | Évaluation, preuves, écarts et remédiation          |

**Compétences visées :**

- Comprendre la gouvernance de la cybersécurité.
- Réaliser une analyse des risques.
- Identifier les mesures de sécurité pertinentes.
- Comprendre les exigences de sécurité industrielle.
- Étudier l'applicabilité des réglementations.
- Produire un rapport d'audit.

Les référentiels et réglementations seront étudiés en tenant compte de leurs versions et de leur champ d'application.

# Niveau 08 — Cybersécurité industrielle IT/OT

**Objectif :** comprendre les architectures industrielles et apprendre à protéger les systèmes de contrôle et d'automatisation.

| Lab     | Sujet                                | Technologies et compétences                      |
| ------- | ------------------------------------ | ------------------------------------------------ |
| LAB 26  | Architecture industrielle            | IT/OT et modèle Purdue                           |
| LAB 26B | Inventaire des actifs OT             | Identification et classification des équipements |
| LAB 27  | Automate programmable                | PLC et simulation industrielle                   |
| LAB 28  | Protocoles industriels               | Modbus/TCP et analyse des communications         |
| LAB 28B | Analyse passive OT                   | Wireshark et observation du trafic               |
| LAB 29  | Supervision industrielle             | SCADA et HMI                                     |
| LAB 29B | Sécurité des postes d'ingénierie     | Durcissement et contrôle des accès               |
| LAB 30  | Projet d'infrastructure industrielle | Conception et sécurisation IT/OT                 |
| LAB 30B | Audit final IT/OT                    | Analyse des risques et recommandations           |

**Compétences visées :**

- Comprendre les différences entre IT et OT.
- Étudier une architecture industrielle.
- Identifier les actifs et les communications industrielles.
- Comprendre les automates et les systèmes SCADA.
- Analyser les protocoles industriels.
- Appliquer les principes de segmentation.
- Identifier les risques propres aux environnements industriels.
- Proposer des mesures de sécurité adaptées.

---

## Projet final — Infrastructure industrielle IT/OT

Le projet final consiste à concevoir et sécuriser une infrastructure industrielle fictive.

L'environnement devra reproduire une architecture comprenant plusieurs zones fonctionnelles :

- Réseau informatique IT.
- Réseau industriel OT.
- DMZ industrielle.
- Serveurs Linux et Windows.
- Active Directory.
- Pare-feu et segmentation réseau.
- Automate programmable virtuel.
- Système de supervision SCADA/HMI.
- Supervision et centralisation des journaux.
- Mécanismes de détection et de réponse aux incidents.

### Livrables attendus

1. Schéma d'architecture réseau.
2. Plan d'adressage IP et VLAN.
3. Matrice des flux réseau.
4. Documentation des serveurs et services.
5. Configuration des mécanismes de sécurité.
6. Inventaire des actifs industriels.
7. Analyse des risques.
8. Étude de sécurité inspirée d'IEC 62443.
9. Rapport d'audit.
10. Plan de remédiation et recommandations.

Le projet devra démontrer la capacité à concevoir, administrer, sécuriser et documenter une infrastructure IT/OT.

---

## Environnement technique

Les technologies seront choisies progressivement en fonction des objectifs de chaque laboratoire.

| Domaine                     | Technologies envisagées       |
| --------------------------- | ----------------------------- |
| Virtualisation              | VirtualBox                    |
| Systèmes Linux              | Debian                        |
| Systèmes Windows            | Windows 10/11, Windows Server |
| Réseau                      | TCP/IP, VLAN, routage         |
| DNS                         | BIND9                         |
| DHCP                        | ISC DHCP ou Kea               |
| Services Web                | Apache, Nginx                 |
| Partage                     | Samba                         |
| Annuaire                    | Active Directory              |
| Pare-feu                    | nftables                      |
| VPN                         | WireGuard                     |
| IDS/IPS                     | Suricata                      |
| Supervision                 | Graylog, outils de monitoring |
| Analyse réseau              | Wireshark                     |
| Tests de sécurité           | Kali Linux                    |
| Protocoles industriels      | Modbus/TCP                    |
| Automatisation industrielle | PLC et simulateurs            |
| Supervision industrielle    | SCADA/HMI                     |

Les outils pourront évoluer selon les besoins des laboratoires.

---

## Méthodologie de travail

Chaque laboratoire suit une méthodologie inspirée des pratiques professionnelles.

1. **Contexte :** présentation d'une situation professionnelle.
2. **Objectifs :** identification des compétences à acquérir.
3. **Architecture :** préparation de l'environnement technique.
4. **Missions :** réalisation des tâches demandées.
5. **Investigation :** recherche autonome et résolution des problèmes.
6. **Validation :** vérification du fonctionnement.
7. **Documentation :** rédaction des procédures et résultats.
8. **Bilan :** analyse des difficultés et des solutions retenues.

Les solutions ne sont pas fournies directement au démarrage des exercices. La priorité est donnée à la recherche, au raisonnement technique et à l'autonomie.

### Grille d'évaluation

| Critère                 |  Points |
| ----------------------- | ------: |
| Compréhension technique |      /5 |
| Autonomie               |      /5 |
| Diagnostic et dépannage |      /5 |
| Sécurité                |      /5 |
| **Total**               | **/20** |

---

## Documentation des laboratoires

Chaque laboratoire disposera de son propre dossier contenant :

- `README.md` : présentation et objectifs.
- `architecture/` : schémas et plans réseau.
- `configuration/` : fichiers de configuration utiles.
- `screenshots/` : captures d'écran des réalisations.
- `tests/` : procédures et résultats de validation.
- `rapport.md` : bilan technique et difficultés rencontrées.

Les mots de passe, clés privées, certificats privés et informations sensibles ne doivent jamais être publiés dans ce dépôt.

---

## Organisation du dépôt

```text
Cybersecurity-IT-OT/
│
├── README.md
│
├── Level-01-Foundations/
│   ├── LAB-01-Virtualization/
│   ├── LAB-02-Linux/
│   ├── LAB-03-Linux-Security/
│   ├── LAB-04-Networking/
│   └── LAB-04B-Troubleshooting/
│
├── Level-02-Infrastructure/
│   ├── LAB-05-DNS/
│   ├── LAB-06-DHCP/
│   ├── LAB-07-Web-Server/
│   ├── LAB-08-Samba/
│   ├── LAB-09-Backup/
│   └── LAB-09B-Disaster-Recovery/
│
├── Level-03-Enterprise/
│   ├── LAB-10-Active-Directory/
│   ├── LAB-11-GPO/
│   ├── LAB-12-Advanced-AD/
│   ├── LAB-12B-Identity-Management/
│   └── LAB-13-PKI/
│
├── Level-04-Network-Security/
│   ├── LAB-14-Firewall/
│   ├── LAB-15-VLAN/
│   ├── LAB-16-Segmentation/
│   ├── LAB-16B-Flow-Matrix/
│   ├── LAB-17-VPN/
│   └── LAB-18-IDS-IPS/
│
├── Level-05-SOC-Detection/
│   ├── LAB-19-Sysmon/
│   ├── LAB-20-Log-Centralization/
│   ├── LAB-21-Detection/
│   ├── LAB-22-Incident-Response/
│   └── LAB-22B-Threat-Hunting/
│
├── Level-06-Offensive-Defensive/
│   ├── LAB-23-Kali-Linux/
│   ├── LAB-24-Web-Security/
│   └── LAB-25-Active-Directory-Security/
│
├── Level-07-Governance-Standards/
│   ├── S01-ISO-27001/
│   ├── S02-ISO-27002/
│   ├── S03-IEC-62443/
│   ├── S04-NIST-CSF/
│   ├── S05-NIST-800-82/
│   ├── S06-Regulations/
│   └── S07-Cybersecurity-Audit/
│
├── Level-08-Industrial-OT/
│   ├── LAB-26-Industrial-Architecture/
│   ├── LAB-26B-OT-Asset-Inventory/
│   ├── LAB-27-PLC/
│   ├── LAB-28-Modbus/
│   ├── LAB-28B-OT-Traffic-Analysis/
│   ├── LAB-29-SCADA-HMI/
│   ├── LAB-29B-Engineering-Workstation/
│   ├── LAB-30-Industrial-Infrastructure/
│   └── LAB-30B-OT-Security-Audit/
│
└── Final-Project-IT-OT/
    ├── architecture/
    ├── network/
    ├── infrastructure/
    ├── security/
    ├── audit/
    └── documentation/
```

---

## Progression

Le parcours est réalisé progressivement. Chaque niveau doit être validé avant de passer au suivant.

| Niveau                             | Statut      |
| ---------------------------------- | ----------- |
| Niveau 01 — Fondations             | En cours    |
| Niveau 02 — Infrastructures        | À commencer |
| Niveau 03 — Entreprise             | À commencer |
| Niveau 04 — Réseaux et sécurité    | À commencer |
| Niveau 05 — SOC                    | À commencer |
| Niveau 06 — Offensive et défensive | À commencer |
| Niveau 07 — Normes et conformité   | À commencer |
| Niveau 08 — IT/OT industriel       | À commencer |
| Projet final                       | À commencer |

---

## Objectif professionnel

Ce projet personnel accompagne mon évolution vers la cybersécurité des systèmes d'information et des systèmes industriels.

Il vise à approfondir les compétences acquises en administration systèmes et réseaux, à développer une approche méthodique de la sécurité et à acquérir des connaissances spécifiques aux environnements industriels.

Il constitue également un support de démonstration de mon travail personnel, de mon autonomie et de ma progression technique dans le cadre de la poursuite de mes études en cybersécurité.

**L'objectif final est de disposer d'un portfolio technique documenté, fondé sur des réalisations pratiques et des méthodes proches des environnements professionnels.**

---

