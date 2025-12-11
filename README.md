# Soft Chrono ⏱️

![Project Status](https://img.shields.io/badge/status-active-success)
![License](https://img.shields.io/badge/license-MIT-blue)

A dual-purpose time tracking web application featuring a precise **Stopwatch** and a visual **Countdown Timer**. Designed with a "Soft UI" aesthetic, it offers a calming user experience with smooth transitions, multiple color themes, and responsive interactivity.

## ✨ Features

### ⏱️ Stopwatch
- **High Precision:** Tracks time down to 10 milliseconds.
- **Lap Functionality:** Record unlimited split times/laps without stopping the clock.
- **Smart Display:** Automatically adjusts format from `MM:SS.ms` to `HH:MM:SS.ms` for longer durations.
- **Soft Controls:** Play, Pause, and Reset with smooth icon transitions.

### ⏳ Timer
- **Custom Input:** Set hours, minutes, and seconds easily.
- **Visual Feedback:** Circular progress ring that visually depletes as time runs out.
- **Smart Controls:** Pause ("Jeda") and Resume ("Lanjut") functionality.
- **Audio Alarm:** Plays a sound notification when the timer hits zero.
- **Preset Buttons:** Quick-set functionality for common durations (1, 5, 10 minutes).

### 🎨 Theming
Personalize the look with 5 beautiful, pastel-inspired themes that persist via `localStorage`:
- **Matcha** (Default Green)
- **Berry** (Soft Pink)
- **Ocean** (Calm Teal)
- **Sunset** (Warm Orange)
- **Lavender** (Light Purple)

## 🛠️ Technologies Used

- **HTML5:** Semantic structure for the application.
- **CSS3:**
  - **CSS Variables:** For efficient theme switching.
  - **Flexbox/Grid:** For responsive layout.
  - **Animations:** Smooth fade-ins (`fade-in`) and transitions.
  - **Soft UI:** Custom box-shadows for a neomorphic/soft-card look.
- **JavaScript (ES6+):**
  - `localStorage` for saving theme preferences.
  - `setInterval` for precise time tracking.
  - DOM manipulation for real-time UI updates.
  - SVG manipulation for the timer progress ring.
- **External Libraries:**
  - **Phosphor Icons:** For clean, modern UI icons.
  - **Google Fonts:** Uses *Nunito* for UI text and *JetBrains Mono* for numbers.

## 📂 Project Structure

```
├── index.html   # Main application structure and layout
├── style.css    # Styling, themes, and animations
├── script.js    # Application logic (Timer, Stopwatch, Themes)
└── README.md    # Project documentation
```

## 🚀 How to Run

1. **Clone or Download** this repository.
2. Ensure all three files (`index.html`, `style.css`, `script.js`) are in the same folder.
3. Open `index.html` in any modern web browser.
4. **Enjoy!** Your theme preference will be saved automatically for your next visit.

## 🕹️ Usage Guide

### Switching Modes
Use the top tabs to switch between **Stopwatch** and **Timer** views. The active tab is highlighted.

### Changing Themes
Click on the colored theme buttons in the UI to instantly switch the color palette. This setting is saved in your browser.

### Using the Stopwatch
1. Click the **Play** icon to start.
2. Click **Lap** (flag icon) to record a split time while running.
3. Click **Pause** to stop the timer.
4. Click **Reset** to clear all data and return to zero.

### Using the Timer
1. Enter your desired duration using the input fields (Hours, Minutes, Seconds).
2. Or use the quick preset buttons (1m, 5m, 10m).
3. Click **Start**.
4. The interface shifts to a countdown view with a circular progress indicator.
5. Click **Jeda** (Pause) to pause, or **Lanjut** (Resume) to continue.
6. When the timer reaches zero, an alarm sound plays automatically.
7. Click **Reset** to return to the setup screen.

## 💡 Key Features Explained

### Theme System
The app uses CSS custom properties (`--bg-color`, `--primary`, etc.) defined in `:root` and theme-specific overrides using `[data-theme]` selectors. JavaScript updates the `data-theme` attribute on the `<body>` element and persists the choice in `localStorage`.

### Stopwatch Logic
- Uses `Date.now()` for accurate time tracking independent of `setInterval` delays.
- Updates display every 10ms for smooth millisecond counter.
- Laps are stored in an array and rendered dynamically with reverse indexing.

### Timer Logic
- Calculates total time in milliseconds from user input.
- Uses an SVG circle with `stroke-dashoffset` manipulation to create the visual progress ring.
- Updates every 100ms (sufficient for countdown precision).
- Plays an embedded audio element when countdown completes.

### Responsive Design
- Uses flexible units and percentage-based layouts.
- Custom scrollbar hiding for cleaner look.
- Tab navigation system with smooth transitions.

## 🎨 Customization

To add a new theme:

1. Open `style.css`
2. Add a new `[data-theme="your-theme-name"]` block with custom color variables
3. Update the HTML to include a button that calls `setTheme('your-theme-name')`

Example:
```css
[data-theme="mint"] {
  --bg-color: #E8F8F5;
  --card-bg: #FFFFFF;
  --primary: #48C9B0;
  --primary-dark: #17A589;
  --shadow-color: rgba(72, 201, 176, 0.3);
}
```

## 📱 Browser Compatibility

Works on all modern browsers that support:
- CSS Variables
- ES6 JavaScript
- LocalStorage API
- SVG manipulation

Tested on: Chrome, Firefox, Safari, Edge (latest versions).

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Created with ❤️ using Vanilla JavaScript, CSS3, and HTML5**
