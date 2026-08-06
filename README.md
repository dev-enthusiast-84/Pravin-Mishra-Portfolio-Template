# DMI Portfolio Website (Static HTML/CSS)

This repository contains a clean, professional-looking **static portfolio website** used in **DevOps Micro Internship (DMI)** Week 1 to practice:
- Linux basics
- Nginx hosting
- Deployment proof / ownership
- Production-style checks

✅ Students deploy this website on an Ubuntu VM using Nginx and keep it live for 24 hours.

---

## Who is this for?
- DMI students (beginner → intermediate)
- Anyone learning how to host a static site with Nginx on Linux

---

## What you will build
A portfolio-style website hosted on:
- **Ubuntu VM**
- **Nginx**
- Accessible via: `http://<public-ip>`

---

## Mandatory Ownership Proof (DMI Rule)
Before you deploy, you MUST edit the footer and add your details:

Original:

```html
<p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
```

Add this line (example):

```html
<p><strong>Deployed by:</strong> DMI Cohort 2 | Rahul Sharma | Group 4 | Week 1 | 16-01-2026</p>
```

✅ This proof must be visible in your browser screenshot submission.

---

## Dynamic Deploy Date in Footer

The portfolio footer now includes a **dynamically generated deploy date** that updates automatically when the page is loaded.

### How It Works

The deploy date is generated using JavaScript that:
1. Gets the current date when the page loads
2. Formats it as `DD Mon YYYY` (e.g., `06 Aug 2026`)
3. Displays it in the footer without requiring manual updates

### Footer Implementation

```html
<div class="footer-bottom">
  <p>© <span id="year"></span> Pravin Mishra. All rights reserved.</p>
  <p>Crafted with <span>cloud</span> excellence by Pravin Mishra</p>
  <p>Pravin Mishra Portfolio v1.0 - Deployed on <span id="deployDate"></span> — By Maneetta Antony</p>
</div>

<script>
  const options = { day: '2-digit', month: 'short', year: 'numeric' };
  document.getElementById('deployDate').textContent =
    new Date().toLocaleDateString('en-GB', options).replace(',', '');
</script>
```

### Key Points

- **No hardcoding needed**: The date updates automatically each time the page is deployed
- **Locale-aware**: Uses `en-GB` format for consistent date display
- **Client-side rendering**: JavaScript runs in the browser to display the current date