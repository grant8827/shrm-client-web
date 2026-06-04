# Netlify Deployment Fix for React App

## ❌ The Problem
Netlify is looking for a `.next` directory, but this is a **React app** (not Next.js).
React apps build to a `build/` directory, not `.next/`.

## ✅ The Solution

### 1. **netlify.toml Configuration**
```toml
[build]
  command = "npm run build"
  publish = "build"          # ← CORRECT: React output directory

[build.environment]
  NODE_VERSION = "18"
  REACT_APP_API_URL = "https://shrm-server-web-production.up.railway.app/api"
```

### 2. **React Router Support**
- Added `public/_redirects` file
- Configured SPA routing in `netlify.toml`

### 3. **Build Process**
```bash
# React build process (NOT Next.js)
npm install      # Install dependencies
npm run build    # Creates 'build/' directory
```

## 🚀 Netlify Settings

### Manual Configuration (if needed):
1. **Build Command**: `npm run build`
2. **Publish Directory**: `build`
3. **Base Directory**: Leave empty (or `client` if subfolder)

### Environment Variables:
- `REACT_APP_API_URL`: `https://shrm-server-web-production.up.railway.app/api`
- `NODE_VERSION`: `18`
- `CI`: `true`

## 📁 Correct Directory Structure
```
client/
├── build/              ← React output (CORRECT)
├── netlify.toml        ← Netlify config
├── public/_redirects   ← SPA routing
└── package.json        ← Build scripts
```

## ⚠️ Important Notes
- **Never create a `.next` directory** - this is for Next.js only
- **React apps use `build/` directory** - this is standard
- **The error is a configuration issue**, not a missing directory

## 🔧 Troubleshooting
If Netlify still looks for `.next`:
1. Clear build cache in Netlify dashboard
2. Trigger new deployment
3. Check build logs for correct `build/` directory creation