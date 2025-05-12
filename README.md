# CSS3 Transitions, Animations, and Advanced JavaScript Functions

## Objectives

Create smooth CSS transitions and animations.
Use JavaScript functions for dynamic behavior.
Implement local storage for data persistence.

## Instructions
Add CSS animations to elements like buttons or images.

>[!NOTE]
> - Write a JavaScript function that:
> - Stores and retrieves user preferences using localStorage.
> - Implements an animation triggered by user actions.

## Tasks

Create a CSS animation.
Store data in localStorage.
Apply JavaScript to trigger animations.

Happy Coding! 💻✨


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Animated Page with Local Storage</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 20px;
      background-color: var(--bg, #ffffff);
      color: var(--color, #333);
      transition: background-color 0.5s ease, color 0.5s ease;
    }

    h1 {
      text-align: center;
    }

    .animated-button {
      display: block;
      margin: 20px auto;
      padding: 12px 24px;
      font-size: 18px;
      background-color: #0077cc;
      color: #fff;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.3s ease, background-color 0.3s ease;
    }

    .animated-button:hover {
      transform: scale(1.1);
      background-color: #005fa3;
    }

    .fade-in-box {
      opacity: 0;
      background-color: #d4af37;
      padding: 20px;
      border-radius: 10px;
      margin-top: 30px;
      text-align: center;
      transition: opacity 1s ease-in-out;
    }

    .visible {
      opacity: 1;
    }

    .theme-toggle {
      background: #222;
      color: #fff;
      border: none;
      padding: 10px 15px;
      margin-top: 30px;
      border-radius: 5px;
      cursor: pointer;
    }
  </style>
</head>
<body>

  <h1>🌟 Animated Page with Local Storage</h1>

  <!-- Button with animation and JS-triggered box -->
  <button class="animated-button" onclick="showBox()">Click to Trigger Animation</button>
  <div id="animatedBox" class="fade-in-box">🎉 Hello! I'm animated with CSS and JS.</div>

  <!-- Theme toggle button with localStorage -->
  <button class="theme-toggle" onclick="toggleTheme()">Toggle Light/Dark Theme</button>

  <script>
    // Show box with animation triggered by button
    function showBox() {
      document.getElementById("animatedBox").classList.add("visible");
    }

    // Toggle and store theme in localStorage
    function toggleTheme() {
      const currentTheme = localStorage.getItem("theme");
      if (currentTheme === "dark") {
        document.documentElement.style.setProperty('--bg', '#ffffff');
        document.documentElement.style.setProperty('--color', '#333');
        localStorage.setItem("theme", "light");
      } else {
        document.documentElement.style.setProperty('--bg', '#222222');
        document.documentElement.style.setProperty('--color', '#f4f4f4');
        localStorage.setItem("theme", "dark");
      }
    }

    // Load stored theme on page load
    window.onload = () => {
      const storedTheme = localStorage.getItem("theme");
      if (storedTheme === "dark") {
        document.documentElement.style.setProperty('--bg', '#222222');
        document.documentElement.style.setProperty('--color', '#f4f4f4');
      }
    };
  </script>

</body>
</html>
