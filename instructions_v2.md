# CareAtHome — Frontend Web Application: Build Instructions

## Project Overview

Build a **responsive, multi-page frontend web application** called **"Care At Home"** — a platform for booking home nursing attendants and elder caretakers.

- **Tech Stack:** HTML, CSS (Tailwind CSS), and vanilla JavaScript only. No backend required.
- **Data Handling:** All form submissions are simulated on the client side (no real API calls). Show a success message on submit.
- **Tone & UI:** Healthcare-focused — calm, trustworthy, and professional.

---

## Tech Stack & Styling Rules

| Concern        | Choice                                      |
|----------------|---------------------------------------------|
| Structure      | Semantic HTML5                              |
| Styling        | Tailwind CSS (via CDN)                      |
| Logic          | Vanilla JavaScript (no frameworks)          |
| Fonts          | Google Fonts — Poppins, Roboto, or Inter    |
| Color Palette  | White, soft blue, soft green, grey          |
| Icons          | Optional (e.g., Font Awesome or Heroicons)  |

---

## Page Structure

The app consists of the following **HTML pages**:

1. **`index.html`** — Main page containing: Hero, About Us, Services, Contact Us, and Footer sections
2. **`book-service.html`** — Dedicated "Book a Service" page
3. **`fee-calculator.html`** — Dedicated "Fee Calculator" page

---

## 1. Navbar

A fixed/sticky top navigation bar containing:

- **Logo** — icon + app name "Care At Home" (left-aligned)
- **Nav Links** (right-aligned):
  - Home (scrolls to top / Hero section)
  - Services (scrolls to Services section)
  - About Us (scrolls to About Us section)
  - Contact Us (scrolls to Contact Us section)
- **Action Buttons** (right of nav links):
  - `Fee Calculator` — navigates to `fee-calculator.html`
  - `Book a Service` — navigates to `book-service.html` (styled as primary CTA button)

---

## 2. Hero Section

Full-width banner section at the top of the page.

- **Tagline (H1):** `Book a Service for Your Loved One`
- **Subtext:** `Get all your home healthcare needs at one place. Providing the best in health at your doorstep. We take care of you with expertise and compassion.`
- **CTA Button:** `Book a Service` → navigates to `book-service.html`

---

## 3. About Us Section

A section with a short paragraph describing the company.

- **Heading:** `About Us`
- **Body Text:** `We are a team of dedicated professionals who are passionate about providing quality healthcare services to our patients. We believe that everyone deserves to receive the best possible care, and we are committed to delivering it with expertise and compassion.`

---

## 4. Services Section

Display all 4 services as a **responsive grid of cards** (2 columns on tablet, 4 on desktop).

Each card contains:
- Service icon (representative emoji or SVG icon)
- Service name
- Short one-line description
- `Book Now` button → navigates to `book-service.html` with the service **pre-selected** (pass service name as a URL query parameter, e.g. `book-service.html?service=home-nursing-attendant`)

### Service List

| # | Service Name                     | Short Description                                              |
|---|----------------------------------|----------------------------------------------------------------|
| 1 | Home Nursing Attendant           | Professional care at home for 12 or 24 hours.                 |
| 2 | Elder Caretaker                  | Comprehensive support for seniors, available 12 or 24 hours.  |
| 3 | Post-Surgery Wound Dressing      | Certified nurse visits for wound care and dressing changes.    |
| 4 | Physiotherapy Visits at Home     | Licensed physiotherapist visits for rehabilitation at home.    |

---

## 5. Contact Us Section

A simple contact form embedded in the page (not a modal).

**Fields:**
- Full Name
- Email Address
- Phone Number
- Message (textarea)
- `Send Message` button

On click of `Send Message` → display an inline success message: `"Thank you! We'll get back to you shortly."`

---

## 6. Footer

- App name + tagline
- Quick links (Home, Services, About Us, Contact Us)
- Social media icons (Facebook, Instagram, Twitter/X — placeholder links)
- Copyright: `© 2024 Care At Home. All rights reserved.`

---

## 7. Book a Service Page (`book-service.html`)

A **dedicated full page** for booking a service. Navigated to from any "Book a Service" or "Book Now" button. The page shares the same Navbar and Footer as `index.html`.

