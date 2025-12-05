# Technical Documentation: Portfolio Website (Assignment 3)

## Project Overview

### Description
This is the final advanced version of the Computer Science Portfolio Website, created for Assignment 3.  
It expands upon the work completed in Assignments 1 and 2 by introducing API integration, complex JavaScript logic, advanced state management, and performance optimization.

The website serves as a dynamic and interactive portfolio, showcasing personal details, skills, featured projects, and a fully validated contact form. It includes responsive layouts, animations, real-time weather information, and persistent user state.

### Technologies Used
- **HTML5** – Semantic structure and accessibility enhancements.  
- **CSS3** – Flexbox/Grid layouts, transitions, animations, and responsive design.  
- **JavaScript (ES6+)** – API fetching, DOM manipulation, event handling, asynchronous programming, and state management.  
- **External Tools & APIs**:
  - GoWeather API  
  - Browser Geolocation API  
  - Formspree  
  - Google Fonts  
  - LocalStorage  

### Purpose
Assignment 3 required transforming the portfolio into a highly interactive web application, demonstrating:
- API integration  
- Complex and maintainable JavaScript logic  
- Persistent state management  
- Advanced error/loading handling  
- Performance and optimization strategies  
- Proper documentation and responsible use of AI tools  

---

## Project Structure

```
Assignment-3/
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── assets/
│   ├── icons/
│   └── images/
├── docs/
│   ├── ai-usage-report.md
│   └── technical-documentation.md
└── README.md
```

---

## HTML Structure

- **Semantic Layout:**  
  Uses `<header>`, `<nav>`, `<main>`, `<section>`, and `<footer>` for accessible structure.

- **Sections Included:**
  1. Hero Section  
  2. Greeting Bar with weather widget  
  3. About Me  
  4. Skills  
  5. Projects with filter buttons  
  6. Contact Form  

- **New Assignment 3 Components:**
  - Weather display elements  
  - Weather loading/error placeholders  
  - Project filter buttons (`data-language` attributes)  
  - Greeting prefix element for personalized welcome-back messaging  

---

## CSS Architecture

- **Design Tokens:**  
  Variables for colors, spacing, transitions, fonts.

- **Responsive Breakpoints:**  
  Mobile, tablet, and desktop layouts.

- **Component Styling:**  
  - Weather widget styles  
  - Filter button states  
  - Card animations for filtering  

- **Animations:**  
  - Staggered transitions for filtered project cards  
  - Smooth fade-in animations for scrolling content  
  - Loading indicators for weather  

- **Accessibility Styles:**  
  - High-contrast color choices  
  - Visible focus outlines  

---

## JavaScript Functionality

### 1. Weather API Integration
- Attempts to detect user location via `navigator.geolocation`.  
- Falls back to Dhahran if location access fails.  
- Fetches weather data using:
  ```
  https://goweather.herokuapp.com/weather/{city}
  ```
- Uses three dedicated UI state functions:
  - `showWeatherLoading()`  
  - `showWeatherData()`  
  - `showWeatherError()`  
- Errors handled using `try/catch` for reliable fallback behavior.

### 2. Project Filtering System
- Projects contain `data-language` attributes (e.g., "python", "java", "web-design").  
- Filter buttons modify `currentFilter` and update button active states.  
- `filterProjects()`:
  - Applies animation classes (`filtered-out`, `filtered-in`).  
  - Uses an `isFiltering` flag to prevent overlapping animations.  
  - Supports “All” category to reset filters.

### 3. Welcome-Back Greeting System
- Saves the username using:
  ```
  localStorage.setItem('portfolioUserName', name);
  ```
- Detects returning users and updates the greeting prefix (`Welcome` → `Welcome back`).  
- Integrated through `showGreetingMessage()` and `initGreetingBar()`.

### 4. Contact Form Validation
- Inline validation for name, email, and message fields.  
- Email validation uses a regex pattern.  
- Displays error messages below each input.  
- Submits using Formspree via async `fetch`:
  ```
  fetch(form.action, { method: 'POST', ... })
  ```
- Includes loading and success/error UI states.

### 5. Scroll Animations
- Intersection Observer triggers fade-in animations when elements enter the viewport.  
- Enhances performance by animating only visible content.

### 6. Navigation Features
- Smooth scrolling to page sections.  
- Active link highlighting based on scroll position.  
- Mobile navigation toggle behavior.

---

## Accessibility and User Experience

- Keyboard-friendly navigation.  
- ARIA roles for dynamic components:
  - Weather section  
  - Live greeting region  
  - Form feedback  
- Error messages and loading indicators provide clarity and feedback.  
- Mobile responsiveness ensures readability across devices.  
- Thoughtful animations improve user engagement without overwhelming interaction.

---

## Performance and Optimization

### Key Improvements
- Added `defer` to main JavaScript file for non-blocking rendering.  
- Removed unused functions and logs to streamline execution.  
- Maintained small, optimized assets for fast loading.  
- Lightweight API usage with efficient DOM manipulation.  
- Hardware-accelerated CSS transitions (opacity, transform).  

### Lighthouse Performance
| Device | Score |
|--------|--------|
| Desktop | 100% |
| Mobile | 98–100% |

---

## Features Summary

| Feature | Description | Technology |
|--------|-------------|------------|
| Weather Integration | Real-time weather with loading/error states | JavaScript API Fetch |
| Project Filtering | Animated filtering by programming language | JS + CSS transitions |
| Welcome-Back Greeting | Persistent returning-user detection | LocalStorage |
| Contact Form | Inline validation + async submission | JS + Formspree |
| Scroll Animations | Lazy-loaded fade/slide-in animations | Intersection Observer |
| Responsive Layout | Mobile-first, scalable design | CSS Grid / Flexbox |
| Accessibility | Focus outlines, ARIA roles | HTML + CSS |

---

## Conclusion

The Assignment 3 portfolio successfully demonstrates advanced web engineering skills by integrating real-time APIs, implementing complex filtering logic, managing persistent user state, and optimizing performance for fast interaction.  
With well-structured HTML, modular CSS, and organized JavaScript, the website provides a seamless and dynamic user experience.  
