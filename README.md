# XMeals - Food Delivery Platform

XMeals is a comprehensive food delivery platform built with modern web technologies. This repository contains multiple applications that work together to provide a complete ecosystem for customers, delivery partners, vendors, and administrators.

---

## 📦 Applications Overview

### 1. **QA Backend** 
**Location:** `./QA Backend/backend/`

The core backend server for the XMeals platform built with Node.js and Express.

**Key Features:**
- RESTful API endpoints
- Order management
- Payment processing (Razorpay integration)
- Wallet management
- Google Maps integration
- WhatsApp notifications
- Real-time order listeners

**Tech Stack:**
- Node.js
- Express.js
- Supabase (Database & Authentication)
- Razorpay (Payment Gateway)
- Axios (HTTP Client)
- dotenv (Environment Configuration)

**Scripts:**
- `npm run dev` - Start development server with nodemon
- `npm start` - Start production server

---

### 2. **Admin Dashboard** 
**Location:** `./xmeals-admin-react-pwa/`

Admin panel for managing the XMeals platform with analytics and control features.

**Key Features:**
- Dashboard analytics with charts
- Order management and monitoring
- Vendor management
- Admin controls and settings
- PDF export functionality (jsPDF)
- File management (FileSaver)
- Google Maps integration for delivery tracking
- Real-time data updates

**Tech Stack:**
- React 19
- Vite (Build tool)
- Tailwind CSS
- Supabase (Database)
- Chart.js (Analytics)
- Google Maps API
- date-fns (Date manipulation)

**Scripts:**
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

---

### 3. **Delivery Partner App** 
**Location:** `./xmeals-dp-react-pwa/`

Mobile-first Progressive Web App for delivery partners to manage deliveries and track orders.

**Key Features:**
- Order acceptance and delivery tracking
- Real-time location updates
- Calendar view for scheduling
- Delivery status management
- Performance metrics
- Responsive PWA design

**Tech Stack:**
- React 19
- Vite (Build tool)
- Tailwind CSS
- Supabase (Database)
- HeadlessUI (UI Components)
- React Calendar
- date-fns (Date manipulation)

**Scripts:**
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

---

### 4. **User App** 
**Location:** `./xmeals-user-react-pwa/`

Customer-facing Progressive Web App for browsing restaurants, placing orders, and managing payments.

**Key Features:**
- Browse restaurants and menus
- Order placement and tracking
- Payment processing (Razorpay)
- Wallet management
- User profiles and preferences
- Real-time order status
- Push notifications support
- Location-based services (Leaflet Maps)
- Firebase integration

**Tech Stack:**
- React
- Vite (Build tool)
- Tailwind CSS
- Supabase (Database)
- Firebase (Alternative auth/messaging)
- Razorpay (Payment Processing)
- Leaflet (Open-source mapping)
- Framer Motion (Animations)
- Lucide React (Icons)

**Scripts:**
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

---

### 5. **Vendor App** 
**Location:** `./xmeals-vendor-react-pwa/frontend/`

Progressive Web App for restaurant vendors to manage their menu, orders, and delivery operations.

**Key Features:**
- Menu management
- Order management and fulfillment
- Delivery coordination
- Performance analytics
- Date picker for scheduling
- Material-UI components for professional interface

**Tech Stack:**
- React
- Vite (Build tool)
- Tailwind CSS
- Material-UI (MUI) Components
- Supabase (Database)
- Google Maps API
- Emotion (CSS-in-JS)
- date-fns (Date manipulation)

**Scripts:**
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint
- `npm run preview` - Preview production build

