# AstroWatch

A comprehensive astronomical events platform.

## Prerequisites

- Node.js (v18+)
- npm
- Docker and Docker Compose

## Local Development Setup

1. **Install Dependencies**
   ```bash
   npm install
   ```

2. **Start Infrastructure (Database, Cache, Search)**
   ```bash
   cd infra
   docker compose up -d
   cd ..
   ```

3. **Set up Environment Variables**
   Copy `infra/.env.example` to `apps/api/.env`:
   ```bash
   cp infra/.env.example apps/api/.env
   ```

4. **Initialize Database**
   ```bash
   cd apps/api
   npx prisma generate
   npx prisma db push
   npx ts-node prisma/seed.ts
   cd ../..
   ```

5. **Start the Monorepo**
   ```bash
   npm run dev
   ```
   - Frontend will be running on `http://localhost:3000`
   - API will be running on `http://localhost:4000`
