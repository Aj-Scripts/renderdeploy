# Event Management & Ticket Booking System

A fullstack web application for managing events, booking tickets, and handling payments. Built with React (frontend) and Node.js/Express (backend), featuring AI-powered recommendations, analytics, and seamless user experience.

## Features

- **User Authentication**: Secure login/signup with JWT tokens, password reset, and profile management.
- **Event Management**: Create, update, delete, and view events with image uploads (Cloudinary integration).
- **Ticket Booking**: Book tickets with Razorpay payment gateway, generate QR codes and PDF tickets.
- **AI Recommendations**: Personalized event suggestions using embeddings and machine learning.
- **Admin Dashboard**: Analytics, user management, revenue reports, and custom CSV/PDF exports.
- **Responsive Design**: Mobile-friendly UI built with TailwindCSS and React.
- **Email Notifications**: Automated emails for bookings and password resets.
- **Search & Filtering**: Advanced search with AI-powered event discovery.

## Tech Stack

### Frontend
- **React** (v19) with Vite for fast development
- **React Router** for navigation
- **Axios** for API calls
- **TailwindCSS** for styling
- **Chart.js** for analytics visualization
- **Lucide React** for icons
- **Browser Image Compression** for optimized uploads

### Backend
- **Node.js** with Express.js
- **MongoDB** with Mongoose for database
- **JWT** for authentication
- **Razorpay** for payments
- **Cloudinary** for image storage
- **Nodemailer** for emails
- **PDFKit** for ticket generation
- **QRCode** for ticket QR codes
- **AI Integration**: Google Generative AI and OpenAI for recommendations
- **Multer** for file uploads

### DevOps
- **Docker** for containerized deployment
- **Nodemon** for backend development
- **ESLint** for code linting

## Prerequisites

Before running the application, ensure you have the following installed:

- **Node.js** (v22 or higher) - [Download here](https://nodejs.org/)
- **MongoDB** (local or cloud instance like MongoDB Atlas)
- **Git** for cloning the repository
- **Docker** (optional, for containerized deployment)

## Installation

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd EventTest-Copy
   ```

2. **Install backend dependencies**:
   ```bash
   cd backend
   npm install
   ```

3. **Install frontend dependencies**:
   ```bash
   cd ../frontend
   npm install
   cd ..
   ```

## Environment Setup

1. **Create environment file** for the backend:
   - Copy `backend/.env.example` to `backend/.env` (if it exists) or create `backend/.env`
   - Add the following variables (replace with your actual values):

   ```env
   # Database
   MONGO_URI=mongodb://localhost:27017/event-management

   # JWT
   JWT_SECRET=your-super-secret-jwt-key-here

   # Email (for notifications)
   EMAIL_USER=your-email@gmail.com
   EMAIL_PASS=your-email-password

   # Cloudinary (for image uploads)
   CLOUDINARY_CLOUD_NAME=your-cloud-name
   CLOUDINARY_API_KEY=your-api-key
   CLOUDINARY_API_SECRET=your-api-secret

   # Razorpay (for payments)
   RAZORPAY_KEY_ID=your-razorpay-key-id
   RAZORPAY_KEY_SECRET=your-razorpay-key-secret

   # AI Services (optional, for recommendations)
   GOOGLE_AI_API_KEY=your-google-ai-key
   OPENAI_API_KEY=your-openai-key

   # Frontend URL (for CORS)
   FRONTEND_URL=http://localhost:5173

   # Port
   PORT=5000
   ```

   **Note**: Never commit `.env` files to version control. Add `backend/.env` to `.gitignore`.

## Running Locally

### Backend
1. Ensure MongoDB is running locally or update `MONGO_URI` for cloud DB.
2. Start the backend server:
   ```bash
   cd backend
   npm run dev
   ```
   - Server will run on `http://localhost:5000`
   - API endpoints available at `http://localhost:5000/api/*`

### Frontend
1. In a new terminal, start the frontend:
   ```bash
   cd frontend
   npm run dev
   ```
   - Frontend will run on `http://localhost:5173`
   - It proxies API calls to the backend automatically.

2. Open your browser and navigate to `http://localhost:5173` to access the application.

### Seeding the Database
To populate the database with sample data:
```bash
cd backend
npm run seed
```

## Running with Docker

For production deployment or easy setup:

1. **Build and run the Docker container**:
   ```bash
   docker build -t event-management-app .
   docker run -p 5000:5000 --env-file backend/.env event-management-app
   ```

2. Access the application at `http://localhost:5000` (frontend served by backend).

**Note**: Ensure all environment variables are set in `backend/.env` before building.

## API Overview

The backend provides RESTful APIs for:

- **Authentication** (`/api/auth`): Login, signup, profile management
- **Events** (`/api/events`): CRUD operations for events
- **Bookings** (`/api/bookings`): Ticket booking and management
- **Analytics** (`/api/analytics`): Admin reports and user management
- **Payments** (`/api/payment`): Razorpay integration
- **Recommendations** (`/api/recommendations`): AI-powered event suggestions

Refer to `frontend/src/services/api.js` for frontend API integration examples.

## Contributing

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Commit changes: `git commit -m 'Add some feature'`
4. Push to branch: `git push origin feature/your-feature-name`
5. Open a pull request.

## License

This project is licensed under the ISC License.

---
