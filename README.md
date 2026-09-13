# 🍺 OpenPayKit

**Open-source ordering, point-of-sale and payment platform for bars.**

OpenPayKit is an open-source project designed to help bars manage customer orders, receipts and payments through a simple, customizable and extensible system.

The goal is simple: **provide bars with a free and modern alternative to expensive proprietary solutions**, while giving developers complete control over the source code.

OpenPayKit is designed to be installed, customized and extended according to each establishment's needs.

---

# 🇫🇷 Français

## 📖 À propos

OpenPayKit est un projet **open-source de prise de commande, de gestion des tickets de caisse et de paiement destiné aux bars et établissements similaires**.

Un client peut consulter la carte, passer une commande et recevoir un ticket. Le personnel peut ensuite gérer la commande et son paiement depuis un terminal mobile.

L'objectif d'OpenPayKit n'est pas seulement de digitaliser la prise de commande.

> **Le but est de fournir aux bars un outil gratuit, personnalisable et extensible permettant de réduire leurs coûts et d'améliorer leur rentabilité.**

Le projet est conçu avec une philosophie **developer-first** : le code doit être clair, documenté et facilement modifiable.

---

## ✨ Fonctionnalités prévues

### 📱 Commande

* Carte des produits accessible depuis un smartphone
* Catégories et produits personnalisables
* Panier
* Création et suivi des commandes
* Association d'une commande à une table
* Transmission de la commande au bar

### 🧾 Tickets de caisse

* Création automatique d'un ticket
* Numérotation des tickets
* Gestion du statut du ticket
* Gestion du paiement
* Impression sur imprimante thermique portable
* Génération d'un QR Code unique associé au ticket

### 💳 Paiement

OpenPayKit est conçu pour pouvoir fonctionner avec différents systèmes de paiement.

Le premier objectif est de permettre le paiement depuis un **terminal Android équipé du NFC**, grâce à une solution de Tap to Pay compatible.

L'architecture sera conçue afin de ne pas rendre OpenPayKit dépendant d'un fournisseur particulier.

```text
OpenPayKit
    │
    └── Payment Provider
          ├── Provider A
          ├── Provider B
          └── Custom Provider
```

Les prestataires de paiement seront intégrés sous forme de modules afin de permettre à chaque établissement de choisir la solution correspondant à ses besoins.

### 🔳 QR Codes

Chaque ticket peut générer un **QR Code unique**.

Ce QR Code peut permettre d'accéder à différentes expériences :

* récompense ;
* boisson offerte ;
* réduction ;
* programme de fidélité ;
* chanson de karaoké ;
* promotion ;
* expérience personnalisée.

Ces fonctionnalités pourront être développées sous forme de plugins.

### 🔌 Plugins

OpenPayKit est conçu pour être extensible.

Les fonctionnalités supplémentaires pourront être ajoutées sous forme de plugins :

```text
plugins/
├── payment/
├── loyalty/
├── promotions/
├── karaoke/
└── custom/
```

L'objectif est de permettre à la communauté de créer ses propres intégrations.

---

## 💰 Une priorité : la rentabilité du bar

OpenPayKit est conçu autour d'un principe simple :

> **Un outil de caisse doit aider le bar à gagner plus et à dépenser moins.**

Le projet cherche notamment à permettre :

* la réduction des coûts logiciels ;
* la réduction des erreurs de prise de commande ;
* une prise de commande plus rapide ;
* l'augmentation du panier moyen ;
* des promotions personnalisées ;
* des systèmes de fidélité ;
* des expériences client accessibles depuis le ticket ;
* l'analyse des ventes et des produits.

À terme, OpenPayKit pourra également intégrer des mécanismes d'upselling et de recommandations afin d'augmenter la valeur moyenne des commandes.

---

## 🖨️ Matériel

Le système est pensé pour fonctionner avec un équipement mobile :

```text
📱 Terminal Android
       │
       ├── OpenPayKit
       ├── NFC / paiement
       │
       └── Bluetooth
              │
              ▼
       🖨️ Imprimante thermique
```

Le terminal doit notamment pouvoir disposer de :

* NFC ;
* 4G/5G ou Wi-Fi ;
* Android récent ;
* Bluetooth ;
* une autonomie suffisante pour une utilisation intensive.

Une petite imprimante thermique portable Bluetooth pourra être utilisée pour imprimer les tickets.

---

## 🛠️ Installation

OpenPayKit vise une installation simple, y compris pour les utilisateurs qui ne sont pas développeurs.

Une interface graphique accessible depuis un navigateur permettra de configurer l'installation :

```text
OpenPayKit Installer

Bar name
[ My Bar                     ]

Database
[ PostgreSQL ▼               ]

Payment provider
[ Select provider ▼          ]

[ Install OpenPayKit ]
```

