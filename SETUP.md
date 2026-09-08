# 🚀 Environment Setup Guide

## Quick Start

This guide walks through setting up your development environment for the Health Dashboard Saudi Arabia project.

### Prerequisites
- Node.js 18+
- Docker & Docker Compose
- MongoDB 7+
- Git

## Step 1: Clone Repository

```bash
git clone https://github.com/pinssfinss-gif/interactive-dashboard.git
cd interactive-dashboard
```

## Step 2: Environment Configuration

### Backend Setup

```bash
cd backend

# Copy environment template
cp .env.example .env

# Edit .env with your configuration
nano .env  # or your preferred editor

# Install dependencies
npm install
```

**Key configurations to update:**
- `MONGO_URI`: Database connection string
- `JWT_SECRET`: Change from default value
- `CORS_ORIGIN`: Frontend URL for local development
- Email settings (optional)

### Frontend Setup

```bash
cd ../frontend

# Copy environment template
cp .env.example .env

# Edit .env with your configuration
nano .env  # or your preferred editor

# Install dependencies
npm install
```

**Key configurations to update:**
- `VITE_API_URL`: Backend API URL
- Map configuration (optional)

## Step 3: Start Development Environment

### Option A: Using Docker Compose (Recommended)

```bash
# From project root
docker-compose up

# Access:
# Frontend: http://localhost:3000
# Backend:  http://localhost:5000
# MongoDB:  mongodb://localhost:27017
```

### Option B: Manual Setup

**Terminal 1 - MongoDB:**
```bash
mongod
# or use Docker
docker run -d -p 27017:27017 --name mongodb mongo:7
```

**Terminal 2 - Backend:**
```bash
cd backend
npm run dev
```

**Terminal 3 - Frontend:**
```bash
cd frontend
npm run dev
```

## Step 4: Verify Installation

### Check Backend
```bash
curl http://localhost:5000/api/health
# Should return: { "status": "ok" }
```

### Check Frontend
Open browser to `http://localhost:3000`

## Demo Login Credentials

| Role | Email | Password |
|------|-------|----------|
| Public Health Officer | officer@health.gov.sa | Officer123! |
| Facility Manager | manager@hospital.sa | Manager123! |
| Patient | patient@email.sa | Patient123! |

## Environment Variables Reference

### Backend (.env)

```env
# Server
PORT=5000
NODE_ENV=development

# Database
MONGO_URI=mongodb://localhost:27017/health-dashboard

# Security
JWT_SECRET=your_secret_key
JWT_EXPIRE=7d

# CORS
CORS_ORIGIN=http://localhost:3000

# Logging
LOG_LEVEL=debug
```

### Frontend (.env)

```env
# API
VITE_API_URL=http://localhost:5000/api

# App
VITE_APP_NAME=Health Dashboard Saudi Arabia

# Localization
VITE_DEFAULT_LANGUAGE=en
VITE_SUPPORTED_LANGUAGES=en,ar
```

## Troubleshooting

### MongoDB Connection Error
```bash
# Check MongoDB is running
mongosh

# If using Docker
docker logs mongodb
```

### Port Already in Use
```bash
# Find process using port 5000
lsof -i :5000

# Kill process
kill -9 <PID>
```

### Dependencies Issues
```bash
# Clean install
rm -rf node_modules package-lock.json
npm install
```

## Next Steps

1. Read the main [README.md](README.md)
2. Check the [API Documentation](docs/API.md)
3. Review [Contributing Guidelines](CONTRIBUTING.md)
4. Join the development team!

---

**Need help?** Check GitHub Issues or contact the team.