---

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│                  XMeals Ecosystem                        │
├─────────────────────────────────────────────────────────┤
│                                                           │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐   │
│  │ User App     │  │ Vendor App   │  │ Admin App    │   │
│  │ (PWA)        │  │ (PWA)        │  │ (PWA)        │   │
│  └──────┬───────┘  └──────┬───────┘  └──────┬───────┘   │
│         │                 │                 │            │
│         └─────────────────┼─────────────────┘            │
│                           │                              │
│  ┌──────────────────────────────────────────────┐       │
│  │   QA Backend (Node.js/Express)               │       │
│  │  - REST APIs                                 │       │
│  │  - Payment Processing (Razorpay)            │       │
│  │  - Order Management                         │       │
│  │  - Wallet Management                        │       │
│  └──────────────┬───────────────────────────────┘       │
│                 │                                        │
│         ┌───────┴──────────┐                            │
│         │                  │                            │
│    ┌────▼────┐        ┌────▼────┐                      │
│    │ Supabase │        │ Razorpay │                     │
│    │ (DB)     │        │ (Payment)│                     │
│    └──────────┘        └──────────┘                     │
│                                                           │
└─────────────────────────────────────────────────────────┘

Delivery Partner App (PWA)
  └──> Connected to Backend for order management
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- npm or yarn
- Git

### Setup Instructions

#### Backend Setup
```bash
cd "QA Backend/backend"
npm install
cp .env.example .env
# Configure your environment variables
npm run dev
```

#### Frontend Apps Setup

For each frontend app (Admin, User, Vendor, Delivery Partner):

```bash
cd <app-directory>

# e.g., cd xmeals-user-react-pwa

npm install
npm run dev
```

---

## 📋 Project Structure

```
XMeals/
├── QA Backend/
│   └── backend/
│       ├── index.js
│       ├── config/
│       ├── controllers/
│       ├── routes/
│       ├── services/
│       └── middlewares/
├── xmeals-admin-react-pwa/
│   └── src/
│       ├── pages/
│       ├── components/
│       ├── services/
│       └── utils/
├── xmeals-dp-react-pwa/
│   └── src/
│       ├── pages/
│       ├── components/
│       └── Routes/
├── xmeals-user-react-pwa/
│   ├── backend/ (Embedded)
│   └── src/
│       ├── pages/
│       ├── components/
│       ├── Apis/
│       └── context/
└── xmeals-vendor-react-pwa/
    └── frontend/
        └── src/
            ├── pages/
            ├── components/
            └── utils/
```

---

## 🔐 Environment Variables

Each application requires specific environment variables. Create `.env` files in the respective directories:

### Backend (.env)
```
SUPABASE_URL=your_supabase_url
SUPABASE_KEY=your_supabase_key
RAZORPAY_KEY_ID=your_razorpay_key
RAZORPAY_KEY_SECRET=your_razorpay_secret
PORT=5000
```

### Frontend Apps (.env)
```
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_supabase_key
VITE_RAZORPAY_KEY=your_razorpay_key
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_key
```

---

## 🛠️ Technology Stack Summary

| Category | Technology |
|----------|-----------|
| **Frontend Framework** | React 19 |
| **Build Tool** | Vite |
| **Styling** | Tailwind CSS |
| **Backend** | Node.js + Express |
| **Database** | Supabase (PostgreSQL) |
| **Authentication** | Supabase Auth / Firebase |
| **Payments** | Razorpay |
| **Mapping** | Google Maps API / Leaflet |
| **State Management** | React Context |
| **HTTP Client** | Axios |

---

## 📱 PWA Features

All frontend applications are built as Progressive Web Apps with:
- Push notifications
- App-like experience
- Service Workers
- Responsive design

---

## 📚 API Documentation

For detailed API documentation, refer to the `QA Backend` directory which contains:
- Order routes
- Payment routes
- Wallet routes
- Google Maps routes
- Razorpay webhook routes
- WhatsApp notification routes

---

## 🤝 Development Workflow

1. Clone the repository
2. Install dependencies for each app
3. Configure environment variables
4. Start the backend server
5. Start frontend apps in development mode
6. Make changes and test locally
7. Build for production when ready

---

## 📝 Notes

- All frontend apps use Vite for fast development and optimized builds
- The backend serves as a single Point of Entry for all frontend applications
- Supabase is used as the primary database and authentication provider
- Razorpay handles payment processing for the user app
- WhatsApp integration for order notifications
- Real-time order tracking with Google Maps integration

---

## 📄 License

All rights reserved - XMeals Platform

---

## 👥 Support

For issues, questions, or contributions, please refer to the project documentation or contact the development team.

---

**Last Updated:** February 2026
