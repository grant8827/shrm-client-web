# 🔧 Email Debugging Guide

## Current Configuration
- **Host**: webhosting2023.is.cc
- **Port**: 587 (STARTTLS)
- **Username**: info@safehavenrestorationministries.com
- **Password**: Safehaven2025

## 🚨 Important Steps to Debug Email Issues

### Step 1: Test SMTP Configuration
Run this command in your terminal from the server directory:
```bash
node test-all-smtp.js
```

This will test multiple SMTP configurations:
1. STARTTLS Port 587 (current)
2. SSL Port 465 
3. Port 25 (Plain)
4. Alternative mail server

### Step 2: Check Server Logs
1. Start your Express server: `npm run dev` (from server directory)
2. Submit a contact form or appointment from your website
3. Watch the server console for these messages:
   - `📧 Sending appointment confirmation emails...`
   - `✅ Client confirmation email sent`
   - `❌ Failed to send appointment emails:`

### Step 3: Common Issues to Check

#### 🔐 Authentication Issues
- Verify the email password is correct: `Safehaven2025`
- Check if your hosting provider requires special SMTP authentication

#### 🌐 Network/Firewall Issues
- Your hosting provider might block outgoing SMTP
- Try different ports (587, 465, 25)
- Contact your hosting provider for SMTP settings

#### 📧 Email Server Settings
Your hosting provider might use different settings:
- Try `mail.webhosting2023.is.cc` as hostname
- Ask hosting provider for exact SMTP settings
- Check if they require SSL/TLS authentication

### Step 4: Alternative Configuration to Try

Update your `.env` file with these settings and test:

```env
# Try SSL on port 465
EMAIL_HOST=webhosting2023.is.cc
EMAIL_PORT=465
EMAIL_SECURE=true

# Or try mail subdomain
EMAIL_HOST=mail.webhosting2023.is.cc
EMAIL_PORT=587
EMAIL_SECURE=false
```

### Step 5: Contact Hosting Provider
If none work, contact your hosting provider and ask for:
1. SMTP server hostname
2. SMTP port number
3. SSL/TLS requirements
4. Any firewall restrictions

## 📝 Current Email Features
- ✅ Contact form emails (to admin + auto-reply to user)
- ✅ Appointment confirmation emails (to client + admin notification)
- ✅ Professional HTML email templates
- ✅ Comprehensive error logging

The email code is ready - we just need the correct SMTP settings!