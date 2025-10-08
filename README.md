# 💰 Finance Tracking Dashboard

A modern, full-stack finance tracking application built with Next.js 15, featuring comprehensive invoice management, customer tracking, and financial analytics.

![Next.js](https://img.shields.io/badge/Next.js-15.6.0-black?style=flat-square&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5.7.3-blue?style=flat-square&logo=typescript)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue?style=flat-square&logo=postgresql)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4.17-38B2AC?style=flat-square&logo=tailwind-css)

## 🚀 Features

### 📊 Dashboard Analytics
- **Revenue Overview**: Real-time revenue tracking with visual charts
- **Financial Metrics**: Key performance indicators and financial summaries
- **Latest Invoices**: Quick view of recent invoice activity

### 📄 Invoice Management
- **Create Invoices**: Add new invoices with customer selection and validation
- **Edit Invoices**: Update existing invoice details with real-time validation
- **Delete Invoices**: Remove invoices with confirmation
- **Invoice Search**: Find invoices by customer name or invoice details
- **Pagination**: Navigate through large invoice lists efficiently
- **Status Tracking**: Monitor payment status (Pending/Paid)

### 👥 Customer Management
- **Customer Database**: Comprehensive customer information storage
- **Customer Profiles**: View customer details and invoice history

### 🔐 Authentication & Security
- **NextAuth Integration**: Secure authentication with credentials provider
- **Protected Routes**: Middleware-based route protection
- **Password Hashing**: Secure password storage with bcrypt
- **Session Management**: Persistent user sessions

### 🎨 Modern UI/UX
- **Responsive Design**: Mobile-first approach with Tailwind CSS
- **Loading States**: Skeleton loaders for improved user experience
- **Error Handling**: Graceful error boundaries and 404 pages
- **Form Validation**: Real-time client and server-side validation
- **Accessibility**: ARIA compliant components

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 15.6.0 with App Router
- **Language**: TypeScript 5.7.3
- **Styling**: Tailwind CSS 3.4.17
- **Icons**: Heroicons React
- **Build Tool**: Turbopack (development)

### Backend
- **Runtime**: Node.js with Edge Runtime support
- **Database**: PostgreSQL (hosted on Supabase)
- **ORM**: Direct SQL queries with `postgres` library
- **Authentication**: NextAuth v5 (beta)
- **Validation**: Zod schema validation

### Development Tools
- **Package Manager**: pnpm
- **Linting**: ESLint with Next.js configuration
- **Type Checking**: TypeScript strict mode
- **Development**: Hot reload with Turbopack

## 📁 Project Structure

```
app/
├── dashboard/              # Main dashboard routes
│   ├── layout.tsx         # Dashboard layout with navigation
│   ├── overview/          # Revenue analytics and charts
│   ├── invoices/          # Invoice management
│   │   ├── page.tsx       # Invoice list with search & pagination
│   │   ├── create/        # Create new invoice
│   │   └── [id]/edit/     # Edit existing invoice
│   └── customers/         # Customer management
├── lib/                   # Utility functions and data
│   ├── actions.ts         # Server actions for CRUD operations
│   ├── data.ts           # Database queries and data fetching
│   ├── definitions.ts     # TypeScript type definitions
│   └── utils.ts          # Helper functions
├── ui/                    # Reusable UI components
│   ├── dashboard/         # Dashboard-specific components
│   ├── invoices/          # Invoice-related components
│   └── customers/         # Customer-related components
└── layout.tsx            # Root layout with global styles
```

## 🚦 Getting Started

### Prerequisites
- Node.js 18+ 
- pnpm (recommended) or npm
- PostgreSQL database (Supabase account recommended)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/red445992/Finance-Tracking.git
   cd nextjs-dashboard
   ```

2. **Install dependencies**
   ```bash
   pnpm install
   ```

3. **Environment Setup**
   
   Create a `.env.local` file in the root directory:
   ```env
   # Database Configuration
   POSTGRES_URL="your_postgres_connection_string"
   POSTGRES_URL_NON_POOLING="your_postgres_direct_connection"
   POSTGRES_USER="your_username"
   POSTGRES_HOST="your_host"
   POSTGRES_PASSWORD="your_password"
   POSTGRES_DATABASE="your_database"
   
   # Supabase Configuration (if using Supabase)
   SUPABASE_URL="your_supabase_url"
   SUPABASE_JWT_SECRET="your_jwt_secret"
   NEXT_PUBLIC_SUPABASE_ANON_KEY="your_anon_key"
   SUPABASE_SERVICE_ROLE_KEY="your_service_role_key"
   
   # NextAuth Configuration
   NEXTAUTH_SECRET="your_super_secret_key"
   NEXTAUTH_URL="http://localhost:3000"
   AUTH_SECRET="your_auth_secret"
   ```

4. **Database Setup**
   
   Run the database seed script to populate initial data:
   ```bash
   # The app includes a seeding route at /seed
   # Visit http://localhost:3000/seed after starting the dev server
   ```

5. **Start Development Server**
   ```bash
   pnpm dev
   ```
   
   Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📊 Database Schema

The application uses the following main tables:

- **users**: User authentication and profiles
- **customers**: Customer information and contact details
- **invoices**: Invoice records with status and amounts
- **revenue**: Monthly revenue tracking data

## 🔒 Authentication

The app uses NextAuth v5 with:
- **Credentials Provider**: Email/password authentication
- **Middleware Protection**: Automatic route protection
- **Session Management**: Persistent login sessions
- **Password Security**: Bcrypt hashing

### Default Login Credentials
Check the database seed data for test user credentials.

## 🎯 Key Features Implemented

### Server Actions
- ✅ **Invoice CRUD**: Create, read, update, delete operations
- ✅ **Form Validation**: Zod schema validation with error handling
- ✅ **Optimistic Updates**: Immediate UI feedback
- ✅ **Error Boundaries**: Graceful error handling

### User Interface
- ✅ **Search & Filter**: Real-time invoice search
- ✅ **Pagination**: Efficient data navigation
- ✅ **Loading States**: Skeleton components during data fetch
- ✅ **Responsive Design**: Mobile-optimized interface
- ✅ **Form Validation**: Real-time field validation with error messages

### Performance Optimizations
- ✅ **Server Components**: Reduced client-side JavaScript
- ✅ **Streaming**: Progressive page loading
- ✅ **Static Generation**: Optimized build output
- ✅ **Database Queries**: Efficient PostgreSQL queries

## 📈 Performance & SEO

- **Core Web Vitals**: Optimized for Google's performance metrics
- **Metadata Management**: Dynamic meta tags for SEO
- **Image Optimization**: Next.js automatic image optimization
- **Bundle Optimization**: Tree shaking and code splitting

## 🚀 Deployment

### Vercel (Recommended)
1. Push your code to GitHub
2. Connect your repository to Vercel
3. Configure environment variables in Vercel dashboard
4. Deploy automatically on every push

### Other Platforms
The app can be deployed on any platform supporting Node.js:
- Railway
- Render
- AWS
- Google Cloud Platform

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built following the [Next.js Learn Course](https://nextjs.org/learn)
- UI components inspired by modern dashboard designs
- Icons provided by [Heroicons](https://heroicons.com/)

## 📞 Support

If you have any questions or issues, please:
1. Check the [Issues](https://github.com/red445992/Finance-Tracking/issues) page
2. Create a new issue with detailed information
3. Contact the maintainers

---

**Happy Coding! 🎉**
