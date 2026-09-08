# 🏥 Health Dashboard Saudi Arabia

A comprehensive health monitoring dashboard for tracking public health metrics, disease surveillance, and healthcare facility management in Saudi Arabia.

## Features

### 📊 Public Health Officer Dashboard
- Real-time disease prevalence monitoring
- Non-communicable disease (NCD) tracking: Diabetes (17.7%), Hypertension (25%)
- Communicable disease surveillance
- Emerging disease alerts (MERS-CoV)
- Vaccination coverage tracking
- Regional health data visualization
- Hajj health monitoring

### 🏥 Facility Manager Dashboard (Phase 2)
- Hospital and clinic management
- Bed availability tracking
- Staff management (doctors, nurses)
- Service catalog
- Telemedicine integration

### 👤 Patient Portal (Phase 2)
- Personal health records
- Vaccination status
- Appointment scheduling
- Medical history
- Lab results

### 🕌 Hajj Health Monitoring (Phase 3)
- Real-time pilgrim tracking
- Health alert system
- Disease case monitoring
- Medical service coordination

## Architecture

```
health-dashboard-saudi/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── database/
│   │   ├── models/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── routes/
│   │   └── server.ts
│   ├── Dockerfile
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── contexts/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── Dockerfile
│   └── package.json
├── data/
│   └── mockData.ts
└── docker-compose.yml
```

## Tech Stack

### Backend
- **Runtime**: Node.js 18+
- **Framework**: Express.js
- **Database**: MongoDB
- **Language**: TypeScript
- **Authentication**: JWT
- **API**: RESTful

### Frontend
- **Framework**: React 18
- **Language**: TypeScript
- **UI Library**: Material-UI (MUI)
- **Charts**: Recharts
- **Maps**: Leaflet
- **Routing**: React Router v6
- **State Management**: Zustand
- **Build Tool**: Vite

## Getting Started

### Prerequisites
- Node.js 18+
- Docker & Docker Compose (optional)
- MongoDB 7+

### Quick Start with Docker

```bash
# Clone repository
git clone https://github.com/fahmisetiawan109-hue/health-dashboard-saudi.git
cd health-dashboard-saudi

# Start services
docker-compose up

# Access application
# Frontend: http://localhost:3000
# Backend: http://localhost:5000
```

### Manual Setup

#### Backend
```bash
cd backend
npm install
cp .env.example .env
# Edit .env with your configuration
npm run dev
```

#### Frontend
```bash
cd frontend
npm install
cp .env.example .env
npm run dev
```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `POST /api/auth/logout` - Logout user

### Diseases
- `GET /api/diseases` - Get all diseases
- `GET /api/diseases/:id` - Get disease by ID
- `GET /api/diseases/region/:province` - Get diseases by region
- `GET /api/diseases/statistics` - Get disease statistics

### Vaccinations
- `GET /api/vaccinations` - Get vaccination data
- `GET /api/vaccinations/coverage` - Get vaccination coverage
- `GET /api/vaccinations/region/:province` - Get regional vaccination data

### Facilities
- `GET /api/facilities` - Get all health facilities
- `GET /api/facilities/:id` - Get facility by ID
- `GET /api/facilities/province/:province` - Get facilities by province
- `GET /api/facilities/statistics` - Get facility statistics

### Hajj
- `GET /api/hajj/statistics` - Get Hajj statistics
- `GET /api/hajj/alerts` - Get health alerts
- `GET /api/hajj/disease-cases` - Get disease cases during Hajj

## Demo Users

| Role | Email | Password |
|------|-------|----------|
| Public Health Officer | officer@health.gov.sa | Officer123! |
| Facility Manager | manager@hospital.sa | Manager123! |
| Patient | patient@email.sa | Patient123! |

## Key Metrics

### Non-Communicable Diseases (73% of mortality)
- Diabetes: 17.7%
- Hypertension: 25%
- Obesity: 28.7%
- Dyslipidemia: 32%

### Communicable Diseases (12% of mortality)
- COVID-19
- MERS-CoV: 2,200 cases (high mortality rate)
- Influenza

### Vaccination Coverage
- Meningococcal: 97%
- Polio: 95%
- Yellow Fever: 90%
- Influenza: 88%
- COVID-19: 85%

### Healthcare Infrastructure
- Total Hospitals: 499
- Total Clinics: 2,500
- Doctors: 113,300
- Nurses: 213,110
- Beds: 85,000

### Hajj Health (2024)
- Total Pilgrims: 1.3 Million
- Medical Services Provided: 1.3 Million
- Vaccinations Required: Meningococcal, Polio, Yellow Fever, COVID-19

## Development Roadmap

### Phase 1: Public Health Dashboard ✅
- [x] Authentication system
- [x] Disease surveillance
- [x] Vaccination tracking
- [x] Hajj monitoring
- [x] Regional analytics

### Phase 2: Facility Manager Dashboard
- [ ] Hospital management
- [ ] Staff management
- [ ] Bed availability
- [ ] Service catalog
- [ ] Telemedicine integration

### Phase 3: Patient Portal
- [ ] Personal health records
- [ ] Appointment scheduling
- [ ] Medical history
- [ ] Lab results
- [ ] Prescription management

### Phase 4: Advanced Features
- [ ] Real-time WebSocket updates
- [ ] Mobile app
- [ ] AI-powered disease prediction
- [ ] Multilingual support (Arabic/English)
- [ ] Advanced analytics and reporting

## Environment Variables

### Backend (.env)
```
PORT=5000
NODE_ENV=development
MONGO_URI=mongodb://localhost:27017/health-dashboard
JWT_SECRET=your_jwt_secret_key
JWT_EXPIRE=7d
CORS_ORIGIN=http://localhost:3000
LOG_LEVEL=debug
```

### Frontend (.env)
```
VITE_API_URL=http://localhost:5000/api
VITE_APP_NAME=Health Dashboard Saudi Arabia
```

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

MIT License - see LICENSE file for details

## Support

For support, email fahmisetiawan109@gmail.com or open an issue on GitHub.

## Acknowledgments

- Saudi Ministry of Health
- WHO Health Guidelines
- Healthcare professionals and consultants
- Community feedback and contributions

---

**Made with ❤️ for public health in Saudi Arabia**
