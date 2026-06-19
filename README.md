# 📚 StudyNotion — EdTech Platform

StudyNotion is a fully functional EdTech platform that enables users to create, consume, and rate educational content. Built with the MERN stack (MongoDB, Express.js, React.js, Node.js), it provides a seamless learning experience for students and a powerful course management system for instructors.

---

## 🚀 Live Demo

> Run locally following the setup guide below.

---

## ✨ Features

### For Students
- 🔐 Signup / Login with OTP email verification
- 🛒 Browse, purchase, and enroll in courses
- 🎥 Watch video lectures with progress tracking
- ⭐ Rate and review courses
- 👤 Manage profile and settings

### For Instructors
- 📝 Create and manage courses with sections & sub-sections
- 📊 Instructor dashboard with earnings & student analytics
- 🖼️ Upload course thumbnails and video content via Cloudinary
- ✏️ Edit or delete existing courses

### General
- 💳 Razorpay payment integration
- 📧 Transactional emails (OTP, enrollment, password reset)
- 📱 Fully responsive UI

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Frontend** | React.js, Redux Toolkit, Tailwind CSS |
| **Backend** | Node.js, Express.js |
| **Database** | MongoDB (Mongoose) |
| **Media Storage** | Cloudinary |
| **Payments** | Razorpay |
| **Email** | Nodemailer (SMTP) |
| **Auth** | JWT, bcrypt |

---

## 📁 Project Structure

```
studynotion-edtech-project/
├── public/               # Static assets
├── src/                  # React frontend
│   ├── components/       # Reusable UI components
│   ├── pages/            # Route-level pages
│   ├── services/         # API calls & Redux operations
│   ├── slices/           # Redux state slices
│   └── hooks/            # Custom React hooks
├── server/               # Express backend
│   ├── config/           # DB, Cloudinary, Razorpay config
│   ├── controllers/      # Route handler logic
│   ├── models/           # Mongoose schemas
│   ├── routes/           # API route definitions
│   ├── middleware/        # Auth middleware
│   ├── mail/             # Email templates
│   └── utils/            # Helper utilities
├── .env                  # Frontend env variables (not committed)
└── server/.env           # Backend env variables (not committed)
```

---

## ⚙️ Getting Started

### Prerequisites
- Node.js v16+
- MongoDB (local or Atlas)
- A Gmail account (for OTP emails)
- Cloudinary account (for media uploads)
- Razorpay account (for payments, optional for local dev)

---

### 1. Clone the Repository

```bash
git clone https://github.com/phanome/StudyNotion-app.git
cd StudyNotion-app
```

---

### 2. Install Dependencies

```bash
# Install frontend dependencies
npm install

# Install backend dependencies
cd server && npm install && cd ..
```

---

### 3. Configure Environment Variables

#### Frontend — create `.env` in the root directory:
```env
REACT_APP_BASE_URL=http://localhost:4000/api/v1
```

#### Backend — create `server/.env`:
```env
JWT_SECRET=your_random_jwt_secret
MONGODB_URL=mongodb://127.0.0.1:27017/studynotion

# Gmail SMTP (use App Password)
MAIL_HOST=smtp.gmail.com
MAIL_USER=your_email@gmail.com
MAIL_PASS=your_gmail_app_password

# Cloudinary
CLOUD_NAME=your_cloudinary_cloud_name
API_KEY=your_cloudinary_api_key
API_SECRET=your_cloudinary_api_secret

# Razorpay (optional for local dev)
RAZORPAY_KEY=your_razorpay_key
RAZORPAY_SECRET=your_razorpay_secret
```

> **JWT_SECRET:** Generate one with:
> ```bash
> node -e "console.log(require('crypto').randomBytes(64).toString('hex'))"
> ```

> **Gmail App Password:** Go to [myaccount.google.com/apppasswords](https://myaccount.google.com/apppasswords) → Create an app password (requires 2FA enabled).

---

### 4. Run the Application

```bash
# Run both frontend and backend concurrently
npm run dev
```

- **Frontend:** [http://localhost:3000](http://localhost:3000)
- **Backend API:** [http://localhost:4000/api/v1](http://localhost:4000/api/v1)

---

## 🔑 API Overview

| Method | Endpoint | Description |
|---|---|---|
| POST | `/api/v1/auth/sendotp` | Send OTP for email verification |
| POST | `/api/v1/auth/signup` | Register a new user |
| POST | `/api/v1/auth/login` | Login and get JWT token |
| GET | `/api/v1/course/getAllCourses` | Fetch all courses |
| POST | `/api/v1/course/createCourse` | Create a new course (Instructor) |
| POST | `/api/v1/payment/capturePayment` | Initiate course payment |

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
