# 🌍 World Clocks – OBS Browser‑Source Overlay

A tiny, self‑contained HTML overlay that shows live clocks for multiple time‑zones.  
Perfect for streamers who want to display local time, guest time, or event time on‑screen in **OBS Studio**.

---

## Features
* Live date & time for any city / IANA time‑zone (powered by `moment‑timezone`)
* Emoji flags (auto‑converted to Twemoji SVG for crisp rendering)
* Clean, fully right‑aligned layout – great for a panel or corner overlay
* Easily themeable with **OBS “Custom CSS”** or by editing the file

---

## Quick Start

1. Download (or clone) the repo.
2. In OBS **Sources ➜ + ➜ Browser**, pick `index.html` as the URL  
   (or click **Local File** and browse to it).  
   Recommended size: **640 × 240** – you can resize freely.
3. Done – the clocks start ticking immediately. ✅

---

## Configuration

### 1. Choose your cities  
Open `index.html` and edit the `cities` array:

```js
const cities = [
  { id:'Seoul',  zone:'Asia/Seoul',       flag:'🇰🇷' },
  { id:'Sydney', zone:'Australia/Sydney', flag:'🇦🇺' },
  { id:'NYC',    zone:'America/New_York', flag:'🇺🇸' },
];
```

`id` becomes the visible label.  
`zone` must be a valid IANA time‑zone string.

### 2. URL parameters
* `?flag=0` – hide flags  
* `?flagPos=right` – show the flag after the city name

Example:  
`index.html?flag=0` (no flags)  
`index.html?flagPos=right` ( Tokyo🇯🇵 instead of  🇯🇵Tokyo )

### 3. OBS “Custom CSS”
Paste any CSS in **Browser Source ➜ Custom CSS** to override colours, fonts, gaps, etc.

```css
:root{
  --clock-color:#ffe066;                  /* text + divider colour   */
  --label-font:"Comic Neue", sans-serif;  /* city + date font        */
  --time-font:"Comic Neue", sans-serif;   /* time font               */
  --gap:2rem;                             /* extra spacing           */
}
```

OBS injects this after the built‑in styles, so these rules take precedence.
