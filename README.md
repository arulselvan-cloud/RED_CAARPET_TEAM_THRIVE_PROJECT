# THE PULL — Algorithm Visualizer

> **"Your feed isn't showing you the world. It's showing you the shape of your own attention."**

An interactive web demo that makes the invisible mechanics of social media algorithms **visible and tangible**. In just 3 clicks, watch a filter bubble form in real time.

---

## 🎯 What Is This?

**The Pull** is a single-page interactive demonstration that simulates how a social media feed algorithm learns from your engagement. It reveals how a small number of casual "likes" compound into a visibly narrowed, self-reinforcing feed — a process that normally takes months but is compressed here into seconds.

Built for the **SKCET Internal Hackathon** by **Team Thrive (Red Carpet)**.

---

## ✨ Features

| Feature | Description |
|---|---|
| **18 Content Cards** | Across 8 categories — cats, sports, politics, cooking, tech, travel, fitness, music |
| **Live Weight Engine** | Each like adds +2.2 points to a category; percentages recalculate in real time |
| **5-Tier Visual Fade** | Cards scale and fade based on their category's weight (never disappear, just recede) |
| **Gravity Readout Panel** | Horizontal bars for all 8 categories + a dominant pull percentage |
| **Escalation Message** | After 3+ likes: *"X clicks. That's all it took to narrow your world."* |
| **Full Reset** | Restores neutral weights, reshuffles the feed, clears all state |
| **Keyboard Accessible** | Tab to every button, Enter/Space to engage, `aria-pressed` on all controls |
| **Offline-Ready** | Zero server dependencies — opens directly in any browser |

---

## 🧠 How the Algorithm Works

```
Initial State:  8 categories × 1.0 points each = 12.5% per category

User likes a "Cats" card:
  cats = 1.0 + 2.2 = 3.2
  total = 3.2 + (7 × 1.0) = 10.2
  cats % = 3.2 / 10.2 = 31.4%   ← jumped from 12.5% in one click

After 3 "Cats" likes:
  cats = 1.0 + (3 × 2.2) = 7.6
  total = 7.6 + 7.0 = 14.6
  cats % = 7.6 / 14.6 = 52.1%   ← over half the feed, from just 3 clicks
```

### Visual Styling Tiers

| Category Weight | Opacity | Scale | Position |
|---|---|---|---|
| > 30% | 1.0 | 1.0 | Top of feed |
| 15–30% | 0.85 | 0.95 | Upper-middle |
| 10–15% | 0.7 | 0.9 | Middle |
| 5–10% | 0.55 | 0.85 | Lower |
| < 5% | 0.4 | 0.8 | Bottom (faded) |

---

## 🚀 Getting Started

### Prerequisites

A web browser. That's it.

### Run Locally

```bash
# Clone the repository
git clone https://github.com/arulselvan-cloud/RED_CAARPET_TEAM_THRIVE_PROJECT.git

# Open the file
# On Windows:
start index.html

# On macOS:
open index.html

# On Linux:
xdg-open index.html
```

No build step. No server. No dependencies.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Structure** | Semantic HTML5 |
| **Styling** | Vanilla CSS (inline) — glassmorphism, backdrop-blur, CSS transitions |
| **Logic** | Vanilla JavaScript (inline) — event delegation, DOM diffing |
| **Typography** | Google Fonts — JetBrains Mono + Space Grotesk |
| **Animations** | `transform` + `opacity` only (GPU-composited, no layout thrash) |
| **Accessibility** | `aria-pressed`, `aria-live`, `role="list"`, `prefers-reduced-motion` |

**Zero frameworks. Zero build tools. One file.**

---

## 🎨 Design Language

- **Background**: Space-black `#08090C`
- **Structure / Chrome**: Cyan `#5EEAD4` — borders, brackets, labels
- **Data / Algorithm Signals**: Amber `#FF9F5B` — weight bars, dominant pull, liked states
- **Panels**: Glass effect with `backdrop-filter: blur(16px)`
- **Framing**: Corner-bracket decorations (L-shaped pseudo-elements)
- **Numbers**: Monospace (`JetBrains Mono`) for all live data
- **Overlay**: Dot-grid background + scanline effect for HUD aesthetic

---

## 📁 Project Structure

```
RED_CAARPET_TEAM_THRIVE_PROJECT/
├── index.html    ← The entire application (HTML + CSS + JS)
└── README.md     ← You are here
```

---

## 🔑 Edge Cases Handled

- **Single-like guard** — A card can only be liked once; re-clicking does nothing
- **All-liked category** — If every card in a category is liked, they stay at top without errors
- **Rapid clicks** — 10+ fast likes process correctly with no console errors
- **Reset integrity** — Fully restores randomized order, not just weights
- **Offline mode** — Fonts fall back to system stack; everything else works without network

---

## 💡 The Core Insight

```
Like → Weight Shift → Feed Re-orders → More of the same at top
  ↑                                                          |
  └──────────── You click more of the same ←─────────────────┘
```

**The self-reinforcing feedback loop:**

1. You like something → the algorithm promotes it
2. You see more of it → you're more likely to like it again
3. You like it again → the algorithm promotes it even more
4. Other content fades → you forget it existed

**This demo makes the invisible visible.** What normally takes months of silent tracking is compressed into 3 clicks and 10 seconds.

---

## 👥 Team Thrive — Red Carpet

Built at the **SKCET Internal Hackathon**.

| Member | Department | Section | Year |
|---|---|---|---|
| **Arulselvan M** | CSE | C | 2nd Year |
| **Sudharsan S** | CSE | C | 2nd Year |
| **Sudeep CG** | CSE | C | 2nd Year |

---

## 📄 License

This project is open source and available for educational purposes.
