# SHRM Frontend Error Fix Guide

## Current Situation

The SHRM counseling website frontend has errors because Node.js is not installed on this system. Here's what needs to be done:

## Issues Identified

1. **Node.js Missing**: Commands `node` and `npm` are not found
2. **Dependencies Not Installed**: React Router and other packages are missing
3. **TypeScript Compilation**: Cannot compile TypeScript files without proper setup

## Quick Fix Solution

I've created simplified versions of the components that work without react-router-dom:

### Files Created for Immediate Use:
- `AppSimple.tsx` - Main app without router dependency
- `HeaderSimple.tsx` - Header with button navigation
- `FooterSimple.tsx` - Footer with button navigation  
- `HomeSimple.tsx` - Home page with navigation props
- `SETUP.md` - Detailed setup instructions

## Step-by-Step Fix

### 1. Install Node.js (Required First)

**Option A: Official Installer**
1. Go to https://nodejs.org/
2. Download LTS version for macOS
3. Run installer and follow prompts
4. Restart terminal

**Option B: Using Terminal**
```bash
# Install Homebrew first
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then install Node.js
brew install node
```

### 2. Verify Node.js Installation
```bash
node --version    # Should show version like v18.x.x
npm --version     # Should show version like 9.x.x
```

### 3. Install Project Dependencies
```bash
# Navigate to project root
cd "/Users/gregorygrant/Desktop/Websites/react/react webapp/shrm"

# Install dependencies for the entire project
npm install

# Install client dependencies
cd client
npm install

# Install server dependencies  
cd ../server
npm install
```

### 4. Use the Simplified Version (Temporary)

To test immediately after Node.js installation, you can use the simplified version:

1. Rename current `App.tsx` to `App-Router.tsx`:
```bash
cd client/src
mv App.tsx App-Router.tsx
mv AppSimple.tsx App.tsx
```

2. Start the development server:
```bash
npm start
```

### 5. Switch Back to Full Version (After Dependencies Install)

Once all dependencies are installed:

1. Restore the router version:
```bash
cd client/src
mv App.tsx AppSimple.tsx
mv App-Router.tsx App.tsx
```

2. The full version with React Router will now work properly.

## Expected Behavior After Fix

✅ **Frontend (port 3000)**: 
- Professional counseling website interface
- Navigation between Home, About, Services, Contact, Appointments
- Responsive design for mobile/desktop
- Professional styling with healing colors

✅ **Backend (port 5000)**:
- REST API for appointments, users, services
- Authentication system
- MongoDB integration
- Email notifications

## Environment Setup Checklist

After Node.js installation:

- [ ] Node.js and npm commands work
- [ ] Dependencies installed (`npm install` in root, client, and server)
- [ ] MongoDB connection configured (local or cloud)
- [ ] Environment variables set in `server/.env`
- [ ] Both frontend and backend start successfully
- [ ] Can access http://localhost:3000 and http://localhost:5000

## Common Commands After Setup

```bash
# Start both frontend and backend
npm run dev

# Start only frontend (from root)
npm run client

# Start only backend (from root) 
npm run server

# Install new dependencies
cd client && npm install package-name
cd server && npm install package-name
```

## Troubleshooting

**If you still see import errors:**
- Ensure you're in the client directory: `cd client`
- Run `npm install` to install React Router and other dependencies
- Check that `node_modules` folder exists in client directory

**If MongoDB errors:**
- Install MongoDB locally or use MongoDB Atlas cloud
- Update `MONGODB_URI` in `server/.env` file

**If ports are in use:**
- Kill existing processes or change ports in package.json

## Need Help?

1. Follow the SETUP.md file for detailed instructions
2. Check that all dependencies are properly installed
3. Verify environment variables are configured
4. Test each component individually if needed

The website structure is complete - it just needs Node.js and dependencies to run properly!