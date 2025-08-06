# EmailJS Setup Guide

Follow these steps to make your contact form fully functional:

## 1. Create EmailJS Account
1. Go to [EmailJS](https://www.emailjs.com/)
2. Sign up for a free account

## 2. Create Email Service
1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the authentication steps
5. Save your Service ID (e.g., "service_abc123")

## 3. Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template structure:

```
Subject: New Contact Form Message from {{from_name}}

From: {{from_name}}
Email: {{from_email}}

Message:
{{message}}
```

4. Set "To Email" to your email address
5. Save and note your Template ID (e.g., "template_xyz789")

## 4. Get Your Public Key
1. Go to "Account" → "API Keys"
2. Copy your Public Key

## 5. Update Your Code
Replace the placeholders in `script.js`:

```javascript
// Line 126
emailjs.init('YOUR_PUBLIC_KEY'); // Replace with your actual public key

// Line 156
await emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams);
// Replace with your actual service and template IDs
```

## 6. Test Your Form
1. Open your portfolio in a browser
2. Fill out the contact form
3. Click "Send Message"
4. You should see a success notification and receive an email

## Alternative: Use Environment Variables
For better security, consider using environment variables or a configuration file that's not committed to version control.

## Troubleshooting
- Check browser console for errors
- Verify all IDs are correct
- Ensure your email service is properly connected in EmailJS
- Check your spam folder for test emails