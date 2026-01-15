# Express Backend Setup Complete! 🎉

## ✅ Backend Status: READY TO RUN

The Express backend for SHRM Counseling Website is **fully configured** and ready to start once Node.js dependencies are installed.

## 📁 Backend Structure Overview

```
server/
├── server.js              # Main Express server file
├── package.json           # Backend dependencies
├── .env                   # Environment variables (configured)
├── .env.example          # Environment template
├── models/               # MongoDB schemas
│   ├── User.js           # User/Client/Counselor model
│   └── Appointment.js    # Appointment booking model
├── routes/               # API endpoints
│   ├── auth.js           # Authentication (login/register)
│   ├── appointments.js   # Appointment management
│   ├── users.js          # User profile management
│   ├── services.js       # Counseling services info
│   └── contact.js        # Contact form handling
└── middleware/
    └── auth.js           # JWT authentication middleware
```

## 🔧 Configuration Complete

### ✅ Environment Variables (`.env` file created)
- **Server Port**: 5000
- **MongoDB**: `mongodb://localhost:27017/shrm_counseling`
- **JWT Secret**: Set (change for production)
- **CORS**: Configured for frontend (port 3000)
- **Email**: Ready for SMTP configuration
- **Security**: Rate limiting, helmet, bcrypt configured

### ✅ API Endpoints Ready
- `GET /api/health` - Server health check
- `POST /api/auth/register` - User registration
- `POST /api/auth/login` - User login
- `GET /api/auth/me` - Get current user
- `POST /api/appointments` - Book appointment
- `GET /api/appointments` - Get user appointments
- `POST /api/contact` - Submit contact form
- `GET /api/services` - Get counseling services
- `GET /api/users/counselors` - Get counselor list

## 🚀 How to Start the Backend

### Option 1: Start Backend Only
```bash
# Navigate to server directory
cd "/Users/gregorygrant/Desktop/Websites/react/react webapp/shrm/server"

# Install dependencies (once Node.js is available)
npm install

# Start development server with auto-restart
npm run dev

# OR start production server
npm start
```

### Option 2: Start Full Stack (Recommended)
```bash
# From project root
cd "/Users/gregorygrant/Desktop/Websites/react/react webapp/shrm"

# Install all dependencies
npm run install-all

# Start both frontend and backend
npm run dev
```

## 🔍 Backend Features

### 🔐 **Authentication System**
- JWT-based secure authentication
- Password hashing with bcrypt
- Role-based access (client, counselor, admin)
- Session management

### 📅 **Appointment Management**
- Online appointment booking
- Status tracking (scheduled, confirmed, completed, etc.)
- Counselor assignment
- Time slot validation
- Email notifications

### 👥 **User Management**
- Client registration and profiles
- Counselor profiles and specializations
- Profile updates and password changes
- Emergency contact information

### 📧 **Communication**
- Contact form processing
- Email notifications
- Auto-reply system
- Crisis support routing

### 🛡️ **Security & Performance**
- Rate limiting (100 requests per 15 minutes)
- CORS protection
- Input validation and sanitization
- Security headers with Helmet
- Error handling and logging

## 🗄️ MongoDB Integration

### Required Database Setup
The backend expects a MongoDB database with these collections:
- `users` - Client, counselor, and admin accounts
- `appointments` - Appointment bookings and scheduling

### Connection Options
1. **Local MongoDB**: Install MongoDB locally
2. **MongoDB Atlas**: Use cloud database (recommended)
3. **Docker MongoDB**: Run MongoDB in container

Update the `MONGODB_URI` in `.env` file with your connection string.

## 📧 Email Configuration (Optional)

For contact forms and notifications, configure email in `.env`:
```env
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=your-shrm-email@gmail.com
EMAIL_PASS=your-app-password
```

## 🧪 Testing the Backend

Once running, test these endpoints:

```bash
# Health check
curl http://localhost:5000/api/health

# Get services
curl http://localhost:5000/api/services

# Register a test user
curl -X POST http://localhost:5000/api/auth/register \
  -H "Content-Type: application/json" \
  -d '{"firstName":"Test","lastName":"User","email":"test@example.com","password":"password123"}'
```

## 🎯 Next Steps

1. **Install Node.js** if not available
2. **Install Dependencies**: Run `npm install` in server directory
3. **Setup MongoDB**: Local installation or MongoDB Atlas
4. **Configure Email**: Update email settings in `.env`
5. **Start Backend**: Run `npm run dev`
6. **Test API**: Use the health endpoint to verify

## 🔧 Troubleshooting

### Common Issues:
- **Port 5000 in use**: Change PORT in `.env` file
- **MongoDB connection failed**: Check MONGODB_URI and ensure MongoDB is running
- **CORS errors**: Verify CLIENT_URL matches frontend port
- **Email not sending**: Check EMAIL_* configuration in `.env`

### Debug Commands:
```bash
# Check if port 5000 is available
lsof -i :5000

# View server logs
npm run dev
# Look for "SHRM Counseling Server running on port 5000"
```

## 🎉 Status Summary

**✅ Express Backend: COMPLETE**
- Server configuration: ✅
- Database models: ✅  
- API routes: ✅
- Authentication: ✅
- Security middleware: ✅
- Environment setup: ✅

**Ready to serve the SHRM counseling website!**