# Performance Advisory Partners — Go High Level Deployment Guide

## Overview
5 self-contained premium HTML pages with all CSS/JS inline. Ready for Go High Level.

## Deployment Steps

### Step 1: Create a Website in GHL
1. Log into GHL → **Sites** → **Websites** → **+ New Website**
2. Choose **"Blank Template"**
3. Name it "Performance Advisory Partners"

### Step 2: Add Pages
Create 5 pages with these paths:
- Home: `/` (set as homepage)
- About: `/about`
- Services: `/services`
- Speaking: `/speaking`
- Contact: `/contact`

### Step 3: Add Code to Each Page
For each page:
1. Open the page in the GHL editor
2. Delete any default content
3. Add a **"Custom JS/HTML"** element (drag from elements panel)
4. Make it full-width
5. Click the element → **Open Code Editor**
6. Paste the ENTIRE contents of the matching HTML file
7. Click Save

### Step 4: Connect Your Domain
1. **Settings** → **Domains** → Add `PerformanceAdvisoryPartners.com`
2. Follow GHL's DNS setup instructions
3. Point your domain to GHL's servers

### Step 5: Replace Placeholder Images
1. Go to **Marketing** → **Media** in GHL
2. Upload your images (headshot, speaking photos, certification badges)
3. Copy each image URL
4. In the code editor, find placeholder divs like:
   ```html
   <div class="placeholder-img">[Headshot Photo]</div>
   ```
5. Replace with:
   ```html
   <img src="YOUR_IMAGE_URL" alt="Description" style="width:100%;height:100%;object-fit:cover;border-radius:20px;">
   ```

### Step 6: Connect Forms
Option A (Simple):
1. In GHL → **Sites** → **Forms** → Create "Contact Form" and "Speaking Form"
2. Get the webhook URLs
3. Add `action="WEBHOOK_URL" method="POST"` to each `<form>` tag in the code

Option B (GHL Native):
1. Replace the custom HTML forms with GHL's built-in form elements
2. This gives you automatic CRM integration

### Step 7: Connect Your Calendar
1. Go to **Calendars** in GHL
2. Copy your booking link
3. Find all `href="#"` on "Schedule an Appointment" and "Reserve Your Discovery Call" buttons
4. Replace `#` with your calendar URL

### Step 8: Test Everything
- [ ] All 5 pages load correctly
- [ ] Navigation links work between all pages
- [ ] Mobile menu opens and closes
- [ ] Forms submit and show success message
- [ ] Images display properly
- [ ] Calendar links open your booking page
- [ ] Scroll animations trigger on scroll
- [ ] Site looks good on mobile, tablet, and desktop

---

## File Structure

```
sk2-website/
├── index.html          (Home)
├── about.html          (About)
├── services.html       (Services)
├── speaking.html       (Speaking & Training)
├── contact.html        (Contact)
├── assessment.html     (AI Readiness Assessment Landing Page)
└── README.md           (This file)
```

---

## Brand Colors Reference

```css
:root {
  /* Core */
  --navy: #0F2747;
  --navy-deep: #0a1c38;
  --navy-surface: #122a4e;
  --slate: #6F7F94;
  --slate-light: #94a3b8;
  --text-body: #c8d1dc;        /* Body text on dark backgrounds */

  /* Accent (use sparingly, <10%) */
  --teal: #008B8F;
  --teal-bright: #00d4db;

  /* Decorative only */
  --violet: #CA4BFF;

  /* Light backgrounds */
  --bg-light: #f0f2f5;
  --bg-white: #FFFFFF;
  --text-dark: #0F2747;
  --text-dark-body: #3a4a5e;
}
```

---

## Typography

- **Font**: Montserrat (Google Fonts)
- **Weights used**: 300, 400, 500, 600, 700, 800, 900
- **Hero H1**: 800 weight, gradient text effect (white to teal)
- **Section H2**: 800 weight, tight letter-spacing

---

## Image Placeholders to Replace

### about.html
- `[Headshot Photo — Sherry K. Kotvis]` - Professional headshot (recommended: 400×480px)
- `[CAIO Badge]`, `[MS Degree]`, `[Certification]` badges (120×120px each)
- `[Decorative Illustration]` - Abstract/network illustration

### speaking.html
- `[Speaking Event 1]` through `[Speaking Event 2]`
- `[Training Session 1]` through `[Training Session 2]`
- `[Conference 1]` through `[Conference 2]`
- All gallery images: recommended 360×220px

### contact.html
- `[Discovery Call / Consultation Photo]` - Professional consultation image
- `[Google Maps Embed — Maricopa County, AZ]` - Replace with actual Google Maps iframe

