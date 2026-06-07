# Dental Lab Management System

A comprehensive, production-ready management system for dental laboratories, handling customers, cases, production workflows, inventory, and advanced analytics.

## 📋 Table of Contents

- [Overview](#overview)
- [Core Modules](#core-modules)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Quick Start](#quick-start)
- [Documentation](#documentation)
- [Features](#features)

## 🏢 Overview

Dental Lab Management System is an enterprise-grade solution designed to streamline operations in dental laboratories. It provides complete visibility and control over the entire case lifecycle, from initial intake to final delivery.

**Key Benefits:**
- Reduce production time by 20-30%
- Improve quality control with automated tracking
- Real-time case status visibility
- Automated customer notifications
- Comprehensive analytics and reporting
- Machine integration and scheduling
- Complete audit trail

## 🏗️ Core Modules

### 1. **Customer Management**
- Dentist & Clinic database
- Contact information management
- Credit limits & pricing by customer
- Customer history & analytics
- Outstanding balance tracking

### 2. **Case Management**
- Case creation & auto-generated case numbers
- Patient information tracking
- Restoration types:
  - Crown
  - Bridge
  - Veneer
  - Implant
  - Denture
  - Orthodontic appliance
- Due date & priority tracking
- Status management with workflow automation

### 3. **Digital Files Management**
- STL, PLY, DICOM file storage
- Photo management
- 3Shape & Exocad file integration
- AWS S3 / MinIO cloud storage
- Version control & file history

### 4. **Workflow Tracking**
Automated workflow:
```
RECEPTION → DESIGN → VALIDATION → MILLING → SINTERING → FINISHING → QC → DELIVERY
```

Tracking:
- Who worked on the case
- Start/end time
- Delays & alerts
- Productivity metrics

### 5. **Production Management**
- Milling queue management
- Machine scheduling (Ceramill Motion 2)
- Material consumption tracking
- Nesting records
- Job batching & remake tracking

### 6. **Inventory Management**
- Zirconia, PMMA, Wax discs
- Titanium blanks & implant components
- Consumables tracking
- Stock alerts & expiration dates
- Supplier management

### 7. **Employee Management**
- Technician profiles
- Attendance tracking (Pointage)
- Productivity metrics
- Commission calculations
- Payroll exports

### 8. **Billing & Accounting**
- Quote generation
- Invoice creation
- Payment tracking
- Outstanding balance reports
- Customer statements
- VAT handling

### 9. **Delivery Management**
- Delivery notes generation
- Courier tracking integration
- Signature collection
- Return case handling

### 10. **Reports & Dashboard**
- Daily production reports
- Revenue analytics
- Cases by dentist
- Technician productivity
- Material consumption
- Machine utilization

### 11. **Advanced Features**
- **Barcode/QR Code**: Auto-generated per case
- **WhatsApp Notifications**: Case updates & alerts
- **AI Features**: Classification, delay prediction, forecasting, defect analysis

## 🛠️ Technology Stack

### Backend
- **Framework**: NestJS (Node.js)
- **Database**: PostgreSQL 15+
- **Caching**: Redis 7+
- **File Storage**: AWS S3 / MinIO
- **Authentication**: JWT + OAuth2
- **ORM**: TypeORM / Prisma

### Frontend
- **Framework**: React.js 18+
- **UI Library**: Tailwind CSS + Material-UI
- **State Management**: Redux Toolkit
- **Charts**: Recharts / Chart.js
- **Forms**: React Hook Form

### Integrations
- **3Shape API** - Design file management
- **Exocad API** - CAD file handling
- **Ceramill Motion 2** - Machine scheduling
- **WhatsApp Business API** - Notifications
- **Stripe** - Payment processing

### DevOps & Deployment
- **Containerization**: Docker & Docker Compose
- **CI/CD**: GitHub Actions
- **Cloud**: AWS / Azure / DigitalOcean
- **Monitoring**: ELK Stack / Datadog
- **Testing**: Jest, Cypress, Supertest

## 📁 Project Structure

```
dental-lab-management/
├── backend/                    # NestJS API
│   ├── src/
│   │   ├── modules/           # Feature modules
│   │   │   ├── customers/
│   │   │   ├── cases/
│   │   │   ├── files/
│   │   │   ├── workflow/
│   │   │   ├── production/
│   │   │   ├── inventory/
│   │   │   ├── employees/
│   │   │   ├── billing/
│   │   │   ├── delivery/
│   │   │   └── reports/
│   │   ├── common/            # Shared utilities
│   │   ├── config/            # Configuration
│   │   ├── middleware/        # Custom middleware
│   │   └── main.ts
│   ├── migrations/            # Database migrations
│   ├── tests/                 # Test suites
│   ├── docker/
│   ├── package.json
│   └── .env.example
├── frontend/                   # React application
│   ├── src/
│   │   ├── components/        # Reusable components
│   │   ├── pages/            # Page components
│   │   ├── modules/          # Feature modules
│   │   ├── stores/           # Redux stores
│   │   ├── services/         # API services
│   │   └── App.tsx
│   ├── public/
│   ├── package.json
│   └── .env.example
├── database/
│   ├── schemas/              # SQL schema files
│   ├── migrations/           # Migration files
│   └── seeds/                # Seed data
├── docs/                      # Documentation
│   ├── API.md
│   ├── DATABASE.md
│   ├── SETUP.md
│   ├── WORKFLOWS.md
│   ├── ARCHITECTURE.md
│   └── DEPLOYMENT.md
├── docker-compose.yml
├── .gitignore
└── LICENSE
```

## 🚀 Quick Start

### Prerequisites
- Node.js v16+
- Docker & Docker Compose
- Git

### Installation

```bash
# Clone repository
git clone https://github.com/khatimlabdz-lang/dental-lab-management.git
cd dental-lab-management

# Install dependencies
cd backend && npm install
cd ../frontend && npm install

# Setup environment
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env

# Start with Docker Compose
docker-compose up -d

# Run migrations
cd backend && npm run migrate

# Seed sample data
npm run seed
```

### Access
- **Frontend**: http://localhost:3001
- **Backend API**: http://localhost:3000/api/v1
- **Database**: localhost:5432
- **Redis**: localhost:6379

## 📖 Documentation

- **[Setup Guide](docs/SETUP.md)** - Installation and configuration
- **[API Documentation](docs/API.md)** - REST API endpoints
- **[Database Schema](docs/DATABASE.md)** - Database structure
- **[Workflow Details](docs/WORKFLOWS.md)** - Case workflow process
- **[Architecture](docs/ARCHITECTURE.md)** - System design
- **[Deployment](docs/DEPLOYMENT.md)** - Production deployment

## ✨ Key Features

✅ Multi-tenant support
✅ Real-time case tracking
✅ QR code generation & scanning
✅ Machine integration (Ceramill Motion 2)
✅ Advanced analytics & forecasting
✅ WhatsApp notifications
✅ Complete audit trail
✅ Role-based access control (RBAC)
✅ Export to Excel/PDF
✅ Mobile-responsive UI
✅ Dark mode support
✅ Multi-language support (i18n)

## 📊 Dashboard Capabilities

- **Daily Production**: Cases completed, materials used
- **Revenue Analytics**: Income, outstanding balances
- **Technician Performance**: Productivity, quality ratings
- **Machine Utilization**: Usage rates, maintenance schedules
- **Inventory Levels**: Stock status, expiration alerts
- **Delay Analysis**: Bottlenecks, performance trends

## 🔐 Security

- JWT-based authentication
- Role-based access control (RBAC)
- Data encryption at rest
- HTTPS enforced
- SQL injection prevention
- XSS protection
- CSRF tokens
- Rate limiting
- Audit logging

## 📈 Performance

- Response time: < 200ms
- Database query optimization
- Redis caching
- CDN integration
- Lazy loading
- Code splitting
- Image optimization

## 🧪 Testing

```bash
# Unit tests
npm run test

# Integration tests
npm run test:integration

# E2E tests
npm run test:e2e

# Coverage
npm run test:coverage
```

## 🤝 Contributing

Contributions are welcome! Please:
1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

MIT License - see [LICENSE](LICENSE) file for details

## 📞 Support

- **Issues**: GitHub Issues
- **Email**: support@dentallab.com
- **Documentation**: Check `/docs` folder

## 🗺️ Roadmap

- [ ] Mobile app (iOS/Android)
- [ ] AI-powered defect detection
- [ ] Advanced forecasting ML model
- [ ] Multi-lab support
- [ ] ERP integration
- [ ] Video conferencing for remote consultations
- [ ] Blockchain for supply chain tracking

---

**Made with ❤️ for dental laboratories worldwide**
