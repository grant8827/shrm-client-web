# Safe Haven Restoration Ministries (SHRM) - Counseling Website

A full-stack web application for Safe Haven Restoration Ministries, providing professional Christian counseling services with online appointment booking and client management.

## 🌟 Features

- **Responsive Design**: Mobile-first responsive design that works on all devices
- **Online Appointment Booking**: Clients can request appointments online
- **Service Information**: Detailed information about counseling services offered
- **Contact Forms**: Multiple ways for clients to get in touch
- **User Authentication**: Secure login system for clients and counselors
- **Professional Interface**: Clean, professional design suitable for a counseling practice
- **Faith-Based Approach**: Content and design that reflects Christian values and approach

## 🛠 Technology Stack

### Frontend
- **React 18** with TypeScript
- **React Router** for navigation
- **Axios** for API communication
- **CSS3** with responsive design
- **Modern ES6+** JavaScript features

### Backend
- **Node.js** with Express.js
- **MongoDB** with Mongoose ODM
- **JWT** for authentication
- **bcryptjs** for password hashing
- **Express Validator** for input validation
- **Nodemailer** for email notifications
- **Helmet** for security headers
- **CORS** for cross-origin requests

### Security Features
- Rate limiting to prevent abuse
- Input validation and sanitization
- Password hashing with bcrypt
- JWT token authentication
- HELMET security headers
- CORS configuration

## 📁 Project Structure

```
shrm/
├── client/                 # React frontend application
│   ├── public/            # Static files
│   ├── src/
│   │   ├── components/    # Reusable React components
│   │   ├── pages/         # Page components
│   │   ├── services/      # API service functions
│   │   ├── styles/        # CSS stylesheets
│   │   └── index.tsx      # Application entry point
│   └── package.json
├── server/                # Express backend application
│   ├── middleware/        # Custom middleware
│   ├── models/           # MongoDB/Mongoose models
│   ├── routes/           # API route handlers
│   ├── server.js         # Server entry point
│   └── package.json
├── package.json          # Root package.json for scripts
└── README.md
```

## 🚀 Getting Started

### Prerequisites
- Node.js (v16 or higher)
- MongoDB (local installation or MongoDB Atlas)
- Git

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd shrm
   ```

2. **Install dependencies**
   ```bash
   # Install root dependencies
   npm install

   # Install server dependencies
   npm run install-server

   # Install client dependencies
   npm run install-client
   ```

3. **Environment Setup**
   ```bash
   # Copy environment example file
   cp server/.env.example server/.env
   
   # Edit the .env file with your configuration
   nano server/.env
   ```

4. **Configure Environment Variables**
   Update `server/.env` with your settings:
   ```env
   NODE_ENV=development
   PORT=5000
   MONGODB_URI=mongodb://localhost:27017/shrm_counseling
   JWT_SECRET=your_secure_jwt_secret_here
   EMAIL_USER=your_email@gmail.com
   EMAIL_PASS=your_app_password
   CLIENT_URL=http://localhost:3000
   ```

5. **Start the Application**
   ```bash
   # Start both frontend and backend in development mode
   npm run dev
   
   # Or start them separately:
   npm run server    # Start backend only
   npm run client    # Start frontend only
   ```

6. **Access the Application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:5000
   - API Health Check: http://localhost:5000/api/health

## 📚 API Documentation

### Authentication Endpoints
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user

### Appointment Endpoints
- `POST /api/appointments` - Create appointment request
- `GET /api/appointments` - Get user's appointments
- `GET /api/appointments/:id` - Get specific appointment
- `PUT /api/appointments/:id/status` - Update appointment status

### Contact Endpoints
- `POST /api/contact` - Submit contact form

### Service Endpoints
- `GET /api/services` - Get all services
- `GET /api/services/:id` - Get specific service
- `GET /api/services/availability/:date` - Check availability

### User Endpoints
- `GET /api/users/profile` - Get user profile
- `PUT /api/users/profile` - Update user profile
- `GET /api/users/counselors` - Get counselor list
- `POST /api/users/change-password` - Change password

## 🎨 Styling and Design

The application uses a professional color scheme suitable for a counseling practice:
- **Primary Blue**: #3498db (trust, calm)
- **Dark Blue**: #2c3e50 (professional, stable)
- **Light Gray**: #f8f9fa (clean, accessible)
- **Success Green**: #27ae60 (positive feedback)
- **Warning Red**: #e74c3c (alerts, important information)

## 📱 Responsive Design

The application is fully responsive with breakpoints at:
- Desktop: 1200px+
- Tablet: 768px - 1199px
- Mobile: <768px

## 🔐 Security Considerations

- All passwords are hashed using bcrypt
- JWT tokens for secure authentication
- Input validation on all forms
- Rate limiting to prevent abuse
- CORS properly configured
- Security headers via Helmet
- Environment variables for sensitive data

## 🚀 Deployment

### Frontend Deployment (Netlify/Vercel)
```bash
cd client
npm run build
# Deploy the build folder
```

### Backend Deployment (Heroku/Railway)
```bash
# The application includes a Procfile and is ready for Heroku deployment
# Make sure to set environment variables in your hosting platform
```

### Environment Variables for Production
Set these in your hosting platform:
- `NODE_ENV=production`
- `MONGODB_URI=your_production_mongodb_uri`
- `JWT_SECRET=your_production_jwt_secret`
- `EMAIL_USER=your_production_email`
- `EMAIL_PASS=your_production_email_password`
- `CLIENT_URL=your_production_frontend_url`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📞 Support

For technical support or questions about this application:
- Create an issue in the repository
- Contact the development team

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Built with love for Safe Haven Restoration Ministries
- Designed to serve those seeking healing and restoration
- Created to support the mission of Christian counseling and mental health services

---

**Safe Haven Restoration Ministries** - *Finding Hope, Healing, and Restoration Through Faith-Based Counseling*