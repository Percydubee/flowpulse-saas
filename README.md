# FLOWPULSE - Business Management SaaS Platform

A comprehensive, production-ready business management platform built with Next.js, React, TypeScript, and Node.js. FLOWPULSE integrates multiple business modules including CRM, Inventory Management, Project Management, Accounting, and more.

## 🚀 Features

### Core Modules
- **CRM**: Contact management, lead scoring, activity tracking
- **Inventory Management**: Real-time stock tracking, automated reordering, demand forecasting
- **Project Management**: Task tracking, team collaboration, Gantt charts
- **Accounting**: Journal entries, invoicing, financial reporting
- **Payroll**: Employee management, payroll processing, payslips
- **Scheduling**: Resource allocation, calendar management
- **Contracts**: Document management, e-signatures
- **Budgeting**: Budget planning, expense tracking
- **Analytics**: Business intelligence, reporting dashboards

### Technical Features
- 🔐 **Authentication**: JWT-based auth with refresh tokens
- 👥 **Role-Based Access Control**: Admin, Manager, Employee, Client roles
- 📱 **Responsive Design**: Mobile-first approach
- 🌐 **RESTful API**: Well-documented backend API
- 📊 **Real-time Updates**: Live data synchronization
- 🔄 **Offline Support**: SQLite3 for local data caching
- 🎨 **Modern UI**: Built with shadcn/ui components
- 🔔 **Notifications**: Real-time notification system

## 🛠️ Tech Stack

### Frontend
- **Framework**: Next.js 15.3.2
- **Language**: TypeScript
- **Styling**: Tailwind CSS
- **UI Components**: shadcn/ui
- **State Management**: React Hooks
- **Package Manager**: Bun

### Backend
- **Runtime**: Node.js with TypeScript
- **Framework**: Express.js
- **Database**: SQLite3 (development) / PostgreSQL (production-ready)
- **Authentication**: JWT with bcrypt
- **Logging**: Winston
- **Rate Limiting**: express-rate-limit

## 📋 Prerequisites
- Node.js 18+ or Bun 1.0+
- Git
- SQLite3

## 🚀 Quick Start

### Development Setup
1. **Clone the repository**
   ```bash
   git clone https://github.com/your-org/flowpulse.git
   cd flowpulse
   ```

2. **Install dependencies**
   ```bash
   # Install frontend dependencies
   bun install
   
   # Install backend dependencies
   cd backend
   bun install
   cd ..
   ```

3. **Set up environment variables**
   ```bash
   # Backend environment
   cp backend/.env.example backend/.env
   
   # Frontend environment (already configured)
   # Edit .env.local if needed
   ```

4. **Start development servers**
   ```bash
   # Start both frontend and backend
   ./start-dev.sh
   
   # Or start separately:
   # Backend (port 8081)
   cd backend && bun run dev
   
   # Frontend (port 3000)
   bun run dev
   ```

5. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8081
   - API Health: http://localhost:8081/health

### Demo Accounts
| Role | Email | Password |
|------|-------|----------|
| Admin | admin@flowpulse.com | admin123 |
| Manager | manager@flowpulse.com | manager123 |
| Employee | employee@flowpulse.com | employee123 |
| Client | client@flowpulse.com | client123 |

## 🏗️ Production Build

```bash
# Build for production
./build-prod.sh

# Output directories:
# - ./out/ (Frontend static files)
# - ./backend/dist/ (Backend compiled)
```

## 📁 Project Structure

```
flowpulse-saas/
├── src/                    # Frontend source code
│   ├── app/               # Next.js app directory
│   ├── components/        # React components
│   ├── lib/              # Utilities and helpers
│   └── hooks/            # Custom React hooks
├── backend/               # Backend source code
│   ├── src/
│   │   ├── controllers/  # Route controllers
│   │   ├── models/       # Data models
│   │   ├── routes/       # API routes
│   │   ├── middleware/   # Express middleware
│   │   ├── config/       # Configuration files
│   │   └── utils/        # Utility functions
│   ├── database/         # SQLite database
│   └── logs/            # Application logs
├── public/               # Static assets
└── out/                  # Production build output
```

## 🔧 Configuration

### Backend Configuration (.env)
```env
NODE_ENV=development
PORT=8081
DATABASE_PATH=./database/flowpulse.db
JWT_SECRET=your-secret-key
CORS_ORIGIN=http://localhost:3000
```

### Frontend Configuration (.env.local)
```env
NEXT_PUBLIC_API_URL=http://localhost:8081/api
NEXT_PUBLIC_APP_ENV=development
```

## 📚 API Documentation

### Authentication Endpoints
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout  
- `POST /api/auth/refresh` - Refresh access token
- `GET /api/auth/me` - Get current user

### CRM Endpoints
- `GET /api/crm/contacts` - List contacts
- `POST /api/crm/contacts` - Create contact
- `PUT /api/crm/contacts/:id` - Update contact
- `DELETE /api/crm/contacts/:id` - Delete contact

### Project Management Endpoints
- `GET /api/projects` - List projects
- `POST /api/projects` - Create project
- `GET /api/projects/:id` - Get project details
- `PUT /api/projects/:id` - Update project

### Inventory Endpoints
- `GET /api/inventory/items` - List inventory items
- `POST /api/inventory/items` - Create item
- `POST /api/inventory/transactions` - Record transaction
- `GET /api/inventory/predict-demand` - AI demand forecasting

## 🧪 Testing

```bash
# Run backend tests
cd backend && bun test

# Run frontend tests
bun test

# Run linter
bun run lint
```

## 🚀 Deployment

### Using Docker
```bash
# Build Docker image
docker build -t flowpulse .

# Run container
docker run -p 3000:3000 -p 8081:8081 flowpulse
```

### Manual Deployment
1. Build the application using `./build-prod.sh`
2. Set up a reverse proxy (nginx/Apache)
3. Configure PM2 for the backend process
4. Set up SSL certificates
5. Configure environment variables
6. Run database migrations

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with [Next.js](https://nextjs.org/)
- UI components from [shadcn/ui](https://ui.shadcn.com/)
- Icons from [Lucide](https://lucide.dev/)
- Database powered by [SQLite](https://www.sqlite.org/)