# Contact Form Setup Guide

## Current Status

**The contact form currently shows a JavaScript alert** when submitted. It doesn't actually send messages anywhere. This is fine for a portfolio demonstration, but here are your options to make it functional:

## Option 1: Formspree (Recommended - Easiest)

**Best for:** Quick setup, no backend needed
**Cost:** Free for 50 submissions/month

### Setup Steps:

1. Go to [formspree.io](https://formspree.io/) and sign up
2. Create a new form and get your form ID
3. Update `index.html` line 147:

```html
<!-- Change this: -->
<form id="contact-form" class="contact-form">

<!-- To this: -->
<form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="contact-form">
```

4. Remove or comment out the form validation in `script.js` (lines 24-48)

**That's it!** Messages will be sent to your email.

## Option 2: EmailJS

**Best for:** More control, client-side only
**Cost:** Free for 200 emails/month

### Setup Steps:

1. Sign up at [emailjs.com](https://www.emailjs.com/)
2. Create an email service and template
3. Add EmailJS SDK to `index.html` before closing `</body>`:

```html
<script src="https://cdn.jsdelivr.net/npm/@emailjs/browser@3/dist/email.min.js"></script>
<script>
    emailjs.init("YOUR_PUBLIC_KEY");
</script>
```

4. Update `script.js` form handler to use EmailJS API

## Option 3: Remove Form, Use Direct Contact Only

**Best for:** Simplicity, avoiding spam

Simply remove the entire form section (lines 147-163 in `index.html`) and keep only:
- Email link (already added)
- Phone link (already added)
- Social media links

Visitors will click your email/phone to contact you directly.

## Option 4: Link to External Contact

Replace the form with a button linking to:

```html
<!-- Discord -->
<a href="https://discord.com/users/YOUR_DISCORD_ID" class="btn-primary">Message me on Discord</a>

<!-- LinkedIn -->
<a href="https://linkedin.com/in/yourprofile" class="btn-primary">Connect on LinkedIn</a>

<!-- Twitter/X -->
<a href="https://twitter.com/messages/compose?recipient_id=YOUR_ID" class="btn-primary">DM on Twitter</a>
```

## Option 5: Build Your Own Backend

**Best for:** Learning, full control
**Requires:** Node.js server, email service (like SendGrid or Nodemailer)

This is more complex but great for learning. You'd need:
1. A backend server (Node.js + Express)
2. Email sending service
3. Separate hosting for the backend

## My Recommendation

For your portfolio right now, I recommend **Option 1 (Formspree)** or **Option 3 (Remove form, use direct contact)**.

### Why Formspree?
- Takes 5 minutes to set up
- Professional appearance
- Actually works
- Free tier is plenty for a portfolio

### Why Direct Contact Only?
- Even simpler
- No spam submissions
- People can email/call you directly
- Still looks professional

## What to Update Right Now

In `index.html`, update these placeholders:

**Line 143-144:** Replace with your actual contact info:
```html
<strong>Email:</strong> <a href="mailto:your.email@example.com">your.email@example.com</a>
<strong>Phone:</strong> <a href="tel:+1234567890">+1 (234) 567-890</a>
```

Change to:
```html
<strong>Email:</strong> <a href="mailto:grace@example.com">grace@example.com</a>
<strong>Phone:</strong> <a href="tel:+15551234567">+1 (555) 123-4567</a>
```

**Optional:** If you don't want to show your phone number publicly, just remove that line entirely.

## Quick Decision Guide

- **Want working form in 5 minutes?** → Use Formspree
- **Don't want to deal with forms?** → Remove form, keep email/phone links
- **Want to learn backend?** → Build your own (but do this later)
- **Prefer social media contact?** → Add Discord/LinkedIn links, remove form

Choose what works best for you!
