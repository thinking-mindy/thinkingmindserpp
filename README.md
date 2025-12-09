# Thinking Minds ERP

<div align="center">

![Thinking Minds ERP](public/minds2.png)

**A comprehensive, secure, and modern Enterprise Resource Planning (ERP) solution**

[![Next.js](https://img.shields.io/badge/Next.js-15.5.7-black)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.0-blue)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-Latest-blue)](https://www.typescriptlang.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-6.20-green)](https://www.mongodb.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

[Features](#-features) • [Installation](#-installation) • [Documentation](#-documentation) • [Changelog](#-changelog) • [Contributing](#-contributing)

</div>

---

## 📖 Introduction

**Thinking Minds ERP** is a full-featured, cloud-based Enterprise Resource Planning system designed to streamline business operations across multiple departments. Built with modern web technologies, it provides a unified platform for managing HR, Finance, Inventory, Procurement, IT assets, and more.

### Key Highlights

- 🚀 **Modern Tech Stack**: Built with Next.js 15, React 19, and TypeScript
- 🔒 **Enterprise Security**: Clerk authentication, audit logs, and compliance features
- 📊 **Real-time Analytics**: Advanced reporting and data visualization
- 🌍 **Multi-currency Support**: Handle transactions in multiple currencies
- 📱 **Responsive Design**: Works seamlessly on desktop, tablet, and mobile devices
- 🎨 **Beautiful UI**: Material-UI components with dark mode support

---

## ✨ Features

### Core Modules

#### 🏢 **HR & Payroll Management**
- Employee management and profiles
- Attendance tracking
- Payroll processing and payslip generation
- Leave request management
- Performance reviews

#### 💰 **Finance & Accounting**
- Invoice management
- Payment processing
- Expense tracking
- Financial reports and analytics
- Multi-currency support
- Cashier management
- Daily cash summaries

#### 📦 **Inventory Management**
- Product catalog management
- Stock tracking and movements
- Supplier management
- Purchase orders
- Low stock alerts
- Inventory analytics

#### 🛒 **Point of Sale (POS)**
- Real-time sales processing
- Multiple payment methods (Cash, Ecocash, Paynow)
- Receipt generation
- Sales reports
- Mobile-optimized checkout

#### 🛍️ **Procurement**
- Purchase order creation and tracking
- Supplier management
- Order approval workflows
- Procurement analytics

#### 💼 **CRM & Client Management**
- Contact management
- Sales pipeline tracking
- Client communication history
- Deal management

#### 📋 **Project & Task Management**
- Project creation and tracking
- Task assignment and deadlines
- Team collaboration
- Progress monitoring

#### 🖥️ **IT & Asset Management**
- Device inventory
- Asset tracking
- Access management
- System monitoring

#### 🎫 **Helpdesk & Support**
- Ticket management system
- Knowledge base
- User request tracking
- Support analytics

#### 📊 **Reports & Analytics**
- Customizable dashboards
- Real-time data visualization
- Export capabilities (PDF, Excel)
- Audit logs and compliance reports

#### 🔐 **Security & Compliance**
- Comprehensive audit logging
- Role-based access control
- Data encryption
- Compliance reporting

---

## 🛠️ Tech Stack

### Frontend
- **Next.js 15.5.7** - React framework with App Router
- **React 19** - UI library
- **TypeScript** - Type safety
- **Material-UI (MUI)** - Component library
- **Recharts** - Data visualization
- **React Query** - Data fetching and caching

### Backend
- **Next.js Server Actions** - Server-side logic
- **MongoDB 6.20** - Database
- **Clerk** - Authentication and user management

### Additional Libraries
- **Day.js** - Date manipulation
- **jsPDF** - PDF generation
- **QRCode** - QR code generation
- **Paynow** - Payment gateway integration
- **Resend** - Email service

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 18.x or higher
- **npm** or **pnpm** package manager
- **MongoDB** database (local or cloud instance)
- **Clerk** account for authentication

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/thinking-mindy/thinkingmindserp.git
cd thinkingmindserp
```

### 2. Install Dependencies

```bash
npm install --legacy-peer-deps
```

> **Note**: The `--legacy-peer-deps` flag is required due to some peer dependency conflicts with React 19.

### 3. Environment Variables

Create a `.env.local` file in the root directory:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/dashboard
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/dashboard

# MongoDB
MONGODB_URI=your_mongodb_connection_string

# Application
NEXT_PUBLIC_APP_URL=http://localhost:3000

# Paynow (Optional - for payment processing)
PAYNOW_INTEGRATION_ID=your_paynow_integration_id
PAYNOW_INTEGRATION_KEY=your_paynow_integration_key
PAYNOW_SANDBOX=true

# Resend (Optional - for email notifications)
RESEND_API_KEY=your_resend_api_key
```

### 4. Database Setup

Ensure your MongoDB instance is running and accessible. The application will automatically create the necessary collections on first use.

### 5. Seed Initial Data (Optional)

Seed subscription plans:

```bash
npm run seed:plans
```

### 6. Run Development Server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📁 Project Structure

```
thinkingmindserp/
├── src/
│   ├── app/                    # Next.js App Router pages
│   │   ├── (minds)/           # Main application routes
│   │   │   ├── dashboard/     # Dashboard page
│   │   │   ├── finance/       # Finance module
│   │   │   ├── hr/            # HR module
│   │   │   ├── inventory/     # Inventory module
│   │   │   ├── pos/           # POS module
│   │   │   └── ...
│   │   ├── api/               # API routes
│   │   └── layout.tsx         # Root layout
│   ├── _actions/              # Server actions
│   │   ├── finance.ts
│   │   ├── payroll.ts
│   │   ├── inventory-items.ts
│   │   └── ...
│   ├── components/            # Reusable components
│   ├── lib/                   # Utility functions
│   │   ├── mongodb.ts         # MongoDB connection
│   │   ├── serialize.ts       # Data serialization
│   │   └── ...
│   ├── shared-theme/          # MUI theme configuration
│   └── types/                 # TypeScript type definitions
├── public/                    # Static assets
├── scripts/                   # Utility scripts
└── package.json
```

---

## 📚 Documentation

### API Logging
See [API_LOGGING_GUIDE.md](./API_LOGGING_GUIDE.md) for details on API usage logging.

### Paynow Integration
See [PAYNOW_SETUP.md](./PAYNOW_SETUP.md) for Paynow payment gateway setup instructions.

---

## 📝 Changelog

### Version 5.0.0 (Current)

#### Security
- ✅ **Critical Security Update**: Upgraded to Next.js 15.5.7 to patch CVE-2025-55182 (RCE vulnerability)

#### Features
- 🎨 **UI Improvements**: Flattened and normalized colors across dashboard, removed gradients
- 📱 **Mobile Optimization**: Enhanced POS checkout with minimize/unminimize functionality
- 🔄 **Live Data Integration**: All modules now use real-time database connections
- 💰 **Multi-Currency**: Full support for multiple currencies with live exchange rates
- 📊 **Enhanced Analytics**: Real-time data visualization across all modules
- 🎯 **Plan-Aware Components**: UI adapts based on user subscription plan

#### Modules Updated
- ✅ **Finance**: Live cashier transactions, daily summaries, payment method analytics
- ✅ **Payroll**: Real-time payroll records, employee payments, leave requests
- ✅ **Inventory**: Live stock movements, product tracking, supplier management
- ✅ **Audit**: Comprehensive audit logs with compliance reporting
- ✅ **Helpdesk**: Live ticket management, knowledge base, user requests
- ✅ **POS**: Real-time sales processing with multiple payment methods

#### Bug Fixes
- 🔧 Fixed TypeScript type errors in finance and cashier modules
- 🔧 Resolved merge conflicts in AnalyticsTopRef and Hero components
- 🔧 Fixed payment method handling in POS orders
- 🔧 Corrected data serialization for MongoDB ObjectId and Date types

#### UI/UX
- 🎨 Replaced emoji icons with Material-UI icons throughout
- 📐 Optimized stat cards sizing and layout
- 🎨 Unified gradient colors for consistency
- 📱 Improved mobile responsiveness

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Commit your changes** (`git commit -m 'Add some amazing feature'`)
4. **Push to the branch** (`git push origin feature/amazing-feature`)
5. **Open a Pull Request**

### Development Guidelines

- Follow TypeScript best practices
- Use meaningful commit messages
- Write clean, maintainable code
- Test your changes thoroughly
- Update documentation as needed

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🆘 Support

### Getting Help

- 📧 **Email**: support@thinkingminds.co.zw
- 🌐 **Website**: [https://thinkingminds.co.zw](https://thinkingminds.co.zw)
- 🐛 **Issues**: [GitHub Issues](https://github.com/thinking-mindy/thinkingmindserp/issues)

### Demo

- 🚀 **Live Demo**: [https://thinking-minds-demo.vercel.app](https://thinking-minds-demo.vercel.app)

---

## 🙏 Acknowledgments

- Built with ❤️ by [Thinking Minds](https://thinkingminds.co.zw)
- Powered by [Next.js](https://nextjs.org/), [React](https://reactjs.org/), and [Material-UI](https://mui.com/)

---

<div align="center">

**Made with ❤️ by Thinking Minds**

[Website](https://thinkingminds.co.zw) • [GitHub](https://github.com/thinking-mindy/thinkingmindserp) • [Documentation](#-documentation)

</div>
