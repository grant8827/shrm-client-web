# SHRM Setup Instructions

## Prerequisites Installation Required

The SHRM counseling website requires Node.js to be installed. Follow these steps:

### 1. Install Node.js (Required)

#### Option A: Download from Official Website
1. Visit https://nodejs.org/
2. Download the LTS (Long Term Support) version
3. Run the installer and follow the prompts
4. Restart your terminal

#### Option B: Install via Homebrew (macOS)
```bash
# Install Homebrew first (if not already installed)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Node.js via Homebrew
brew install node
```

### 2. Verify Installation
After installing Node.js, verify it's working:
```bash
node --version
npm --version
```

### 3. Install Project Dependencies
Once Node.js is installed, run these commands:
```bash
# Navigate to project root
cd /Users/gregorygrant/Desktop/Websites/react/react\ webapp/shrm

# Install root dependencies
npm install

# Install server dependencies
cd server
npm install

# Install client dependencies  
cd ../client
npm install
```

### 4. Set Up Environment Variables
```bash
# Copy the environment template
cp server/.env.example server/.env

# Edit the environment file with your settings
# You can use any text editor like nano, vim, or VSCode
```

Required environment variables:
- `MONGODB_URI`: Your MongoDB connection string
- `JWT_SECRET`: A secure random string for JWT tokens
- `EMAIL_USER`: Email for sending notifications (optional)
- `EMAIL_PASS`: Email password/app password (optional)

### 5. Start the Development Servers
```bash
# From the project root, start both frontend and backend
npm run dev

# Or start them separately:
npm run server    # Backend only (port 5000)
npm run client    # Frontend only (port 3000)
```

### 6. Access the Application
- Frontend: http://localhost:3000
- Backend API: http://localhost:5000
- Health Check: http://localhost:5000/api/health

## Common Issues and Solutions

### Issue: "command not found: npm" or "command not found: node"
**Solution**: Node.js is not installed or not in your PATH. Follow step 1 above.

### Issue: "Cannot find module 'react-router-dom'"
**Solution**: Dependencies aren't installed. Run `npm install` in the client directory.

### Issue: MongoDB connection errors
**Solution**: 
1. Install MongoDB locally, or
2. Use MongoDB Atlas (cloud), or  
3. Update MONGODB_URI in your .env file

### Issue: Port already in use
**Solution**: 
- Kill existing processes on ports 3000/5000, or
- Change ports in package.json scripts

### Issue: CORS errors in browser
**Solution**: Make sure both frontend (3000) and backend (5000) are running.

## Development Workflow

1. **Backend Development**: Edit files in `/server` directory
2. **Frontend Development**: Edit files in `/client/src` directory  
3. **Styling**: Modify CSS files in `/client/src/styles`
4. **API Testing**: Use http://localhost:5000/api/health to test backend

## Need Help?

If you encounter issues:
1. Check that Node.js is properly installed
2. Ensure all dependencies are installed (`npm install` in both client and server directories)
3. Verify environment variables are set correctly
4. Check that MongoDB is running and accessible
5. Review the console for specific error messages

## Next Steps After Setup

Once everything is running:
1. Create a MongoDB database (local or cloud)
2. Add initial counselor users to the database
3. Configure email settings for contact forms
4. Customize the content and styling as needed
5. Set up deployment when ready to go live