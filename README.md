Here is a comprehensive `README.md` file for your **Soft Chrono** project. It is structured to explain the features, the technology stack, and how the code works, making it perfect for a portfolio or GitHub repository.

````markdown
# Soft Chrono ⏱️

**Soft Chrono** is a lightweight, aesthetically pleasing Stopwatch and Timer web application. Built with a focus on "Soft UI" design principles, it features smooth transitions, a calming color palette, and precise timekeeping capabilities without requiring a complex build process.

![Project Status](https://img.shields.io/badge/status-active-success.svg)
![License](https://img.shields.io/badge/license-MIT-blue.svg)

## 🌟 Overview

This project demonstrates how to build a fully functional, interactive web utility using a **Single File Component** approach. All HTML structure, CSS styling, and JavaScript logic are encapsulated within a single `.html` file, making it incredibly portable and easy to deploy.

## ✨ Features

### 1. ⏱️ Stopwatch
* **Precision Timing:** Tracks time down to the millisecond.
* **Lap Functionality:** Record multiple laps without stopping the timer.
* **Scrollable History:** View your lap history in a clean, scrollable list.
* **Persistent Display:** dynamic formatting that adjusts based on the duration (switching focus between Minutes/Seconds and Hours/Minutes).

### 2. ⏳ Timer
* **Visual Countdown:** A beautiful SVG-based circular progress bar that depletes as time runs out.
* **Quick Presets:** One-click buttons for common durations (5m, 10m, 25m).
* **Custom Input:** Set specific Hours, Minutes, and Seconds.
* **Audio Alert:** Plays a sound when the timer reaches zero.

### 3. 🎨 Dynamic Theming
* **5 Color Palettes:** Switch instantly between *Matcha*, *Berry*, *Ocean*, *Sunset*, and *Lavender*.
* **Persistence:** The app remembers your chosen theme using `localStorage`, so it stays the same when you refresh the page.
* **Smooth Transitions:** CSS variables enable smooth color morphing when switching themes.

### 4. 📱 Responsive & Modern
* **Mobile First:** optimized for both desktop and mobile screens.
* **Glassmorphism:** subtle transparency and blur effects on floating elements.
* **Soft UI (Neumorphism-inspired):** soft shadows and rounded corners for a tactile feel.

---

## 🛠️ Tech Stack

* **Core:** HTML5, Vanilla JavaScript (ES6+)
* **Styling:** * **Tailwind CSS (via CDN):** For rapid utility-first styling and layout.
    * **Custom CSS:** For complex animations, CSS Variables (Theming), and specific UI tweaks.
* **Icons:** [Phosphor Icons](https://phosphoricons.com/) (Web/CDN).
* **Fonts:** * *Nunito* (Google Fonts) for UI text.
    * *JetBrains Mono* (Google Fonts) for tabular numbers to prevent jittering.

---

## 🚀 Getting Started

Since this is a single-file application, no installation or build steps (like `npm install`) are required.

### Prerequisites
A modern web browser (Chrome, Firefox, Safari, Edge).

### Installation
1.  Download the `index.html` file.
2.  Double-click to open it in your browser.
3.  **That's it!** The app is ready to use.

---

## 📂 Code Structure Explained

The project is contained entirely in `index.html`. Here is how the code is organized:

### 1. CSS Variables & Theming (`<style>`)
We use CSS Root Variables to define the theme colors. When a user clicks a theme button, JavaScript updates the `data-theme` attribute on the `body`, which changes these variable values.

```css
:root {
    --primary: #99D98C; /* Default Matcha Color */
}
[data-theme="berry"] {
    --primary: #FFB3C1; /* Berry Color Override */
}
````

### 2\. Application Logic (`<script>`)

#### State Management

Simple variables track the state of the stopwatch and timer.

```javascript
let swRunning = false; // Is stopwatch running?
let tmRemaining = 0;   // Time remaining in milliseconds
```

#### The Timer Loop

The timer uses `Date.now()` logic rather than simple `setInterval` counting to ensure accuracy even if the browser slows down.

```javascript
// Calculates difference between End Time and Current Time
tmRemaining = tmEndTime - Date.now();
```

#### SVG Animation

The circular progress bar is animated by manipulating the `stroke-dashoffset` property of an SVG circle based on the percentage of time remaining.

### 3\. Fonts Strategy

We use **JetBrains Mono** specifically for the numbers (`.font-mono-nums`). This is a monospaced font, which ensures that the width of the time display doesn't jump around as the numbers change (e.g., a "1" taking up less space than a "0").

-----

## 🤝 Contributing

Feel free to fork this project\! Ideas for improvements:

1.  Add a "Dark Mode" specific theme.
2.  Add keyboard shortcuts (Spacebar to Start/Stop).
3.  Save the Timer presets in LocalStorage.

## 📄 License

This project is open-source and available under the **MIT License**.

-----

*Created with ❤️ by [Erick]*

```
```