On page load, read the `service` query parameter from the URL (if present) and pre-select the matching option in the "Select Service" dropdown.

### Page Layout

**Step 1 — Service Selection (dynamic form)**

| Field | Type | Notes |
|---|---|---|
| Select Service | Dropdown | Options: Home Nursing Attendant, Elder Caretaker, Post-Surgery Wound Dressing, Physiotherapy Visits at Home |
| Shift Type | Dropdown | Only shown for services 1 & 2. Options: 12-Hour Duty, 24-Hour Duty |
| Service Description | Read-only text block | Auto-updates based on selected service (see descriptions below) |
| Price | Read-only text | Auto-updates based on selected service + shift type (see pricing below) |

**Step 2 — Booking Form Fields**

| Field | Type |
|---|---|
| Full Name | Text input |
| Email Address | Email input |
| Phone Number | Tel input |
| Address | Text input |
| City | Text input |
| State | Text input |
| ZIP Code | Text input |
| Submit Button | `Confirm Booking` |

On submit → show an **inline success message** on the page: `"Your booking has been submitted successfully! We will contact you shortly."` and reset the form.

### Service Descriptions

**1. Home Nursing Attendant**
> We provide trained and compassionate home nursing attendants for both 12-hour and 24-hour shifts. Our attendants assist with daily activities, medication reminders, mobility support, and companionship to ensure your loved one receives professional care in the comfort of their own home.

**2. Elder Caretaker**
> Our elder caretakers offer comprehensive support for seniors, helping them maintain independence and quality of life. Services include meal preparation, personal care, light housekeeping, companionship, and monitoring of health conditions. Available in both 12-hour and 24-hour care.

**3. Post-Surgery Wound Dressing**
> Professional wound care services provided by certified nurses at your doorstep. We handle post-surgical wound dressing, dressing changes, and wound care for various types of wounds to promote healing and prevent infections. Available as per requirement.

**4. Physiotherapy Visits at Home**
> Receive expert physiotherapy care in the convenience of your home. Our licensed physiotherapists provide personalized treatment plans, including therapeutic exercises, manual therapy, and rehabilitation programs to help you recover from injury, manage pain, and improve mobility.

### Pricing Table

| Service | Option | Price |
|---|---|---|
| Home Nursing Attendant | 12-Hour Duty | ₹1,000 / day |
| Home Nursing Attendant | 24-Hour Duty | ₹1,800 / day |
| Elder Caretaker | 12-Hour Duty | ₹1,200 / day |
| Elder Caretaker | 24-Hour Duty | ₹2,000 / day |
| Post-Surgery Wound Dressing | Per Visit | ₹500 / visit |
| Physiotherapy Visits at Home | Per Visit | ₹800 / visit |

---

## 8. Fee Calculator Page (`fee-calculator.html`)

A **dedicated full page** for estimating service fees. Navigated to from the `Fee Calculator` navbar button. The page shares the same Navbar and Footer as `index.html`.

### Calculator Fields

| Field | Type | Notes |
|---|---|---|
| Select Service | Dropdown | Same 4 services as above |
| Shift Type | Dropdown | Only shown for services 1 & 2. Options: 12-Hour Duty, 24-Hour Duty |
| Number of Days | Number input | Only shown for services 1 & 2 |
| Number of Visits | Number input | Only shown for services 3 & 4 |

### Output

After clicking `Calculate`:
- Display an **inline result section** on the page with a breakdown:
  - Selected Service
  - Rate per day / per visit
  - Duration (days or visits)
  - **Total Estimated Cost: ₹XXXX**

Include a `Reset` button to clear the form and result.

---

## UI / Design Guidelines

- **Color Palette:** Soft blues (`#4A90D9`), soft greens (`#4CAF80`), whites, and light grays.
- **Font:** Poppins or Inter via Google Fonts.
- **Cards:** Rounded corners (`rounded-xl`), subtle shadow (`shadow-md`), hover lift effect.
- **Buttons:** Rounded pill-style or rounded corners, clear hover states.
- **Page Transitions:** Smooth fade-in animation when `book-service.html` and `fee-calculator.html` load.
- **Responsiveness:** Mobile-first. Stack sections/cards vertically on small screens.
- **Accessibility:** Use ARIA labels on modals and form fields. All interactive elements must be keyboard-navigable.