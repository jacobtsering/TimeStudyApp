# Time Study Application - Package.json

This file needs to be updated to include the scripts for running the application and the dependencies required.

```json
{
  "name": "time-study-app",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "next lint",
    "seed": "node scripts/seed.js"
  },
  "dependencies": {
    "@hookform/resolvers": "^3.3.4",
    "@prisma/client": "^6.5.0",
    "next": "14.1.0",
    "next-auth": "^4.24.5",
    "react": "^18.2.0",
    "react-barcode-reader": "^0.0.2",
    "react-dom": "^18.2.0",
    "react-hook-form": "^7.50.1",
    "react-toastify": "^10.0.4",
    "xlsx": "^0.18.5",
    "zod": "^3.22.4"
  },
  "devDependencies": {
    "@types/node": "^20.11.19",
    "@types/react": "^18.2.57",
    "@types/react-dom": "^18.2.19",
    "autoprefixer": "^10.4.17",
    "eslint": "^8.56.0",
    "eslint-config-next": "14.1.0",
    "postcss": "^8.4.35",
    "prisma": "^6.5.0",
    "tailwindcss": "^3.4.1",
    "typescript": "^5.3.3"
  }
}
```
