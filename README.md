# OptiCare: Optical Shop Management System

A full-stack system for an optical shop: customers browse and buy eyewear, try frames on
virtually with their webcam, book eye-test appointments with optometrists, and register
warranties. Staff manage everything from an admin panel, and doctors manage their own
appointments.

**Stack:** React + Vite · Tailwind CSS / MUI · Node.js · Express · MongoDB (Mongoose) · JWT ·
Cloudinary · Stripe / Razorpay (test mode) · Three.js + TensorFlow.js face landmarks (AR try-on)

## Apps in this repository

| Folder | What it is |
| --- | --- |
| `frontend/` | Customer site: product catalogue, purchases with payment-slip upload, appointments, warranty registration and claims, profile |
| `admin/` | Admin and doctor panel: dashboard, doctors, appointments, product and order management |
| `backend/` | Express REST API: auth (users, admin, doctors), products, purchases with approval workflow, appointments, warranty claims, try-on sessions |
| `ARTryOn/` | Webcam virtual glasses try-on, adapted from Benson Ruan's open-source [Virtual Glasses Try-on](https://github.com/bensonruan/Virtual-Glasses-Try-on) (Three.js + face-landmark detection) |

## Features

- Product catalogue with categories, search and product detail pages
- Purchases with payment-slip upload and admin approval, plus PDF and CSV export of purchase records
- Online payments with Stripe or Razorpay (test mode)
- Optometrist appointment booking; doctors see and manage their own schedule
- Warranty registration, claims and warranty statistics
- Store locator map (Leaflet)
- Virtual try-on of frames through the webcam

## Run locally

Requirements: Node.js 20+, MongoDB (local or Atlas), and a free Cloudinary account for images.

```bash
# API
cd backend
cp .env.example .env        # fill in MONGODB_URI, JWT_SECRET, Cloudinary and admin login
npm install
npm run dev                 # http://localhost:5555

# Customer site
cd ../frontend
cp .env.example .env
npm install
npm run dev

# Admin / doctor panel
cd ../admin
cp .env.example .env
npm install
npm run dev
```

Secrets live only in the local `.env` files, which are git-ignored. Each app ships an
`.env.example` that lists the variables it needs.
