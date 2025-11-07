# freelanceX Setup Guide

## Prerequisites
- Node.js (v16 or higher)
- MongoDB
- Git

## Quick Start

### 1. Clone & Install
```bash
git clone <repository-url>
cd freelanceX-main
```

### 2. Backend Setup
```bash
cd server
npm install
cp .env..example .env
# Edit .env with your MongoDB URL and other configs
npm start
```

### 3. Frontend Setup
```bash
cd ../client
npm install
npm run dev
```

### 4. Access Application
- Frontend: http://localhost:3000
- Backend: http://localhost:8747 (or your configured port)

## Environment Variables

### Server (.env)
```
DATABASE_URL="mongodb://localhost:27017/freelancex"
JWT_SECRET="your-jwt-secret"
STRIPE_SECRET_KEY="your-stripe-secret"
CLOUDINARY_CLOUD_NAME="your-cloudinary-name"
CLOUDINARY_API_KEY="your-cloudinary-key"
CLOUDINARY_API_SECRET="your-cloudinary-secret"
```

### Client (.env.local)
```
NEXT_PUBLIC_SERVER_URL="http://localhost:8747"
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY="your-stripe-publishable-key"
```

## Database Setup
```bash
cd server
npx prisma generate
npx prisma db push
npx prisma db seed
```

## Troubleshooting
- If CookiesProvider error: Already fixed in _app.jsx
- If MongoDB connection fails: Check DATABASE_URL in server/.env
- If Stripe errors: Add valid Stripe keys to environment variables