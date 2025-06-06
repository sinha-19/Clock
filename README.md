# 🕒 Clock Web App

A simple, responsive clock web application that displays both an analog and digital clock. Built using pure HTML, CSS, and JavaScript, and easily deployable with GitHub Pages.

---

## 🖼️ Workflow Diagram

The internal workflow of the Clock Web App is illustrated below:

![Clock Workflow Diagram](Clock%20Workflow%20Digram.png)

---

## 🚀 Live Demo

> _Replace this link with your GitHub Pages deployment URL if published_
>
> [https://sinha-19.github.io/clock](https://sinha-19.github.io/clock)

---

## 📂 Project Structure

```
clock/
├── index.html                  # Main HTML file
├── style.css                   # CSS for styling the clock
├── Clock Workflow Digram.png   # Workflow diagram image
└── README.md                   # Project documentation
```

---

## 🛠️ How It Works

1. **User opens the Clock web app in their browser.**
2. **GitHub Pages** hosts and serves the static website.
3. **index.html** loads as the main entry point.
4. **style.css** is loaded for styling the analog and digital clocks.
5. **JavaScript** (inside index.html) runs to calculate and update the current time.
6. The app provides:
   - **Analog Clock:** Animated hour, minute, and second hands.
   - **Digital Clock:** Real-time textual display of the current time.
7. The UI updates every second to reflect the current time.

---

## 📝 Usage

### 1. Clone this repository

```sh
git clone https://github.com/sinha-19/clock.git
cd clock
```

### 2. Run the app

Open `index.html` in your web browser.

---

## 📦 Deployment (GitHub Pages)

1. Commit and push your code to the `main` or `master` branch of your repository.
2. Go to **Settings > Pages** in your GitHub repository.
3. Set the source to your main or master branch (`/root`).
4. GitHub will provide a link to your live site.

---

## 💻 Example Code Overview

### HTML (index.html)

```html
<div class="clock-container">
  <div class="analog-clock">
    <div class="hand hour"></div>
    <div class="hand minute"></div>
    <div class="hand second"></div>
    <div class="center-dot"></div>
  </div>
  <div class="digital-clock" id="digitalClock"></div>
</div>
```

### CSS (style.css)

```css
.analog-clock {
  width: 200px;
  height: 200px;
  border: 8px solid #333;
  border-radius: 50%;
  position: relative;
  margin: 0 auto;
}
.hand {
  position: absolute;
  width: 50%;
  background: #333;
  top: 50%;
  transform-origin: 100%;
  transform: rotate(90deg);
  transition: all 0.1s cubic-bezier(0.4,2.3,0.3,1);
}
.hour { height: 4px; }
.minute { height: 3px; }
.second { height: 2px; background: #e74c3c;}
.center-dot {
  width: 12px; height: 12px; background: #333; border-radius: 50%;
  position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
}
```

### JavaScript (in index.html)

```js
function updateClock() {
  const now = new Date();
  const sec = now.getSeconds();
  const min = now.getMinutes();
  const hr = now.getHours();

  // Analog
  document.querySelector('.hand.hour').style.transform =
    `rotate(${(hr % 12) * 30 + min * 0.5}deg)`;
  document.querySelector('.hand.minute').style.transform =
    `rotate(${min * 6}deg)`;
  document.querySelector('.hand.second').style.transform =
    `rotate(${sec * 6}deg)`;

  // Digital
  document.getElementById('digitalClock').textContent =
    now.toLocaleTimeString();
}
setInterval(updateClock, 1000);
updateClock();
```

---

## 📜 License

MIT License

---

## 🙏 Credits

- Developed by [sinha-19](https://github.com/sinha-19)
- Workflow diagram included in this repository.

---

> _Feel free to customize this README for your own deployment or enhancements!_