L'objectif est qu'un établissement puisse installer et configurer OpenPayKit sans avoir besoin de maîtriser toute la configuration technique du projet.

Les développeurs pourront également effectuer une installation manuelle.

---

## 🧩 Architecture

OpenPayKit sera organisé autour d'un cœur minimal et de modules indépendants.

```text
                    OpenPayKit
                        │
          ┌─────────────┼─────────────┐
          │             │             │
       Products       Orders       Receipts
          │             │             │
          └─────────────┼─────────────┘
                        │
                    Payments
                        │
                     Plugins
                        │
          ┌─────────────┼─────────────┐
          │             │             │
       Payment       Loyalty       Karaoke
       Provider
```

Cette architecture doit permettre d'ajouter des fonctionnalités sans modifier le cœur du système.

---

## 📚 Documentation

La documentation est une partie essentielle du projet.

Elle aura pour objectif d'expliquer :

* l'installation ;
* la configuration ;
* l'architecture ;
* le fonctionnement des commandes ;
* le système de tickets ;
* les paiements ;
* les plugins ;
* la création d'intégrations personnalisées ;
* la contribution au projet.

OpenPayKit doit être suffisamment documenté pour qu'un développeur puisse comprendre le projet et le modifier facilement.

---

## 🗺️ Roadmap

### Phase 1 — Core

* [ ] Architecture du projet
* [ ] Gestion des produits
* [ ] Carte
* [ ] Panier
* [ ] Commandes
* [ ] Gestion des tables
* [ ] Tickets
* [ ] Statuts de commande

### Phase 2 — Terminal

* [ ] Application Android
* [ ] Support NFC
* [ ] Communication avec le serveur
* [ ] Gestion des terminaux
* [ ] Connexion à une imprimante Bluetooth
* [ ] Impression des tickets
* [ ] Génération des QR Codes

### Phase 3 — Paiement

* [ ] Abstraction `PaymentProvider`
* [ ] Premier fournisseur de paiement
* [ ] Tap to Pay
* [ ] Confirmation des paiements
* [ ] Remboursements
* [ ] Gestion des erreurs de paiement

### Phase 4 — Extensions

* [ ] Système de plugins
* [ ] Plugin fidélité
* [ ] Plugin promotions
* [ ] Plugin QR Code
* [ ] Plugin karaoké
* [ ] API publique pour les plugins

### Phase 5 — Analytics

* [ ] Statistiques de ventes
* [ ] Panier moyen
* [ ] Produits les plus vendus
* [ ] Analyse des périodes de forte/faible activité
* [ ] Outils d'aide à la rentabilité

---

## 🤝 Open-source

OpenPayKit est conçu pour être un projet communautaire.

Les développeurs sont invités à :

* proposer des fonctionnalités ;
* créer des plugins ;
* améliorer la documentation ;
* corriger des bugs ;
* proposer des intégrations ;
* partager leurs retours.

Les établissements peuvent adapter OpenPayKit à leurs propres besoins.

---

## 📄 Licence

OpenPayKit est distribué sous licence **MIT**.

Voir le fichier [`LICENSE`](LICENSE) pour plus d'informations.

---

## 🚧 Statut du projet

> **Early development**

OpenPayKit est actuellement en phase de conception et de développement initial.

Les fonctionnalités, l'architecture et les choix technologiques sont susceptibles d'évoluer.

---

# 🇬🇧 English

## 📖 About

OpenPayKit is an **open-source ordering, point-of-sale and payment project designed for bars and similar establishments**.

Customers can browse the menu, place orders and receive a receipt. Staff can then manage orders and payments from a mobile terminal.

The goal of OpenPayKit is not simply to digitize ordering.

> **The goal is to provide bars with a free, customizable and extensible solution that helps reduce costs and improve profitability.**

The project follows a **developer-first** philosophy: the source code should be clear, well documented and easy to customize.

---

## ✨ Planned Features

### 📱 Ordering

* Menu accessible from a smartphone
* Customizable categories and products
* Shopping cart
* Order creation and tracking
* Table assignment
* Order transmission to the bar

### 🧾 Receipts

* Automatic receipt generation
* Receipt numbering
* Receipt status management
* Payment status management
* Portable thermal printer support
* Unique QR Code generated for each receipt

### 💳 Payments

OpenPayKit is designed to support multiple payment systems.

The initial goal is to enable payments through an **NFC-enabled Android terminal**, using a compatible Tap to Pay solution.

The architecture will be designed so that OpenPayKit is not tied to a specific payment provider.

