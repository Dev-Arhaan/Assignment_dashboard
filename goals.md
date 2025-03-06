# Fullstack Developer Intern Assignment  
### Atomic Goals Breakdown

This document breaks down the assignment into **small, manageable goals**, helping you systematically build the application and track your progress.

---

## 1. Project Setup & Initial Configuration

### Backend Setup (Node.js, Express, MongoDB)
- [x] Initialize Node.js project: `npm init -y`
- [x] Install Express.js: `npm install express`
- [x] Install Mongoose: `npm install mongoose`
- [ ] Create `server.js` to set up basic Express server
- [ ] Connect to MongoDB (local/Atlas)
- [ ] Create `.gitignore` for `node_modules`, `.env`, etc.

### Frontend Setup (Next.js, Tailwind CSS, ShadcnUI)
- [x] Create Next.js project: `npx create-next-app@latest frontend`
- [x] Install Tailwind CSS & configure
- [ ] Install ShadcnUI: `npx shadcn-ui@latest init`
- [ ] Add required ShadcnUI components:  
    `npx shadcn-ui@latest add button table dialog input`

### Project Structure
- [x] Create project root: `fullstack-dashboard`
- [x] Move `frontend` into root
- [x] Create `backend` folder for server files
- [ ] Setup proper folder structure inside frontend & backend

### Environment Variables Setup
- [ ] Install dotenv: `npm install dotenv`
- [ ] Create `backend/.env` and define variables:
    - PORT
    - MONGODB_URI
    - JWT_SECRET
- [ ] Load `.env` in `server.js`
- [ ] Prepare frontend for env variables (API Base URL)

---

## 2. Authentication (JWT-based)

### Backend - User Model
- [ ] Create `User` model (`backend/models/User.js`)
- [ ] Fields: `username`, `email`, `password`
- [ ] Use `bcryptjs` for password hashing: `npm install bcryptjs`

### Backend - Authentication Controllers
- [ ] Create `backend/controllers/authController.js`
- [ ] Implement **Signup**:
    - Validate inputs
    - Check if email exists
    - Hash password
    - Save user
    - Return success response
- [ ] Implement **Login**:
    - Validate inputs
    - Find user
    - Compare passwords (bcryptjs)
    - Generate JWT (install `jsonwebtoken`)
    - Return JWT in response

### Backend - Authentication Routes
- [ ] Create `backend/routes/authRoutes.js`
- [ ] Define `/signup` and `/login` routes
- [ ] Add routes to `server.js`

### Frontend - Auth Pages
- [ ] Create:
    - `frontend/pages/auth/login.js`
    - `frontend/pages/auth/signup.js`
- [ ] Design forms using ShadcnUI (Inputs, Buttons)
- [ ] Add submission logic using `fetch`
- [ ] Handle success/error responses
- [ ] Store JWT in `localStorage`/`cookies`

### Frontend - Protected Routes
- [ ] Create `ProtectedRoute` HOC/component
- [ ] Check JWT in `localStorage`
- [ ] Redirect to `/auth/login` if invalid/absent
- [ ] Wrap dashboard with `ProtectedRoute`

### Token Expiry Handling
- [ ] Add `expiresIn` when generating JWT
- [ ] Handle expiry in `ProtectedRoute`
- [ ] Clear expired token & redirect to login
- [ ] Add **Logout** button in dashboard

---

## 3. Dashboard & Google Sheets Integration

### Google Sheets API Setup
- [ ] Enable Sheets API in Google Cloud
- [ ] Create credentials (Service Account)
- [ ] Install `googleapis`: `npm install googleapis`
- [ ] Setup Google Sheets client & auth
- [ ] Store Sheet ID in `.env`

### Backend - Fetch Google Sheet Data
- [ ] Create `backend/controllers/googleSheetController.js`
- [ ] Fetch data from Sheets API & format as JSON
- [ ] Return data as response

### Backend - Sheets Data Route
- [ ] Create `backend/routes/googleSheetRoutes.js`
- [ ] Add `/api/googlesheet/data`
- [ ] Protect with JWT auth middleware

### Frontend - Dashboard UI
- [ ] Create `pages/dashboard.js`
- [ ] Design layout (Header, Sidebar, Content) using Tailwind+ShadcnUI
- [ ] Add "Create Table" button with ShadcnUI Dialog

### Frontend - Create Table Dialog
- [ ] Form to enter number of columns
- [ ] Dynamically generate column name inputs
- [ ] Select data type (Text/Date) for each column
- [ ] Submit table config

### Frontend - Fetch & Display Sheet Data
- [ ] On successful login or dashboard load:
    - Fetch `/api/googlesheet/data`
    - Map data to ShadcnUI Table
- [ ] Render rows/columns dynamically

### Real-time Data Reflection
- [ ] Choose one method:
    - Polling (recommended for simplicity)
    - SSE (Server-Sent Events)
    - WebSockets
- [ ] Implement selected method

---

## 4. Dynamic Column Addition (Frontend)

### UI for Adding Columns
- [ ] Add "Add Column" button
- [ ] On click, open ShadcnUI Dialog
- [ ] Inputs for column name & type
- [ ] Submit to add column (only on frontend)

### Handle Dynamic Columns
- [ ] Add new column to table state
- [ ] Save dynamic columns to `localStorage`
- [ ] Load columns from `localStorage` on dashboard load

---

## 5. Deployment & Final Steps

### Backend Deployment
- [ ] Deploy to Render/Heroku
- [ ] Add env variables in deployment platform
- [ ] Test `/api` endpoints after deployment

### Frontend Deployment
- [ ] Deploy to Vercel (GitHub integration)
- [ ] Add env variables in Vercel if needed
- [ ] Test live frontend link

### GitHub Repository
- [ ] Initialize git repo
- [ ] Commit all code
- [ ] Create & push to GitHub repo

### README.md
- [ ] Add:
    - Project description
    - Live links (Frontend, Backend)
    - GitHub link
    - Setup instructions
    - Required environment variables
    - Tech stack

### Explainer Video (Loom)
- [ ] Record 2-5 min video:
    - Introduction
    - Features demo
    - Code overview
- [ ] Add Loom link to README & submission form

### Code Quality & Final Check
- [ ] Format code (Prettier)
- [ ] Add necessary comments
- [ ] Remove unnecessary logs
- [ ] Run linter (ESLint)
- [ ] Review final submission

### Final Submission
- [ ] Submit:  
    - [ ] GitHub Repo  
    - [ ] Backend Live URL  
    - [ ] Frontend Live URL  
    - [ ] Loom Video  
- [ ] Submit before deadline: **8 PM, 8/3/2025 (Saturday)**

---

**This checklist helps track progress and ensures no step is missed. Best of luck!**
