# Cloud-Based Warehouse and Logistics Management System (CWLMS)

> One smart, secure, online platform that tracks goods from the supplier's truck to the customer's door.

![Status](https://img.shields.io/badge/status-in%20development-orange)
![Cloud](https://img.shields.io/badge/deployment-cloud--native-1B7F79)
![License](https://img.shields.io/badge/license-MIT-blue)

---

## Project Details

**Project Title:** Cloud-Based Warehouse and Logistics Management System (CWLMS)

**Course:** Cloud Infrastructure and Services (25CS2206E) | **A.Y.:** 2026-2027

### Project Description

CWLMS is a scalable digital platform that streamlines inventory management, order tracking, warehousing operations and logistics processes in real time through a secure, cloud-based environment.

### Team Members

**Team Number:** 7 | **Section:** 4

| S.No. | Name | Roll No. |
|---|---|---|
| 1 | Krish Sureja | 2520030134 |
| 2 | Harshit Sajjanapu | 2520030187 |
| 3 | Karthik Vanka | 2520030053 |

### Guide Details

**Dr. V. Sireesha**  
Professor, Department of CSE  
KLH University, Bowrampet, Hyderabad-500043, Telangana, India.

---

## Table of Contents

1. [Project Details](#project-details)
2. [Abstract](#abstract)
3. [Overview](#overview)
4. [Problem Statement](#problem-statement)
5. [Objectives](#objectives)
6. [How It Works: Life of One Order](#how-it-works-life-of-one-order)
7. [Features and Modules](#features-and-modules)
8. [System Architecture](#system-architecture)
9. [Tech Stack](#tech-stack)
10. [Suggested Project Structure](#suggested-project-structure)
11. [Getting Started](#getting-started)
12. [Security](#security)
13. [Roadmap](#roadmap)
14. [Advantages and Challenges](#advantages-and-challenges)
15. [Real-World Applications](#real-world-applications)
16. [Future Scope](#future-scope)
17. [Glossary](#glossary)
18. [Contributing](#contributing)
19. [License](#license)

---

## Abstract

The Cloud-Based Warehouse and Logistics Management System (CWLMS) is a scalable, web-accessible platform that digitizes the entire supply chain, from receiving and storing goods to picking, packing, dispatching and delivering orders. Traditional warehouses depend on paper registers and spreadsheets, which lead to data errors, stock mismatches, slow order processing and poor route planning. CWLMS replaces them with one secure cloud platform that gives staff, managers, drivers, suppliers and customers the same live view.

The system provides real-time inventory tracking with barcode scanning and low-stock alerts; automated order management from placement to delivery; warehouse operations such as put-away, picking and cycle counting; vehicle and driver management with live GPS tracking; role-based access control; notifications; invoicing; and analytics dashboards with demand forecasting. It follows a multi-tier, cloud-native architecture hosted on AWS, so it scales automatically and stays highly available.

Expected outcomes include reduced manual effort and cost, fewer stock errors, faster order fulfilment, on-time deliveries and data-driven decisions through a secure, pay-as-you-go model.

**AWS services:** Amazon EC2 (with Load Balancing and Auto Scaling), RDS (PostgreSQL), ElastiCache (Redis), S3, CloudFront, Lambda, SQS, SNS, SES, Cognito, IAM, Location Service and CloudWatch.

---

## Overview

**CWLMS** is a centralized, web-accessible platform that digitizes every stage of the supply chain: receiving goods, storing them, picking and packing orders, dispatching shipments, and delivering to the end customer.

Instead of spreadsheets, paper registers and disconnected on-premise software, all data lives in a **secure cloud environment**. Warehouse staff, managers, drivers, suppliers and customers see the same live information from any device.

The system is the single source of truth for questions like:

- How much stock do we have, and where exactly is it?
- Which orders are pending, packed, shipped or delayed?
- Which vehicle is carrying which shipment, and when will it arrive?
- Which products are running low and need reordering?

> **New to the idea?** Think of it as a smart digital notebook for a warehouse, shared live by everyone who needs it. "Cloud" simply means the data is kept on secure internet servers instead of one office computer.

---

## Problem Statement

Traditional warehouse and logistics operations suffer from:

- Manual record keeping, causing errors, duplicate entries and lost data
- No real-time visibility, so stock mismatches and stockouts are common
- Slow order processing and inefficient picking
- Poor route planning, which raises fuel cost and delays deliveries
- Weak communication between warehouse, transport and customers
- Difficulty scaling during peak seasons
- High infrastructure and maintenance cost for on-premise servers

A cloud-based system solves these by centralizing data, automating workflows and scaling on demand.

---

## Objectives

- Provide **real-time inventory tracking** across one or multiple warehouses
- **Automate order management** from placement to delivery
- Optimize warehouse space, picking paths and labor allocation
- Enable **live shipment tracking** and route optimization
- Reduce operational cost and human error
- Provide **analytics and reports** for data-driven decisions
- Ensure **secure, role-based access** to data
- Build a system that **scales** as the business grows

---

## How It Works: Life of One Order

```
 INSIDE THE WAREHOUSE                              OUT TO THE CUSTOMER
┌────────────┐   ┌────────────┐   ┌──────────────┐   ┌──────────────┐   ┌──────────┐   ┌───────────┐
│ 1. Goods   │ → │ 2. Stored  │ → │ 3. Order     │ → │ 4. Pick and  │ → │ 5.       │ → │ 6.        │
│    arrive  │   │ rack/shelf │   │    placed    │   │    pack      │   │ Shipped  │   │ Delivered │
└────────────┘   └────────────┘   └──────────────┘   └──────────────┘   └──────────┘   └───────────┘
```

1. **Goods arrive:** items from a supplier are checked and logged.
2. **Stored:** each item gets a rack, shelf and bin location.
3. **Order placed:** a customer orders via website, mobile app or API.
4. **Pick and pack:** staff follow a pick list, scan barcodes, pack and label.
5. **Shipped:** a driver and vehicle are assigned and the route is planned.
6. **Delivered:** live tracking, proof of delivery (OTP, photo or signature) and invoice.

**Order status workflow:** `Placed → Confirmed → Picked → Packed → Shipped → Delivered`

---

## Features and Modules

### 1. User and Access Management
- Role-based access control (Admin, Warehouse Manager, Staff, Driver, Supplier, Customer)
- Secure login with JWT or OAuth, optional two-factor authentication
- Activity logs and audit trails

### 2. Inventory Management
- Add, update and delete products with SKU, category, batch and expiry details
- Real-time stock levels across locations
- Barcode and QR code generation and scanning
- Low-stock alerts and automatic reorder points
- Stock adjustments, returns and damaged-goods tracking
- Batch and expiry tracking (FIFO / FEFO)

### 3. Warehouse Operations (WMS Core)
- **Inbound:** purchase orders, goods receipt, quality check, put-away
- **Storage:** zone, rack, shelf and bin location mapping
- **Outbound:** pick lists, packing, labeling, dispatch
- Cycle counting and stock audits
- Warehouse layout and capacity visualization

### 4. Order Management
- Order creation from web, mobile or API (e-commerce integration)
- Order prioritization and bulk processing
- Returns and refund handling

### 5. Transportation and Logistics (TMS)
- Vehicle and driver management
- Shipment creation and assignment
- Route planning and optimization
- Live GPS tracking on a map, with ETA calculation
- Proof of delivery (signature, photo, OTP)
- Freight cost calculation

### 6. Supplier and Customer Management
- Supplier database, performance rating and purchase history
- Customer portal for order tracking
- Automated email, SMS and push notifications

### 7. Analytics and Reporting
- KPI dashboard: inventory turnover, order fulfillment rate, on-time delivery rate, warehouse utilization
- Sales, stock and delivery reports (PDF and Excel export)
- Demand forecasting from historical data
- Cost analysis and performance trends

### 8. Billing and Invoicing
- Auto-generated invoices and delivery challans
- Tax and GST calculation
- Payment status tracking

### 9. Notifications and Alerts
- Low stock, delayed shipment and failed delivery alerts
- Real-time updates via WebSockets, email and SMS

---

## System Architecture

CWLMS follows a multi-tier, cloud-native architecture.

```
┌──────────────────────────────────────────────────────────────┐
│ 1. PRESENTATION   Web dashboard · Mobile app · Tracking page │
├──────────────────────────────────────────────────────────────┤
│ 2. APPLICATION    REST APIs · Business logic · Auth · Alerts │
├──────────────────────────────────────────────────────────────┤
│ 3. DATA           Relational DB · Redis cache · File storage │
├──────────────────────────────────────────────────────────────┤
│ 4. INTEGRATION    Maps · Payments · SMS/Email · E-commerce   │
├──────────────────────────────────────────────────────────────┤
│ 5. INFRASTRUCTURE Compute · Load balancer · Auto-scaling ·   │
│                   Backups · Monitoring                       │
└──────────────────────────────────────────────────────────────┘
```

> **Monolith vs microservices:** a single monolith is simpler and ideal for a student project. A microservices design (Inventory, Orders, Shipping, Auth and Notification services) is the more advanced, scalable option and can be adopted later.

---

## Tech Stack

### Recommended minimum viable stack

| Layer | Tool |
|---|---|
| Frontend | React + Tailwind CSS (Vite) |
| Backend | Node.js + Express |
| Database | PostgreSQL or MongoDB |
| Cache | Redis |
| Live updates | Socket.IO |
| Maps | Leaflet (OpenStreetMap) or Google Maps |
| Containers | Docker, Docker Compose |
| Hosting | AWS, Render or Railway |
| CI/CD | GitHub Actions |

### Full set of options

| Area | Options |
|---|---|
| **Frontend** | React, Next.js, Angular; Tailwind, Material UI; Redux Toolkit, Zustand, React Query; Recharts, Chart.js, D3 |
| **Mobile** | React Native, Flutter |
| **Backend** | Node.js (Express, NestJS), Django/FastAPI, Spring Boot |
| **API style** | REST (optionally GraphQL) |
| **Auth** | JWT, OAuth 2.0, Passport.js, bcrypt |
| **Jobs and queues** | BullMQ, Celery, node-cron; RabbitMQ, Kafka, AWS SQS |
| **Databases** | PostgreSQL, MySQL, MongoDB, Redis, Elasticsearch |
| **File storage** | AWS S3, Google Cloud Storage, Cloudinary |
| **Cloud** | AWS (EC2, S3, RDS, Lambda, CloudFront, SQS, SNS, CloudWatch), Azure, Google Cloud; student-friendly: Render, Railway, Vercel, Netlify, MongoDB Atlas, Supabase |
| **DevOps** | Git/GitHub, Docker, Kubernetes (optional), GitHub Actions, Jenkins, Terraform (optional) |
| **Monitoring** | Prometheus, Grafana, ELK stack, CloudWatch |
| **Testing** | Jest, Mocha, Postman, Cypress, Selenium |
| **Design and planning** | Figma, draw.io, Lucidchart, Jira, Trello, Notion |

### Optional integrations and enhancements

- **APIs:** Google Maps or Mapbox, Razorpay or Stripe, Twilio or Firebase Cloud Messaging, SendGrid or Nodemailer, Shopify or WooCommerce
- **Hardware / IoT:** barcode and QR scanners, RFID, GPS trackers, temperature and humidity sensors, ESP32 or Arduino for demos
- **AI / analytics:** Python (Pandas, NumPy, scikit-learn), Prophet or LSTM for forecasting, Google OR-Tools for route optimization, Power BI or Tableau

---

## Suggested Project Structure

A starting layout for the monolith version:

```
cwlms/
├── client/                  # React frontend
│   ├── src/
│   │   ├── components/
│   │   ├── pages/           # Dashboard, Inventory, Orders, Tracking
│   │   ├── hooks/
│   │   └── services/        # API calls
│   └── package.json
├── server/                  # Node.js + Express backend
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/      # auth, validation, rate limiting
│   │   ├── models/          # products, warehouses, orders, shipments, users
│   │   ├── routes/
│   │   ├── services/        # business logic, notifications
│   │   └── sockets/         # live tracking and alerts
│   └── package.json
├── docs/                    # ER diagram, architecture diagram, wireframes
├── docker-compose.yml
├── .github/workflows/       # CI/CD pipeline
└── README.md
```

---

## Getting Started

> These steps describe the **planned** setup for the recommended stack. Adjust the commands to match the code as it is built.

### Prerequisites

- Node.js 18 or later
- PostgreSQL (or MongoDB) and Redis, or Docker with Docker Compose
- Git

### Installation

```bash
# 1. Clone the repository
git clone <your-repo-url>
cd cwlms

# 2. Install dependencies
cd server && npm install
cd ../client && npm install
```

### Environment variables

Create a `.env` file inside `server/`:

```env
PORT=5000
DATABASE_URL=your_database_connection_string
REDIS_URL=your_redis_connection_string
JWT_SECRET=a_long_random_secret
MAPS_API_KEY=your_maps_api_key
```

Never commit `.env` files or real keys to Git.

### Run locally

```bash
# Backend
cd server && npm run dev

# Frontend (in a second terminal)
cd client && npm run dev
```

### Run with Docker

```bash
docker compose up --build
```

---

## Security

Security is designed in from day one:

- HTTPS/TLS encryption for all traffic
- Password hashing with bcrypt or Argon2
- Role-based access control with least-privilege policies
- Input validation to prevent SQL injection and XSS
- Rate limiting and API gateway protection
- Encrypted backups and database encryption at rest
- Audit logs and regular security reviews for traceability

---

## Roadmap

| Phase | Step | Focus |
|---|---|---|
| **Plan** | 1. Requirement analysis | Users, workflows, features |
| | 2. System design | ER diagram, use cases, architecture, wireframes |
| | 3. Database design | Products, warehouses, inventory, orders, shipments, users |
| **Build** | 4. Backend development | Auth, inventory, order and shipment APIs |
| | 5. Frontend development | Dashboards, forms, tracking map |
| | 6. Integration | Maps, notifications, payments |
| **Launch** | 7. Testing | Unit, integration, user acceptance |
| | 8. Deployment | Containerize and deploy with CI/CD |
| | 9. Monitoring and improvement | Logs, analytics, feedback |

---

## Advantages and Challenges

**Advantages**

- **Scalable:** resources grow or shrink with demand
- **Cost-effective:** pay-as-you-go instead of heavy hardware
- **Accessible:** use it from anywhere on any device
- **Real-time:** live stock and shipment status
- **Automated:** fewer manual tasks and errors
- **Reliable:** cloud backups and high availability
- **Easy to integrate:** works with ERP, e-commerce and payment systems

**Challenges**

- Dependence on internet connectivity
- Data security and privacy concerns
- Initial setup and integration complexity
- Vendor lock-in with a single cloud provider
- Staff training needed for adoption

---

## Real-World Applications

- E-commerce fulfillment centers
- Retail and supermarket supply chains
- Pharmaceutical and cold-storage warehouses
- Manufacturing and raw-material management
- Third-party logistics (3PL) companies
- Food delivery and grocery distribution

---

## Future Scope

- AI-based demand forecasting and smart replenishment
- Warehouse robotics and automated guided vehicles (AGVs)
- Blockchain for transparent supply-chain tracking
- Computer vision for automated stock counting
- Voice-picking and AR-assisted picking
- Sustainability tracking, such as the carbon footprint of delivery routes

---

## Glossary

| Term | Meaning |
|---|---|
| **SKU** | Stock Keeping Unit: a unique code for each product |
| **FIFO / FEFO** | First-In-First-Out / First-Expiry-First-Out: oldest or earliest-expiry stock ships first |
| **WMS** | Warehouse Management System: software that runs the warehouse |
| **TMS** | Transport Management System: software that runs transport |
| **API** | Application Programming Interface: a doorway that lets two programs talk |
| **JWT** | JSON Web Token: a digital pass that proves who you are after login |
| **RBAC** | Role-Based Access Control: each role sees only what it needs |
| **ETA** | Estimated Time of Arrival |
| **3PL** | Third-Party Logistics: an outside company that ships goods for others |
| **KPI** | Key Performance Indicator: a number showing how well the business is doing |

---

## Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Commit your changes: `git commit -m "Add your feature"`
4. Push the branch: `git push origin feature/your-feature`
5. Open a Pull Request

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