```text
OpenPayKit
    │
    └── Payment Provider
          ├── Provider A
          ├── Provider B
          └── Custom Provider
```

Payment providers will be implemented as modules, allowing each establishment to choose the solution that best fits its needs.

### 🔳 QR Codes

Each receipt can generate a **unique QR Code**.

The QR Code can provide access to different experiences:

* rewards;
* free drinks;
* discounts;
* loyalty programs;
* karaoke songs;
* promotions;
* custom experiences.

These features can be implemented as plugins.

### 🔌 Plugins

OpenPayKit is designed to be extensible.

Additional features can be added through plugins:

```text
plugins/
├── payment/
├── loyalty/
├── promotions/
├── karaoke/
└── custom/
```

The goal is to allow the community to build and share their own integrations.

---

## 💰 A Focus on Bar Profitability

OpenPayKit is built around a simple principle:

> **A point-of-sale system should help a bar make more money while spending less.**

The project aims to support:

* lower software costs;
* fewer ordering mistakes;
* faster ordering;
* increased average order value;
* personalized promotions;
* loyalty programs;
* ticket-based customer experiences;
* sales and product analytics.

In the future, OpenPayKit may also provide upselling and recommendation features designed to increase average order value.

---

## 🖨️ Hardware

The system is designed around a mobile setup:

```text
📱 Android Terminal
       │
       ├── OpenPayKit
       ├── NFC / payments
       │
       └── Bluetooth
              │
              ▼
       🖨️ Thermal Printer
```

The terminal should support:

* NFC;
* 4G/5G or Wi-Fi;
* a recent Android version;
* Bluetooth;
* sufficient battery life for intensive use.

A small portable Bluetooth thermal printer can be used to print receipts.

---

## 🛠️ Installation

OpenPayKit aims to provide a simple installation process, including for non-technical users.

A browser-based graphical installer will allow users to configure their installation:

```text
OpenPayKit Installer

Bar name
[ My Bar                     ]

Database
[ PostgreSQL ▼               ]

Payment provider
[ Select provider ▼          ]

[ Install OpenPayKit ]
```

The goal is to allow an establishment to install and configure OpenPayKit without requiring extensive technical knowledge.

Developers will also be able to perform a manual installation.

---

## 🧩 Architecture

OpenPayKit will be built around a minimal core and independent modules.

```text
                    OpenPayKit
                        │
          ┌─────────────┼─────────────┐
          │             │             │
       Products       Orders       Receipts
          │             │             │
          └─────────────┼─────────────┘
                        │
                    Payments
                        │
                     Plugins
                        │
          ┌─────────────┼─────────────┐
          │             │             │
       Payment       Loyalty       Karaoke
       Provider
```

This architecture should make it possible to add new features without modifying the core system.

---

## 📚 Documentation

Documentation is a core part of the project.

It will cover:

* installation;
* configuration;
* architecture;
* order management;
* receipt management;
* payments;
* plugins;
* custom integrations;
* contributing to the project.

OpenPayKit should be documented well enough for developers to understand, modify and extend the project easily.

---

## 🗺️ Roadmap

### Phase 1 — Core

* [ ] Project architecture
* [ ] Product management
* [ ] Menu
* [ ] Shopping cart
* [ ] Orders
* [ ] Table management
* [ ] Receipts
* [ ] Order statuses

### Phase 2 — Terminal

* [ ] Android application
* [ ] NFC support
* [ ] Server communication
* [ ] Terminal management
* [ ] Bluetooth printer support
* [ ] Receipt printing
* [ ] QR Code generation

### Phase 3 — Payments

* [ ] `PaymentProvider` abstraction
* [ ] First payment provider
* [ ] Tap to Pay
* [ ] Payment confirmation
* [ ] Refunds
* [ ] Payment error handling

### Phase 4 — Extensions

* [ ] Plugin system
* [ ] Loyalty plugin
* [ ] Promotions plugin
* [ ] QR Code plugin
* [ ] Karaoke plugin
* [ ] Public plugin API

### Phase 5 — Analytics

* [ ] Sales analytics
* [ ] Average order value
* [ ] Best-selling products
* [ ] Peak/off-peak analysis
* [ ] Profitability tools

---

## 🤝 Open-source

OpenPayKit is designed as a community-driven project.

Developers are welcome to:

* propose features;
* build plugins;
* improve documentation;
* fix bugs;
* create integrations;
* share feedback.

Establishments can adapt OpenPayKit to their own needs.

---

## 📄 License

OpenPayKit is released under the **MIT License**.

See [`LICENSE`](LICENSE) for more information.

---

## 🚧 Project Status

> **Early development**

OpenPayKit is currently in the initial design and development phase.

Features, architecture and technology choices may evolve as the project progresses.
