# 🏥 Care At Home — Quality Home Healthcare Services

**Care At Home** is a frontend-only web application that connects families with professional home healthcare services. Built with pure HTML, CSS, and JavaScript — no backend, no build tools, no frameworks required.

> _"Providing the best in health at your doorstep."_

---

## ✨ Features

- **Service Catalog** — Browse four core home healthcare services with transparent pricing
- **Multi-Step Booking Flow** — Three-step guided booking: service selection → patient details → nurse selection
- **Nurse Directory** — Choose from verified, certified caregivers with photos, ratings, experience, and specialty filters (loaded from JSON)
- **Fee Calculator** — Instantly estimate total costs based on service type, shift duration, and number of days/visits
- **Contact Form** — Reach out with questions or custom requests
- **Fully Responsive** — Mobile-first design with hamburger menu, works across all screen sizes
- **Scroll Animations** — Smooth reveal-on-scroll effects and floating card animations

## 🩺 Services Offered

| Service | Pricing |
|---|---|
| 🧑‍⚕️ Home Nursing Attendant | ₹1,000/day (12hr) · ₹1,800/day (24hr) |
| 👴 Elder Caretaker | ₹1,200/day (12hr) · ₹2,000/day (24hr) |
| 🩹 Post-Surgery Wound Dressing | ₹500/visit |
| 🏃 Physiotherapy Visits at Home | ₹800/visit |

## 📁 Project Structure

```
CareAtHome/
├── index.html              # Landing page (hero, services, about, contact)
├── book-service.html       # Multi-step service booking with nurse selection
├── fee-calculator.html     # Interactive fee estimation tool
├── LICENSE                 # Apache License 2.0
├── README.md               # This file
└── assets/
    ├── nurse_details.json  # Nurse profiles data (name, certs, ratings, etc.)
    └── photos/             # Nurse profile photos
```

## 🛠 Tech Stack

This is a **frontend-only** static website — no server, no database, no build step.

| Technology | Purpose |
|---|---|
| **HTML5** | Semantic page structure and accessibility (ARIA labels) |
| **Tailwind CSS** (CDN) | Utility-first responsive styling |
| **Vanilla JavaScript** | DOM manipulation, form handling, multi-step wizard logic |
| **Font Awesome 6** (CDN) | Icons throughout the UI |
| **Google Fonts (Poppins)** | Typography |
| **JSON** | Nurse data stored in a static `nurse_details.json` file |

## 🚀 Getting Started

Since this is a static frontend project, you can run it instantly:

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/CareAtHome.git
   cd CareAtHome
   ```

2. **Open in browser**
   - Simply open `index.html` in any modern web browser, or
   - Use a local dev server for the best experience:
     ```bash
     # Using Python
     python -m http.server 8000

     # Using Node.js (npx)
     npx serve .
     ```
   - Then visit `http://localhost:8000`

> **Note:** A local server is recommended so that the `fetch()` call for `nurse_details.json` works correctly (some browsers block local file fetches due to CORS).

## 📄 Pages Overview

### `index.html` — Landing Page
- **Hero Section** — Dark gradient hero with stats (500+ families, 200+ caregivers, 24/7 support)
- **Services Section** — Four service cards with descriptions, starting prices, and "Book Now" CTAs
- **About Us Section** — Mission statement, values grid, and key highlights
- **Contact Section** — Contact info (phone, email, support hours) and a message form
- **Footer** — Quick links, service links, and social media icons

### `book-service.html` — Booking Page
- **Step 1** — Select a service (with shift type for nursing/elder care); shows description and price
- **Step 2** — Fill in patient details (name, age, email, phone, address, city, state, ZIP)
- **Step 3** — Browse and select a nurse from dynamically filtered cards (photo, rating, experience, certifications, languages)
- **Confirmation** — Success message with option to book another service

### `fee-calculator.html` — Fee Calculator
- Select service, shift type, and number of days/visits
- Instant cost breakdown with total estimate
- Quick pricing reference sidebar
- Direct "Book This Service" CTA linking to the booking page

## 📜 License

This project is licensed under the **Apache License 2.0** — see the [LICENSE](LICENSE) file for details.

---