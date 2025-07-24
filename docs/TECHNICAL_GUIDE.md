# Safi Greens – Technical Guide

Welcome, developer! This Technical Guide provides everything you need to understand, integrate, and contribute to the Safi Greens platform—the digital solution empowering Mama Mboga vendors and their customers.

---

## Table of Contents

- [System Overview](#system-overview)
- [Architecture Diagram](#architecture-diagram)
- [Technology Stack](#technology-stack)
- [Progressive Web App Features](#progressive-web-app-features)
- [API Reference](#api-reference)
- [Authentication & Security](#authentication--security)
- [Integration: MPesa Payments](#integration-mpesa-payments)
- [Deployment & Hosting](#deployment--hosting)
- [Testing & QA](#testing--qa)
- [Troubleshooting & Debugging](#troubleshooting--debugging)
- [Contributing Guidelines](#contributing-guidelines)
- [Release Notes](#release-notes)
- [Resources & Links](#resources--links)

---

## System Overview

Safi Greens is a Progressive Web App (PWA) connecting Mama Mboga vendors and urban customers, featuring:

- Product listing and management
- Order placement and tracking
- MPesa payment integration
- Last-mile delivery coordination
- AI-powered advisory agent (for shelf life, spoilage, and savings tips)

---

## Architecture Diagram

[![View System Architecture](assets/Safi-Greens-System-Architecture-Diagram-1.png)](https://lucid.app/lucidchart/7263de22-187a-420f-a047-80f08c20bb45/edit?referringApp=slack&invitationId=inv_64dcd694-e37b-43ba-a2c7-c936a39d5e59&page=0_0#)

---

## Technology Stack

- **Frontend:** ReactJS (PWA), HTML5, CSS3, JavaScript/TypeScript
- **Backend:**Django
- **Database:**PostGres
- **Payments:** MPesa API
- **AI Agent:** Python (integration via REST API)
- **Hosting:** [e.g. Heroku]
- **Version Control:** GitHub

---

## Progressive Web App Features

- Offline support and mobile optimization
- Push notifications for orders and delivery status
- Responsive design for kiosk and customer devices
- Secure authentication and user management

---

## API Reference

Core REST endpoints:

- `POST /users/register` – User registration
- `POST /users/login` – User Login
- `GET /api/products` – List available produce
- `POST /api/vendor-products` – Add new product (vendor)
- `GET /api/orders` – View orders (vendor & customer)
- `POST /api/add-orders` – Place order
- `POST /api/payments` – Process MPesa payment
- `POST /api/Subscriptions` –Subscriptions

Full API details: [See API Documentation](docs/API_REFERENCE.md)

---

## Authentication & Security

- JWT-based authentication for users
- Role-based access (vendor vs customer vs admin)
- Secure password storage (bcrypt hashing)
- All sensitive operations require authentication
- API rate limiting and input validation

---

## Integration: MPesa Payments

- Uses MPesa Daraja API for mobile payments
- Payment flow: customer initiates payment → backend verifies transaction → order confirmed
- Ensure proper handling of callbacks and payment confirmations

Reference: [MPesa Daraja API Docs](https://developer.safaricom.co.ke/daraja/apis/post/safaricom-safaricom)

---

## Deployment & Hosting

- CI/CD pipeline via GitHub Actions
- Recommended: Dockerize backend for easy cloud deployment
- Frontend can be hosted via GitHub Pages or Netlify
- Environment variables for DB, MPesa API keys, and secrets

---

## Testing & QA

- Unit and integration tests (Jest for JS/TS, Mocha for Node.js)
- End-to-end tests for order flow and payments
- Manual QA for mobile browser/device compatibility
- Use staging environment for release testing

---

## Troubleshooting & Debugging

- Enable detailed logging for backend and payment operations
- Common issues:

  - MPesa payments not confirming: check callback URL and API credentials
  - Order not showing: verify product availability and DB connection
  - AI tips not loading: check advisor API endpoint and network

- Refer to [Troubleshooting FAQ](docs/FAQ.md#troubleshooting)

---

## Contributing Guidelines

- Fork the repository and create feature branches
- Write clear commit messages and Pull Request descriptions
- Follow existing coding styles (see `.eslintrc`, `.prettierrc`)
- Add tests for new features
- See [CONTRIBUTING.md](docs/CONTRIBUTING.md)

---

## Release Notes

- [See full release history](docs/RELEASE_NOTES.md)

---

## Resources & Links

- [System Architecture Diagram (Lucidchart)](https://lucid.app/lucidchart/7263de22-187a-420f-a047-80f08c20bb45/edit?referringApp=slack&invitationId=inv_64dcd694-e37b-43ba-a2c7-c936a39d5e59&page=0_0#)
- [Mockup Design (Figma)](https://www.figma.com/design/neV9t33HSy5WE2IHlVgwNH/Big_Minds-Design?node-id=424-128&p=f&t=IB79oess1v2oQCRu-0)
- [Admin Dashboard (Figma)](https://www.figma.com/design/aS7x1NNWoTxKNRX7Oj2K0G/Admin-Safi?node-id=0-1&p=f&t=rEuVmzaAGaTkMwlM-0)
- [MPesa Daraja API Docs](https://developer.safaricom.co.ke/daraja/apis/post/safaricom-safaricom)
- [API Reference](docs/API_REFERENCE.md)

---

**Happy coding and welcome to Safi Greens!**