---

## Forms Configuration

### Contact Form (`contact.html`)
Fields:
- Full Name (required)
- Email Address (required)
- Phone (optional)
- Subject (dropdown, required)
- Message (textarea, required)

### Speaking Inquiry Form (`speaking.html`)
Fields:
- Full Name (required)
- Email Address (required)
- Organization / Company (required)
- Phone Number (optional)
- Event Type (dropdown, required)
- Expected Audience Size (dropdown, optional)
- Preferred Date(s) (text, optional)
- Event Location (text, optional)
- Budget Range (dropdown, optional)
- Additional Details (textarea, optional)

---

## Quick Fixes

### Nav links broken?
Check that your GHL page paths match: `/about`, `/services`, `/speaking`, `/contact`

### Forms not submitting to CRM?
Make sure you added the GHL webhook URL to the form action attribute.

### Images look stretched?
Use `object-fit: cover` on all img tags.

### Styling conflicts with GHL?
GHL may inject its own CSS. Add `!important` to critical styles if needed.

### Scroll animations not working?
Ensure JavaScript at the bottom of each file is included. Check browser console for errors.

---

## Premium Features Included

- ✅ Animated gradient mesh backgrounds in hero sections
- ✅ Glassmorphism navigation with blur effect
- ✅ Gradient text effects on headings
- ✅ Glowing CTA buttons with hover lift
- ✅ Gradient-border cards with hover effects
- ✅ Scroll-triggered fade-up animations
- ✅ FAQ accordion with smooth animation
- ✅ Form validation with success messages
- ✅ Mobile hamburger menu with slide-in panel
- ✅ Responsive design (mobile, tablet, desktop)
- ✅ WCAG accessibility (skip links, ARIA labels, focus states)
- ✅ SEO meta tags (title, description, Open Graph)

---

## Service Pricing Reference

| Tier | Price |
|------|-------|
| Discovery Call | $500 (refundable, applied to engagement) |
| Snapshot | $6,500 (fixed-scope) |
| Sprint | Starting at $12,500 |
| Blueprint | Starting at $49,000 |
| CAIO Oversight | $7,500–$15,000/month (3-month min) |

---

## Landing Page Deployment (assessment.html)

### Step 1: Create a New Funnel in GHL
1. Go to **Sites** → **Funnels** → **+ Create New Funnel**
2. Name it "AI Readiness Assessment"
3. Choose "Start from scratch"
4. Add ONE funnel step, set the path to `/assessment`

### Step 2: Add the Landing Page Code
1. Open the funnel step editor
2. Add a **"Custom JS/HTML"** element
3. Make it full-width
4. Open the code editor and paste the ENTIRE contents of assessment.html
5. Save

### Step 3: Connect Lead Capture to GHL
To send leads into your GHL CRM automatically:

**Option A — Webhook (Recommended):**
1. In GHL, go to **Automation** → **Workflows** → **+ Create Workflow**
2. Choose trigger: **"Inbound Webhook"**
3. Copy the webhook URL
4. In assessment.html, find the hidden form with id="ghl-data"
5. Add the webhook URL as the form action
6. Uncomment the auto-submit JavaScript code (search for "GHL WEBHOOK" in the code)
7. Add workflow actions: Create/Update Contact, Add Tag "AI Assessment Lead", send notification

**Option B — GHL Native Form:**
1. In GHL, create a form with fields: First Name, Email
2. Replace the custom lead capture HTML with GHL's form embed code
3. You'll lose the seamless transition but gain native CRM integration

### Step 4: Set Up Your Social Media Link
Use this URL in all social media posts:
- `https://PerformanceAdvisoryPartners.com/assessment`
- Or use a short link service to create something like `PerformanceAdvisoryPartners.com/ready`

### Step 5: Connect Results CTAs to Main Site
In the assessment.html code, find the CTA buttons in the results section.
Update the href values to point to your live site:
- Discovery Call button → `https://PerformanceAdvisoryPartners.com/contact`
- Services button → `https://PerformanceAdvisoryPartners.com/services`

### Step 6: Test the Full Flow
- [ ] Landing page loads with hero + lead capture form
- [ ] Submitting name + email reveals the quiz
- [ ] All 7 questions display and auto-advance correctly
- [ ] Results show correct tier based on score
- [ ] Score ring animation plays
- [ ] CTA buttons link to main site
- [ ] Works perfectly on mobile
- [ ] Lead data flows into GHL CRM (after webhook setup)

---

© 2024–2025 Performance Advisory Partners. All rights reserved.
