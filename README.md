# HostelSync - Modern Hostel Management System 🏢

![HostelSync Banner](frontend/src/assets/hostelsync-logo.png)

A comprehensive, full-stack web application designed to streamline and automate hostel administration, resident services, and campus communication. Built with the **MERN** stack (MongoDB, Express.js, React, Node.js), HostelSync provides role-based access for Students, Staff/Wardens, and Administrators.

---

## 👤 Author & Maintainer

Developed and maintained by **[PARIKSHIT-hub](https://github.com/PARIKSHIT-hub)**.

- **GitHub:** [@PARIKSHIT-hub](https://github.com/PARIKSHIT-hub)
- **Repository:** [Hostel_Management_System](https://github.com/PARIKSHIT-hub/Hostel_Management_System)

---

## 🚀 Features

### 👤 Role-Based Portals
- **Student Dashboard:** Manage complaints, laundry bookings, leave applications, mess feedback, gate passes, visitor logs, and room transfer requests.
- **Admin Dashboard:** Overview of hostel statistics, manage user approvals (students/staff), allocate rooms, manage notices, mess menus, and system controls.
- **Staff / Warden Portal:** Manage student leave approvals, oversee gate entry/exit logs, process complaints, and review visitor requests.

### 🛠️ Core Capabilities
- 📋 **Complaint Management System:**
  - Submit complaints with photo attachments (via Cloudinary integration).
  - Track complaint status in real time (*Pending*, *In Progress*, *Resolved*).
- 🧺 **Automated Laundry Booking:**
  - Real-time machine slot allocation and status tracking.
  - Automated background worker (`laundryAutoJob`) to clear expired slots every minute.
- 🚪 **Digital Gate Pass & Entry/Exit Tracking:**
  - Generate digital gate passes for student movement.
  - Guard/Admin interface for scanning and validating student entries and exits.
- 📝 **Leave & Absence Management:**
  - Digital leave application submission with automated email notifications.
  - Multi-tier approval workflow (Warden/Admin).
- 🍽️ **Mess Management & Ratings:**
  - Weekly menu display for all meals (Breakfast, Lunch, Snacks, Dinner).
  - Rating system and student feedback module.
- 📢 **Community Hub & Notices:**
  - Digital notice board for instant campus announcements.
  - Community Hub featuring general chat, announcement channels, and Lost & Found.
- 👥 **Visitor Registration:**
  - Pre-register visitors with check-in/check-out timestamps and approval verification.
- 🔄 **Room Transfer Requests:**
  - Seamless digital requests for room transfers with warden review.
- 🌓 **Dark / Light Theme:** Custom UI styling with full light and dark mode toggling.

---

## 🛠️ Tech Stack

### Frontend
- **Framework:** React 19 + Vite
- **Routing:** React Router v7
- **Icons:** React Icons
- **Notifications:** React Toastify
- **Styling:** CSS3, Custom Responsive UI Layouts, CSS Variables for Dark/Light Themes

### Backend
- **Runtime:** Node.js + Express.js (v5)
- **Database:** MongoDB + Mongoose ORM
- **Authentication:** JSON Web Tokens (JWT) & bcryptjs
- **File Uploads:** Multer + Cloudinary
- **Email Notifications:** Nodemailer
- **Security & Rate Limiting:** Helmet, Express Rate Limit, Express Mongo Sanitize

---

## 📁 Repository Structure

```text
Hostel_Management_System/
├── backend/
│   ├── config/             # DB connection settings
│   ├── controllers/        # Route logic for auth, complaints, laundry, leave, etc.
│   ├── middleware/         # Auth, validation, upload, and error handling middleware
│   ├── models/             # Mongoose schemas (User, Complaint, GatePass, Laundry, etc.)
│   ├── routes/             # Express API endpoints
│   ├── utils/              # Cloudinary, Nodemailer, laundry cron job helpers
│   ├── validators/         # Input validation schemas
│   ├── server.js           # Server entry point
│   └── package.json
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── assets/         # Images, logos, and icons
│   │   ├── components/     # Reusable UI components (Navbar, Sidebar, Modals)
│   │   ├── context/        # React Context (AuthContext, ThemeContext)
│   │   ├── layouts/        # Admin, Staff, Student layout wrappers
│   │   ├── pages/          # Page components grouped by feature
│   │   ├── App.jsx         # Main application component & routes
│   │   └── main.jsx        # App entry point
│   └── package.json
└── README.md
```

---

## ⚙️ Prerequisites

Before running the project, ensure you have the following installed:
- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [MongoDB](https://www.mongodb.com/) (Local instance or MongoDB Atlas cluster)
- Cloudinary Account (for image upload features)
- Email credentials / SMTP server (for email notifications)

---

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/PARIKSHIT-hub/Hostel_Management_System.git
cd Hostel_Management_System
```

---

### 2. Backend Setup

1. Navigate to the backend directory:
   ```bash
   cd backend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the `backend` folder based on `.env.example`:
   ```env
   PORT=5000
   MONGO_URI=mongodb://localhost:27017/hostel_db
   JWT_SECRET=your_jwt_secret_key

   # Cloudinary Credentials
   CLOUDINARY_CLOUD_NAME=your_cloud_name
   CLOUDINARY_API_KEY=your_api_key
   CLOUDINARY_API_SECRET=your_api_secret

   # Nodemailer Credentials
   EMAIL_USER=your_email@gmail.com
   EMAIL_PASS=your_app_specific_password
   ```

4. Start the backend server:
   - Development Mode (with nodemon):
     ```bash
     npm run dev
     ```
   - Production Mode:
     ```bash
     npm start
     ```

The backend server will run on `http://localhost:5000`.

---

### 3. Frontend Setup

1. Navigate to the frontend directory:
   ```bash
   cd ../frontend
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Start the development server:
   ```bash
   npm run dev
   ```

The frontend application will run on `http://localhost:5173`.

---

## 📑 API Endpoints Summary

| Endpoint | Method | Description |
| :--- | :--- | :--- |
| `/api/auth/register` | `POST` | Register a new user |
| `/api/auth/login` | `POST` | Authenticate user & receive JWT token |
| `/api/complaints` | `GET` / `POST` | View and submit hostel complaints |
| `/api/laundry` | `GET` / `POST` | Check machine availability and book slots |
| `/api/leave` | `GET` / `POST` | Apply for leave and track history |
| `/api/gate` | `GET` / `POST` | Issue and scan digital gate passes |
| `/api/mess` | `GET` / `POST` | View mess menus and submit ratings |
| `/api/notices` | `GET` / `POST` | View and create digital notices |
| `/api/community` | `GET` / `POST` | Read/post community announcements & chats |
| `/api/visitors` | `GET` / `POST` | Log and approve visitor entries |
| `/api/room-transfer` | `GET` / `POST` | Submit and manage room transfer requests |

---

## 🤝 Contributing

Contributions are welcome! If you find any issues or have ideas for enhancement, feel free to open an issue or submit a pull request.

1. Fork the project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📜 License

Copyright © 2026 [PARIKSHIT-hub](https://github.com/PARIKSHIT-hub). All Rights Reserved.

This project is **private and proprietary**. Unauthorized copying, modification, distribution, or reuse of this code and software, via any medium, is strictly prohibited without explicit written permission from the owner.
