# HRMS - Human Resource Management System

A comprehensive, production-ready HRMS built with Next.js, React, and PostgreSQL. This system provides complete HR functionality including employee management, attendance tracking, task management, leave management, and analytics.

## 🚀 Features

### Core HR
- **Employee Management**: Complete employee profiles, org chart, departments
- **Authentication & RBAC**: Role-based access control with NextAuth.js
- **Dashboard**: Personalized dashboards for different user roles

### Attendance & Time Tracking
- **Punch In/Out**: GPS-enabled attendance tracking
- **Timesheets**: Daily, weekly, monthly timesheet views
- **Attendance Rules**: Configurable shift times, grace periods, half-day thresholds

### Task Management
- **Task Assignment**: Assign tasks to individuals, teams, or departments
- **Sub-tasks**: Employees can create sub-tasks for assigned tasks
- **Kanban Board**: Drag-and-drop task management
- **Progress Tracking**: Automated progress calculation with weighted sub-tasks

### Analytics & Efficiency
- **Daily Activity Tracking**: Work, family, health, travel time logging
- **Efficiency Metrics**: Automated efficiency calculation and categorization
- **Charts & Reports**: Visual analytics with Chart.js/Recharts

### Leave Management
- **Leave Types**: Configurable leave types with rules
- **Approval Workflow**: Multi-level approval process
- **Leave Balance**: Automatic accrual and balance tracking

### Communication
- **Notices**: Rich text notices with role/department targeting
- **Notifications**: In-app and email notifications
- **Birthdays & Anniversaries**: Automated celebration reminders

### Additional Features
- **OKRs/KPIs**: Goal setting and performance tracking
- **Payroll**: Lightweight payroll with attendance integration
- **Reports & Exports**: CSV/PDF export functionality
- **Audit Logging**: Complete audit trail for all actions

## 🛠️ Tech Stack

- **Frontend**: Next.js 15, React 19, TailwindCSS
- **Backend**: Next.js API Routes, Node.js
- **Database**: PostgreSQL with Prisma ORM
- **Authentication**: NextAuth.js with JWT
- **UI Components**: Radix UI + shadcn/ui
- **Charts**: Chart.js, Recharts
- **Drag & Drop**: @hello-pangea/dnd
- **Forms**: React Hook Form + Zod validation
- **Styling**: TailwindCSS with class-variance-authority

## 📋 Prerequisites

- Node.js 18+ 
- PostgreSQL 14+
- npm or yarn

## 🚀 Quick Start

### 1. Clone and Install

```bash
git clone <repository-url>
cd hrms
npm install
```

### 2. Environment Setup

Copy the environment template and configure your variables:

```bash
cp env.template .env.local
```

Update `.env.local` with your configuration:

```env
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/hrms_db"

# NextAuth.js
NEXTAUTH_SECRET="your-secret-key-here"
NEXTAUTH_URL="http://localhost:3000"

# Email Configuration (optional)
SMTP_HOST="smtp.gmail.com"
SMTP_PORT="587"
SMTP_USER="your-email@gmail.com"
SMTP_PASS="your-app-password"
```

### 3. Database Setup

```bash
# Generate Prisma client
npm run db:generate

# Push schema to database
npm run db:push

# Seed with sample data
npm run db:seed
```

### 4. Start Development Server

```bash
npm run dev
```

Visit [http://localhost:3000](http://localhost:3000) to access the application.

## 👥 Demo Credentials

### Super Admin
- **Email**: admin@hrms.com
- **Password**: admin123

### HOD (Head of Department)
- **Email**: hod@hrms.com
- **Password**: employee123

### Team Leader
- **Email**: teamlead@hrms.com
- **Password**: employee123

### Employee
- **Email**: employee@hrms.com
- **Password**: employee123

## 📁 Project Structure

```
hrms/
├── app/                          # Next.js App Router
│   ├── (dashboard)/             # Protected dashboard routes
│   ├── api/                     # API routes
│   ├── auth/                    # Authentication pages
│   └── globals.css              # Global styles
├── components/                   # React components
│   ├── ui/                      # Base UI components
│   ├── layout/                  # Layout components
│   ├── attendance/              # Attendance components
│   ├── tasks/                   # Task management components
│   └── ...                      # Feature-specific components
├── lib/                         # Utility libraries
│   ├── auth.ts                  # Authentication config
│   ├── db.ts                    # Database connection
│   └── utils.ts                 # Utility functions
├── prisma/                      # Database schema and migrations
│   ├── schema.prisma            # Database schema
│   └── seed.ts                  # Database seeding
└── types/                       # TypeScript type definitions
```

## 🔧 Available Scripts

```bash
# Development
npm run dev              # Start development server
npm run build            # Build for production
npm run start            # Start production server

# Database
npm run db:generate      # Generate Prisma client
npm run db:push          # Push schema to database
npm run db:migrate       # Run database migrations
npm run db:studio        # Open Prisma Studio
npm run db:seed          # Seed database with sample data

# Testing
npm run test             # Run tests
npm run test:watch       # Run tests in watch mode

# Linting
npm run lint             # Run ESLint
```

## 🔐 Role-Based Access Control

The system implements comprehensive RBAC with the following roles:

- **Super Admin**: Full system access
- **Admin**: HR management, reports, system configuration
- **HOD**: Department management, team oversight
- **Team Leader**: Team management, task assignment
- **Employee**: Personal data, tasks, attendance

## 📊 Key Features Deep Dive

### Attendance System
- GPS-based punch in/out
- IP and device tracking
- Configurable work hours and grace periods
- Automatic status calculation (present, late, half-day)

### Task Management
- Hierarchical task structure with sub-tasks
- Weighted progress calculation
- Kanban board with drag-and-drop
- Comments and file attachments

### Efficiency Analytics
- Daily activity logging (work, family, health, travel)
- Automatic efficiency calculation
- Categorization (Workaholic, Balanced, Family/Friends)
- Weekly/monthly trend analysis

### Leave Management
- Multiple leave types with different rules
- Automatic balance calculation
- Multi-level approval workflow
- Calendar integration

## 🚀 Deployment

### Vercel (Recommended)

1. Push your code to GitHub
2. Connect your repository to Vercel
3. Configure environment variables
4. Deploy

### Docker

```bash
# Build image
docker build -t hrms .

# Run container
docker run -p 3000:3000 hrms
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

For support, email support@hrms.com or create an issue in the repository.

## 🗺️ Roadmap

- [ ] Mobile PWA with offline support
- [ ] Advanced reporting and analytics
- [ ] Integration with external HR systems
- [ ] Biometric device integration
- [ ] Advanced workflow automation
- [ ] Multi-language support
