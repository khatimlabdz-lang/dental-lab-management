# Setup Guide - Dental Lab Management System

## Prerequisites
- Node.js v16+
- Docker & Docker Compose
- PostgreSQL v12+ (if not using Docker)
- Redis v6+ (if not using Docker)

## Installation

### 1. Clone Repository
```bash
git clone https://github.com/khatimlabdz-lang/dental-lab-management.git
cd dental-lab-management
```

### 2. Backend Setup
```bash
cd backend
npm install
cp .env.example .env
npm run migrate
npm run dev
```

### 3. Frontend Setup
```bash
cd frontend
npm install
cp .env.example .env
npm start
```

### 4. Docker Compose (Recommended)
```bash
cp backend/.env.example backend/.env
cp frontend/.env.example frontend/.env
docker-compose up -d
```

## Environment Configuration

### Backend `.env`
- `DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USER`, `DB_PASSWORD`
- `REDIS_URL`
- `JWT_SECRET`
- `MINIO_ENDPOINT`, `MINIO_ROOT_USER`, `MINIO_ROOT_PASSWORD`

### Frontend `.env`
- `REACT_APP_API_URL`
- `REACT_APP_ENV`

## Verification

```bash
# Backend health check
curl http://localhost:3000/api/v1/health

# Frontend
http://localhost:3001

# Database
docker exec -it dental-lab-db psql -U postgres -d dental_lab -c "\dt"
```

## Troubleshooting

### Port Already in Use
```bash
lsof -i :3000
lsof -i :3001
kill -9 <PID>
```

### Database Connection Error
```bash
docker-compose logs postgres
docker-compose restart postgres
```

## Next Steps
1. Create admin user
2. Import sample data
3. Configure integrations (3Shape, Exocad, WhatsApp)
4. Run tests
