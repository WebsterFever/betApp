# 🎲 Bolet — Online Bolet & Lotto Platform

Bolet is a **complete online bolet/lottery web platform**, created especially for the **Haitian community**, allowing users to play bolet online in a **simple, fast, and secure** way. The platform includes a **points system**, an **administrative dashboard**, and **full control over bets**.

---

## 🚀 Project Overview

Bolet allows users to:

- Create an account and log in  
- Buy points  
- Play different types of bolet  
- Track all bets in real time  
- View betting history (**Fich**)  
- Request payout of winnings  
- Receive credits or payments via **PIX**

It also allows administrators to:

- View all bets  
- Mark bets as **won, lost, paid, pending**  
- Manage users  
- Manage payout requests  
- Control the entire system from a central dashboard  

---

## 🧩 Supported Bet Types

The system currently supports:

- **Yon Chif** (1 number)  
- **De Chif** (2 numbers)  
- **Twa Chif** (3 numbers)  
- **Katchif** (4 numbers)  
- **Maryaj** (combination)  

Each bet type includes:

- Number(s)  
- Amount of points wagered  
- Draw location (e.g. **New York / Florida**)  
- Bet status  

---

## 🧑‍💻 Technologies Used

### Frontend
- React  
- React Router  
- Axios  
- Context API  
- CSS Modules  
- **Deployment:** Vercel  

### Backend
- Node.js  
- Express  
- Sequelize (ORM)  
- PostgreSQL  
- JWT Authentication  
- Configured CORS  
- **Deployment:** Railway / Render  

### Database
- PostgreSQL (Render)  
- Relational structure with associations between users and bets  

---

## 🔐 Authentication & Security

- Login and registration using **JWT**  
- `authenticate` middleware for protected routes  
- `adminOnly` middleware for admin routes  
- Tokens stored in **localStorage**  
- CORS configured for frontend ↔ backend communication  

---

## 💰 Points System

- Users play using points  
- Points can be purchased  
- Each bet automatically deducts points  
- Balance is always updated in real time  

---

## 📊 Bet Statuses

Each bet can have one of the following statuses:

- `pending` – waiting for result  
- `won` – winning bet  
- `lost` – losing bet  
- `paid` – prize already paid  
- `void / cancelled` – cancelled bet  

---

## 🧾 Fich — Bet History

The **Fich** page displays:

- All user bets  
- Bet types  
- Played numbers  
- Points wagered  
- Date and time  
- Current status  
- Total points wagered  

All data is returned through a **single unified backend endpoint**.

---

## 🏆 Winnings System (Claims)

When a bet is marked as **won**, the user can:

- Request winnings as **points**  
- Request payout via **PIX**  

The request is stored as a **claim**, waiting for administrator action.

---

## 👑 Admin Dashboard

### Admin — Manage Bets
- View all bets  
- Filter by type and status  
- Search by number, type, or phone  
- Update bet status in real time  

### Admin — Claims
- View payout requests  
- Credit points to users  
- Mark PIX payments as paid  
- Full control over payout history  

---

## 📡 Main API Routes

### Authentication
```http
POST /api/auth/register
POST /api/auth/login

POST /api/yonchif
POST /api/dechif
POST /api/twachif
POST /api/katchif
POST /api/maryaj
GET  /api/bets/me

GET   /api/admin/bets
PATCH /api/admin/bets/:type/:id/status
GET   /api/admin/claims
POST  /api/admin/claims/:id/credit-points
POST  /api/admin/claims/:id/mark-paid

backend/
 ├── controllers/
 ├── routes/
 ├── models/
 ├── middleware/
 ├── app.js
 └── server.js

frontend/
 ├── components/
 ├── pages/
 ├── context/
 ├── App.jsx
 └── main.jsx

new commit 