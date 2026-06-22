# 🚀 Curiosity Lab

> **Awe and Curiosity are the two main prerogatives of this built. If the kids (8-12 yo) learn something then - Bravo!! But wonder and amazement is the anchor of this site.**

> Playful, hands-on web activities that teach big ideas to curious kids aged **8–12**.

Curiosity Lab is a small collection of self-contained, browser-based learning games.
No installs, no accounts, no data collection — just open a page and play. Each activity
is built to deliver one real "aha!" moment about how the world (and computers) work,
guided by a friendly robot mascot named **Bit**.

---

## 🎮 The Activities

| Activity | What kids learn | The "aha!" |
|---|---|---|
| **🪐 Solar System Explorer** | The planets, moons and scale of our Solar System | Space is huge — and beautiful |
| **💡 Binary Lights** | How computers count using only 1s and 0s | "16 looks like **10000** to a computer!" |
| **🔢 Mathe-Magic Squares** | Magic squares & the Siamese method | Every row, column and diagonal can add to the same magic number |

A friendly **Landing** page ties them together so kids can pick their own adventure.

---

## ✨ Design principles

- **One idea per activity.** Each game drives toward a single, memorable insight.
- **Show, don't tell.** Kids discover rules by doing — tapping bulbs, placing tiles, watching the "dance."
- **Always encouraging.** Wrong answers get a gentle "Oops!" from Bit plus a visual hint, never a penalty.
- **Reward the win.** Correct moves get a satisfying sound and a celebratory reveal.
- **Readable & touch-friendly.** Large type, big tap targets, and layouts that fit one screen without awkward scrolling.

---

## 🗂 Project structure

```
.
├── index.html                    # Entry point
├── Landing.dc.html               # "Pick your adventure" hub
├── Solar System Explorer.dc.html # Activity
├── Binary Lights.dc.html         # Activity
├── Mathe-Magic Squares.dc.html   # Activity
├── support.js                    # Shared runtime (do not edit)
├── CLAUDE.md                     # Project conventions / defaults
├── README.md                     # You are here
├── CONTRIBUTING.md               # How to add or change activities
└── LICENSE                       # MIT
```

Each activity is a single `.dc.html` file — open it directly in a browser and it runs.
Files are self-contained except for the shared `support.js` runtime and Google Fonts.

---

## ▶️ Running it

No build step. Either:

- **Open directly** — double-click `index.html` (or any `*.dc.html`) in a browser, or
- **Serve locally** (recommended, avoids file:// quirks):

  ```bash
  # from the project root
  python3 -m http.server 8000
  # then visit http://localhost:8000
  ```

Works in Chrome, Edge, Firefox, and Safari (desktop + iPad/iPhone).

---

## 🔊 A note on sound

Browsers block audio until the user interacts with the page. Every activity with sound
unlocks audio on the **first tap** anywhere — so sound plays reliably from then on.

- The first tap just *unlocks* audio; sound starts from the next interaction (this feels natural in play).
- On **iPhone**, make sure the side **silent switch** is off and the volume is up.

See `CLAUDE.md` for the exact pattern, which is applied to every activity by default.

---

## 🎯 Audience & accessibility

- **Ages 8–12**, readable independently by most; great for classrooms or at home.
- Simple language, generous sizing, and color + motion used to support (not replace) meaning.
- No login, no ads, no tracking, no external data.

---

## 📄 License

Released under the **MIT License** — see [LICENSE](LICENSE). Use it, remix it, teach with it.

Made with curiosity by [@chetandudhane](https://github.com/chetandudhane) 🤖
