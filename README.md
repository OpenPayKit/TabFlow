# TabFlow

**Open-source ordering, POS and payment platform for bars.**

TabFlow is an open-source platform designed for bars, cafés and similar establishments.

The goal is simple: provide a **complete, customizable and low-cost ordering and point-of-sale system**, while helping establishments improve their profitability.

Menu → Order → Ticket → Payment → Receipt → QR Code → Customer experience.

---

## ✨ Features

### 🍻 Menu & Products

* Digital menu
* Product management
* Categories
* Prices
* Availability
* Product customization
* Promotions and special offers

### 🧾 Orders & Tickets

* Create and manage orders
* Table management
* Order status tracking
* Ticket generation
* Receipt management
* Payment status
* Refund support
* Ticket history

### 💳 Payments

TabFlow does **not process card data itself**.

Payments are handled through external payment providers using a provider abstraction layer.

This allows TabFlow to support multiple payment providers without locking the project to a single company.

Example architecture:

```text
TabFlow
   │
   ├── PaymentProvider
   │      ├── SumUp
   │      ├── Mollie
   │      ├── Adyen
   │      └── Other providers
   │
   └── Payment confirmation
```

The first mobile payment implementation is designed around **Android Tap-to-Pay**.

---

## 📱 Mobile POS

A standard Android smartphone can act as the POS/payment terminal.

The device can handle:

* TabFlow application
* Order management
* Payment
* NFC Tap-to-Pay
* Customer receipt
* QR code generation
* Bluetooth printer connection
* 4G/5G or Wi-Fi connectivity

### Recommended phone

The project does not require a specific phone model.

The recommended configuration is:

* Android
* NFC
* 4G/5G
* Bluetooth
* Wi-Fi
* USB-C
* Good battery life

Example:

* [Samsung Galaxy A26 5G — Amazon France](https://www.amazon.fr/s?k=Samsung+Galaxy+A26+5G+NFC)

The hardware recommendation is only a reference. Any compatible Android device can potentially be used.

---

## 🖨️ Portable Receipt Printer

TabFlow can connect to a portable thermal printer through Bluetooth.

Recommended characteristics:

* Thermal printing
* Bluetooth
* 58 mm paper
* Android compatible
* ESC/POS support
* Battery powered
* Portable

Example:

* [Portable Bluetooth thermal printers 58 mm — Amazon France](https://www.amazon.fr/s?k=imprimante+thermique+portable+Bluetooth+58mm+ESC%2FPOS)

The printer is not mandatory for using TabFlow, but is recommended for a physical ticket workflow.

---

## 🔄 Complete Workflow

```text
Customer
   │
   ▼
Order
   │
   ▼
TabFlow
   │
   ▼
Ticket
   │
   ▼
Payment
   │
   ├── NFC / Tap-to-Pay
   │
   ▼
Payment confirmed
   │
   ▼
Unique QR Code
   │
   ▼
Receipt printed
   │
   ▼
Customer experience
```

---

## 🔐 Unique QR Codes

Each completed ticket can generate a unique QR code.

The QR code can give the customer access to additional experiences:

* Loyalty rewards
* Free drink
* Discount
* Promotional offer
* Karaoke song
* Customer games
* Special events
* Future loyalty features

QR codes should use secure tokens rather than exposing internal ticket IDs.

Possible security mechanisms:

* Random tokens
* Expiration dates
* One-time use
* Server-side validation
* Revocation

Example:

```text
Ticket #10482
      │
      ▼
Secure Token
      │
      ▼
QR Code
      │
      ▼
Customer
      │
      ▼
Reward / Experience
```

---

## 📈 Profitability

TabFlow is not intended to be only an electronic ordering system.

The project is designed to help establishments increase profitability.

Future features can include:

* Upselling
* Product recommendations
* Promotions
* Happy hours
* Loyalty programs
* Best-selling product analysis
* Average order value
* Peak-hour analysis
* Customer behavior
* Revenue analytics
* Product profitability
* Promotion performance

The objective is to help the establishment understand:

> **What sells, when it sells, and how to increase revenue.**

---

## 🧩 Plugin System

TabFlow is designed to be extensible.

Plugins can add functionality without modifying the core system.

Possible plugins:

```text
plugins/
├── loyalty/
├── promotions/
├── karaoke/
├── analytics/
├── rewards/
└── custom/
```

Examples:

* Loyalty system
* Karaoke
* Promotional campaigns
* Customer rewards
* External accounting
* Analytics
* Custom integrations

The long-term objective is to provide a public plugin API.

---

## 🏗️ Architecture

The project is designed around modular components.

```text
TabFlow
│
├── Core
│   ├── Products
│   ├── Orders
│   ├── Tables
│   ├── Tickets
│   ├── Receipts
│   └── Payments
│
├── PaymentProvider
│   ├── SumUp
│   ├── Mollie
│   ├── Adyen
│   └── Other providers
│
├── QR
│   ├── Tokens
│   ├── Rewards
│   └── Experiences
│
├── Plugins
│   ├── Loyalty
│   ├── Promotions
│   ├── Karaoke
│   └── Analytics
│
└── API
```

---

## 🗃️ Core Data

### Order

```text
id
table
items
subtotal
taxes
total
status
payment_status
payment_method
created_at
closed_at
```

### Ticket

```text
id
order_id
number
items
totals
payment
issued_at
```

### QR Token

```text
id
ticket_id
token
expires_at
used_at
status
```

---

## ⚙️ Installation

TabFlow should provide two installation methods.

### Graphical installation

A browser-based installer will guide the user through the setup.

Example:

```text
┌──────────────────────────────┐
│        TabFlow Setup         │
├──────────────────────────────┤
│                              │
│ Bar name:                    │
│ [ My Bar                  ]  │
│                              │
│ Database:                    │
│ [ PostgreSQL              ]  │
│                              │
│ Payment provider:             │
│ [ SumUp                   ]  │
│                              │
│        [ Install TabFlow ]   │
│                              │
└──────────────────────────────┘
```

### Manual installation

Advanced users can install and configure TabFlow manually.

Complete documentation will be provided.

---

## 🚀 Roadmap

### Phase 1 — Core

* [ ] Project architecture
* [ ] Database
* [ ] Products
* [ ] Menu
* [ ] Orders
* [ ] Tables
* [ ] Tickets
* [ ] Receipts
* [ ] Status management
* [ ] REST API

### Phase 2 — Mobile POS

* [ ] Android application
* [ ] NFC support
* [ ] Tap-to-Pay integration
* [ ] Terminal management
* [ ] Bluetooth printer
* [ ] Ticket printing
* [ ] QR code generation

### Phase 3 — Payments

* [ ] PaymentProvider abstraction
* [ ] First payment provider
* [ ] Payment confirmation
* [ ] Payment errors
* [ ] Refunds
* [ ] Payment history

### Phase 4 — Extensions

* [ ] Plugin system
* [ ] Loyalty
* [ ] Promotions
* [ ] Rewards
* [ ] Karaoke
* [ ] Public plugin API

### Phase 5 — Analytics

* [ ] Sales dashboard
* [ ] Average order value
* [ ] Best-selling products
* [ ] Peak hours
* [ ] Product profitability
* [ ] Promotion performance
* [ ] Customer analytics

---

## 🛠️ Recommended Hardware

The following hardware is recommended for a basic TabFlow installation.

| Hardware         | Recommended characteristics        |
| ---------------- | ---------------------------------- |
| Android phone    | NFC, Bluetooth, 4G/5G, Wi-Fi       |
| Portable printer | Bluetooth, thermal, 58 mm, ESC/POS |
| Internet         | Wi-Fi or mobile network            |
| Paper            | 58 mm thermal paper                |

### Amazon

**Android phone**

[Samsung Galaxy A26 5G — Amazon France](https://www.amazon.fr/s?k=Samsung+Galaxy+A26+5G+NFC)

**Portable thermal printer**

[Bluetooth thermal printer 58 mm ESC/POS — Amazon France](https://www.amazon.fr/s?k=imprimante+thermique+portable+Bluetooth+58mm+ESC%2FPOS)

These are **reference products only**. TabFlow should remain hardware-independent.

---

## 🔌 Payment Providers

The architecture is intentionally provider-independent.

Potential integrations include:

* SumUp
* Mollie
* Adyen
* Other compatible payment providers

The first integration can focus on Android Tap-to-Pay.

The core application should never depend directly on a single payment provider.

---

## 💡 Design Principles

TabFlow follows several principles:

### Open-source

The source code is public and documented.

### Customizable

Bars should be able to modify the software to match their needs.

### Low cost

No mandatory TabFlow subscription or license fee.

### Hardware-independent

The software should not be locked to one terminal or printer manufacturer.

### Provider-independent

Payment providers should be replaceable.

### Modular

Features should be added through plugins whenever possible.

### Profit-oriented

The system should help businesses increase their revenue and profitability.

---

## 🔒 Security

Security is a core requirement.

TabFlow should:

* Never store raw card data
* Use external payment providers for card processing
* Use secure authentication
* Use HTTPS
* Use secure QR tokens
* Validate payment confirmations server-side
* Support token expiration
* Support QR token revocation
* Log important operations
* Follow least-privilege principles

---

## 📚 Documentation

Documentation will cover:

* Installation
* Configuration
* API
* Database
* Payment providers
* Android application
* Hardware
* Printer integration
* QR codes
* Plugins
* Development
* Deployment

---

## 🤝 Contributing

TabFlow is an open-source project.

Contributions are welcome.

You can contribute through:

* Code
* Documentation
* Plugins
* Bug reports
* Feature requests
* Testing
* Translations

---

## 📄 License

TabFlow is released under the **MIT License**.

See [`LICENSE`](LICENSE) for the complete license text.

---

## ⚠️ Project Status

**Early development.**

TabFlow is currently a work in progress.

The architecture and features may change as development progresses.

---

## 🎯 Vision

TabFlow aims to become a simple, open and customizable platform for bars.

The long-term vision is:

```text
             TABFLOW
                │
       ┌────────┴────────┐
       │                 │
     ORDER            PAYMENT
       │                 │
       └────────┬────────┘
                │
             TICKET
                │
        ┌───────┴───────┐
        │               │
      RECEIPT           QR
        │               │
        │        ┌──────┴──────┐
        │        │             │
        │      LOYALTY      REWARDS
        │        │             │
        └────────┴─────────────┘
                 │
            PROFITABILITY
```

**Open source.
Customizable.
Low cost.
Built for bars.**
