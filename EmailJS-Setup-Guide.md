# EmailJS Setup Guide for Direct Gmail Integration

## Step 1: Create EmailJS Account
1. Go to https://www.emailjs.com/
2. Sign up for a free account
3. Verify your email address

## Step 2: Connect Gmail Service
1. In EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Select "Gmail"
4. Connect your Gmail account (rohand2315@gmail.com)
5. Note down your SERVICE_ID (e.g., "service_gmail_123")

## Step 3: Create Email Template
1. Go to "Email Templates"
2. Click "Create New Template"
3. Use this template:

```
Subject: New Contact Form Submission from {{from_name}}

Hello {{to_name}},

You have received a new message from your website contact form:

Name: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Course Interested: {{course}}

Message:
{{message}}

Best regards,
Your Website Contact Form
```

4. Save the template and note down TEMPLATE_ID (e.g., "template_contact_123")

## Step 4: Get Public Key
1. Go to "Account" > "General"
2. Copy your Public Key (e.g., "qrWVtvvP7X8MrlbaM")

## Step 5: Update Website Code
Replace these values in index.html:

```javascript
// Replace with your actual EmailJS credentials
emailjs.init("YOUR_PUBLIC_KEY"); // Your public key
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams) // Your service and template IDs
```

## Current Implementation Features:
✅ Multiple fallback methods for email delivery
✅ Direct Gmail integration via EmailJS
✅ Form validation and user feedback
✅ Loading states and error handling
✅ Responsive design

## Alternative Methods Included:
1. **EmailJS** (Primary) - Direct Gmail integration
2. **Formspree** (Secondary) - Free form service
3. **Web3Forms** (Tertiary) - Another free service
4. **Manual fallback** - Shows contact information if all fail

## Testing the Form:
1. Fill out the contact form on your website
2. Submit the form
3. Check your Gmail inbox for the form submission
4. If primary method fails, secondary methods will try automatically

## Note:
The current code includes demo credentials that may not work. You need to set up your own EmailJS account and replace the credentials for full functionality.
