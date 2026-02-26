# Innovative X — Website Documentation

> **Stack:** Pure HTML5 · CSS3 · Vanilla JavaScript (No frameworks, no dependencies)

---

## 📁 Project Structure

```
innovativex/
│
├── index.html                        # Main website (Home)
├── helpdesk.html                     # Helpdesk landing page
├── helpdesk-live-bullion-web-app.html # Live Bullion View helpdesk articles
│
├── assets/
│   ├── favicon-96x96.png
│   ├── favicon.svg
│   ├── favicon.ico
│   ├── apple-touch-icon.png
│   ├── site.webmanifest
│   │
│   └── helpdesk/
│       └── live-bullion-web-app/     # All article images (26 images)
│           ├── admin-login1.png
│           ├── admin-login2.png
│           ├── bulk1.png
│           ├── bulk2.png
│           ├── bulk3.png
│           ├── bulk4.png
│           ├── bullion-gst-front.png
│           ├── bullion-wogst-front.png
│           ├── bullionwithgst.png
│           ├── bullionwithoutgst.png
│           ├── coinfront.png
│           ├── coinsdisplay.png
│           ├── createuser.png
│           ├── dynamicsetting.png
│           ├── full_form.png
│           ├── full_form_silver.png
│           ├── goldcoin.png
│           ├── market-closed.png
│           ├── market-onoff.png
│           ├── mcx1.png
│           ├── mcx2.png
│           ├── mcx3.png
│           ├── silvercoin.png
│           ├── spacestation-config.png
│           ├── supplier.png
│           └── viewuser.png
```

---

## 🎨 Theme & Design System

### Color Palette

| Variable | Hex | Usage |
|---|---|---|
| `--primary-blue` | `#00d4ff` | Primary accent, glows |
| `--primary-cyan` | `#00b8d4` | Hover states, borders |
| `--primary-green` | `#c8ff00` | Tips, highlights |
| `--primary-lime` | `#76ff03` | Success states, results |
| `--dark-bg` | `#0a0a0a` | Page background |
| `--dark-card` | `#1a1a1a` | Card/panel backgrounds |
| `--text-primary` | `#ffffff` | Headings, strong text |
| `--text-secondary` | `#b0b0b0` | Body text, descriptions |

### Gradient
```css
--gradient-primary: linear-gradient(135deg, #00d4ff, #00b8d4, #76ff03, #c8ff00);
```
Used on: Logo text, article numbers, step indicators, buttons, scroll-to-top.

### Typography
- **Headings / Logo:** `Orbitron` (Google Fonts) — weights 400, 500, 700, 900
- **Body / UI:** `Poppins` (Google Fonts) — weights 300, 400, 500, 600, 700

---

## 🧱 CSS Components

### Layout
```
.layout              → CSS Grid: 280px sidebar + 1fr content
.sidebar             → Sticky at top: 90px (below fixed header)
.articles-area       → Main content column
```

### Cards
```
.article-card        → Dark card with cyan border, 20px radius, hover glow
.article-number      → Gradient line + uppercase label (e.g. ARTICLE 01)
.article-body        → Body text container
```

### Step Boxes
```
.step                → Flex row: gradient circle number + text content
.step-num            → 26×26px circle, gradient background
.step-text           → Content area, 0.92rem
```

### Info Boxes (inline styles used for color variants)
```
Cyan box    → rgba(0,212,255,0.05) border  — Info / Notes
Yellow box  → rgba(255,180,0,0.07) border  — Warnings
Lime box    → rgba(118,255,3,0.05) border  — Tips / Automation
```

### Image Wrappers
```
.article-image-wrap  → Full-width image with zoom cursor, hover scale(1.02)
.img-narrow          → max-width: 320px, centered — for small nav screenshots
```

### Tip Box
```
.tip                 → Left border lime green, light green background
```

### Navigation Buttons
```
.nav-btn             → Prev/Next article buttons at bottom of each article
.nav-btn.next        → Right-aligned version
```

### Buttons
```
.btn-primary         → Gradient background, dark text
.btn-secondary       → Transparent, cyan border
```

---

## ⚙️ JavaScript Functionality

### 1. Mobile Menu
```javascript
// Toggles .active class on .nav-links
// Changes ☰ to ✕
// Locks body scroll when open
// Closes on outside click or nav link click
```

### 2. Header Scroll Effect
```javascript
// Adds .scrolled class to header after 50px scroll
// Increases opacity and adds shadow
```

### 3. One Article at a Time System
```javascript
// All .article-card elements are collected
// Only active article is shown (display: block), rest hidden (display: none)
// showArticle(index) handles switching
```

### 4. Sidebar Auto-Build
```javascript
// buildSidebar() reads all article h2 titles
// Generates numbered nav links dynamically
// Active state synced with current article
// Article count in header updated automatically
```

### 5. Sidebar Search
```javascript
// Filters sidebar nav items in real time
// Matches against data-title attribute (lowercase)
```

### 6. Prev / Next Navigation Buttons
```javascript
// updateNavButtons() runs on every article switch
// Dynamically creates ← Prev and Next → buttons
// Shows article title in button text
```

### 7. Scroll Behavior (Mobile Fix)
```javascript
// Scrolls to header height + 10px on article switch
// Ensures article title is not hidden behind fixed header on mobile
```

### 8. Lightbox
```javascript
// openLightbox(src)  → sets image src, adds .open class, locks scroll
// closeLightbox()    → removes .open, unlocks scroll
// Closes on: overlay click, ✕ button, Escape key
```

### 9. Scroll to Top Button
```javascript
// Appears after 300px scroll
// Smooth scroll to top
```

---

## 📱 Responsive Breakpoints

| Breakpoint | Change |
|---|---|
| `max-width: 900px` | Sidebar moves above content (single column), nav pills wrap |
| `max-width: 768px` | Mobile menu activates, padding reduced, help banner stacks |
| `max-width: 480px` | Logo smaller, nav padding tighter |

---

## 📄 Helpdesk Articles (Live Bullion View Web App)

| # | Title |
|---|---|
| 01 | Admin Login Guide |
| 02 | Selecting MCX Contracts |
| 03 | Bullion With GST – Add and Edit Script Guide |
| 04 | Bullion Without GST – Add and Edit Script Guide |
| 05 | Gold Coin – Add, Edit and Calculation Guide |
| 06 | Silver Coin – Add, Edit and Calculation Guide |
| 07 | Bulk Edit Guide – Discount / Premium |
| 08 | Spacestation Setting – System Configuration Guide |
| 09 | User Management – Create & View User Guide |

---

## ➕ How to Add a New Article

1. Open `helpdesk-live-bullion-web-app.html`
2. Find the comment: `<!-- ADD NEW ARTICLES BELOW THIS LINE -->`
3. Paste your new article block above that comment using this template:

```html
<div class="article-card" id="article-10" data-title="your article title keywords here">
    <div class="article-number">Article 10</div>
    <h2>Your Article Title Here</h2>
    <div class="article-body">
        <!-- content here -->
    </div>
</div>
```

4. The sidebar, article count, and prev/next buttons update **automatically**.
5. Add any new images to `assets/helpdesk/live-bullion-web-app/`

---

## 📞 Support

**Innovative X**
- 🌐 Website: [innovativex.in](https://innovativex.in)
- 📧 Email: info@innovativex.in
- 📱 Phone: +91 8196962922
