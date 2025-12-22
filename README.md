/jolysolutions-site
│
├── index.html
├── logo.png
├── CNAME
├── README.md
│
├── capabilities.html
│
├── energy-solutions.html
├── regulated-food.html
└── governance-risk.html


# Joly Solutions — Website

**Domain:** `jolysolutions.ca`
**Hosting:** GitHub Pages
**Registrar & DNS:** GoDaddy
**Repository type:** Static site (HTML + CSS, no framework)

This repository contains the public website for **Joly Solutions**, hosted using **GitHub Pages** and connected to the custom domain `jolysolutions.ca`.

The site is intentionally lightweight and framework-free to allow rapid iteration before any future migration to WordPress, Elementor, or another CMS.

---

## Repository Structure

```
/
├── index.html        # Main (and only) webpage
├── logo.png          # Company logo (used in header)
├── CNAME             # Custom domain for GitHub Pages
└── README.md         # This file
```

### Key Files

* **`index.html`**
  Contains all HTML and CSS. Clearly marked sections explain what each block does.
* **`logo.png`**
  Must remain in the root directory and named exactly `logo.png`.
* **`CNAME`**
  Contains only:

  ```
  jolysolutions.ca
  ```

---

## How the Website Is Hosted

* The site is hosted on **GitHub Pages**
* Pages are built from:

  * **Branch:** `main`
  * **Folder:** `/ (root)`
* GitHub Pages serves the site at:

  ```
  https://taz0519.github.io/<repository-name>/
  ```
* The custom domain `jolysolutions.ca` points to GitHub Pages via DNS

---

## Domain & DNS Configuration (GoDaddy)

**IMPORTANT:**
Email and Microsoft 365 services are already configured on this domain.
Do **NOT** remove or edit MX, TXT, CNAME, or SRV records unless you know exactly what you’re doing.

### Required Records for GitHub Pages (Website)

These records are **correct and required**:

#### A Records (Root Domain)

| Type | Host | Value           | TTL    |
| ---- | ---- | --------------- | ------ |
| A    | @    | 185.199.108.153 | 1 Hour |
| A    | @    | 185.199.109.153 | 1 Hour |
| A    | @    | 185.199.110.153 | 1 Hour |
| A    | @    | 185.199.111.153 | 1 Hour |

These tell the internet:

> “When someone visits jolysolutions.ca, send them to GitHub Pages.”

#### CNAME (www subdomain)

| Type  | Host | Value             | TTL    |
| ----- | ---- | ----------------- | ------ |
| CNAME | www  | taz0519.github.io | 1 Hour |

This ensures:

* `www.jolysolutions.ca` also works
* GitHub recognizes the domain as valid

---

## Email & Microsoft 365 (DO NOT TOUCH)

The following records support **Microsoft 365 / Outlook / GoDaddy email services**.
They are **not related to the website** and must remain intact.

### Nameservers (Required by GoDaddy)

```
ns35.domaincontrol.com
ns36.domaincontrol.com
```

### Email / Microsoft 365 Records

* **MX**

  ```
  jolysolutions-ca.mail.protection.outlook.com
  ```
* **CNAME**

  ```
  autodiscover → autodiscover.outlook.com
  email → email.secureserver.net
  lyncdiscover → webdir.online.lync.com
  msoid → clientconfig.microsoftonline-p.net
  sip → sipdir.online.lync.com
  ```
* **TXT**

  ```
  v=spf1 include:secureserver.net -all
  NETORG20136419.onmicrosoft.com
  ```
* **DMARC**

  ```
  v=DMARC1; p=quarantine; ...
  ```
* **SRV**

  ```
  _sip._tls
  _sipfederationtls._tcp
  ```

⚠️ **Do not delete or modify these** unless intentionally changing email providers.

---

## How to Update the Website

### 1. Edit Content

* Open `index.html`
* Look for comments like:

  ```html
  <!-- EDIT HERE -->
  ```
* Modify text, colours, sizes as needed

### 2. Preview Locally

* Double-click `index.html`
* Or open it in Chrome / Edge

### 3. Publish Changes

1. Commit changes to the `main` branch
2. GitHub Pages redeploys automatically (usually < 1 minute)

---

## Common Issues & Fixes

### Logo Not Showing

* File must be named **exactly** `logo.png`
* Must be in the root folder (same level as `index.html`)

### GitHub Pages Says “DNS check unsuccessful”

* DNS propagation can take up to **24 hours**
* Confirm A + CNAME records are correct
* Click **“Check again”** in GitHub Pages settings

### HTTPS Not Available

* HTTPS appears only **after DNS is correct**
* Enable **“Enforce HTTPS”** once available

---

## Future Migration Notes

This site is intentionally simple so it can be:

* Migrated into WordPress later
* Used as a holding page
* Replaced by a CMS without DNS changes

When migrating:

* Leave DNS A records in place
* Change hosting target only when ready
* Do not remove email records

---

## Maintainer

**Marc-Antoine Joly, P.Eng., CEM, CMVP**
📧 [marcantoinejpjoly@gmail.com](mailto:marcantoinejpjoly@gmail.com)
📞 +1 (613) 219-4375
🔗 [https://www.linkedin.com/in/energyjoly17/](https://www.linkedin.com/in/energyjoly17/)

---
