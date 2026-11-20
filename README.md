<div align="center">

# 🏁 MarioKart

### A racing scene brought to life with nothing but HTML and CSS

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-none-brightgreen?style=for-the-badge)
![Dependencies](https://img.shields.io/badge/dependencies-zero-yellow?style=for-the-badge)

**[▶ Watch the race live](https://karltayycodes.github.io/MarioKart/)**

</div>

<!--
  PREVIEW: record a short GIF of the page, save it as img/preview.gif,
  then delete the comment markers around the line below.

  ![MarioKart preview](img/preview.gif)
-->

---

## 🎮 What is this?

Two racers, one road, and a sky full of drifting clouds, all animated with **pure CSS**. No JavaScript, no frameworks, no build step. Open the page and the race starts on its own.

It's a small project built to practice CSS animation: layering a scene, moving elements at different speeds, and chaining multiple animations on a single element.

## ✨ What's happening on screen

| Element | What it does |
|---|---|
| 🔴 **Mario** | Races across the road on a 3-second loop, and hops once as the page loads |
| 🟢 **Luigi** | Cruises along the lower lane on a slower 5-second loop |
| ☁️ **Clouds** | Two clouds drift across the sky at different speeds (50s and 80s), and the smaller one is semi-transparent for a sense of depth |
| 🛣️ **Road** | Gray track with a dashed white center line |
| 🌱 **Scenery** | Blue sky, green grass strip, all sized with percentages so the scene fills any screen height |

## 🧠 How it works

The whole scene is three horizontal bands that split the screen **40% / 30% / 30%** (sky, grass, road). The racers and clouds are absolutely positioned inside them and moved with `@keyframes`.

**One keyframe, two speeds.** Mario and Luigi share the same `drive` animation. Only the duration differs, so Mario laps Luigi:

```css
.mario { animation: drive 3s both infinite linear, jump 0.3s 1.2s ease; }
.luigi { animation: drive 5s both infinite linear; }
```

**Two animations on one element.** Mario runs `drive` (looping forever) and `jump` (once, after a 1.2s delay) at the same time, separated by a comma.

**Different clouds, same trick.** Both clouds share the `wind` animation, played in reverse over 50s and 80s, so they drift apart and never line up.

### The three keyframes

| Keyframe | Job |
|---|---|
| `drive` | Slides a racer from off-screen left (`-350px`) to off-screen right (`1700px`) |
| `wind` | Drifts a cloud across the sky (played in `reverse`, so clouds float right to left) |
| `jump` | Lifts Mario up and back down, a quick hop |

## 📁 Project structure

```
MarioKart/
├── index.html      # Scene markup: sky, grass, road, racers
├── style.css       # Layout, colors and all animations
└── img/
    ├── mario.png
    ├── luigi.png
    └── cloud.png
```

## 🚀 Run it

No installs needed.

```bash
git clone https://github.com/karltayycodes/MarioKart.git
cd MarioKart
```

Then just **double-click `index.html`** to open it in your browser.

## 🛠️ Make it your own

Everything lives in `style.css`. Try these tweaks:

| Want to... | Change this |
|---|---|
| Make Mario faster or slower | The `3s` in `.mario { animation: drive 3s ... }` |
| Make Luigi faster or slower | The `5s` in `.luigi { animation: drive 5s ... }` |
| Make the jump higher | The `-100px` in `@keyframes jump` (50% step) |
| Change when the jump happens | The `1.2s` delay in `.mario` |
| Speed up the clouds | The `50s` / `80s` in `.cloud:nth-child(...)` |
| Change the scenery colors | `skyblue`, `seagreen` and `gray` on `.sky`, `.grass`, `.road` |
| Rebalance the layout | The `40%` / `30%` / `30%` heights |

## 🗺️ Ideas for next laps

- [ ] Make the racers cross any screen width (swap the fixed `1700px` for a viewport-based value)
- [ ] Add a third racer with its own speed
- [ ] Scroll the center line so the road feels like it's moving
- [ ] Add a `:hover` effect that makes a racer boost
- [ ] Animate with `transform` instead of `left` / `top` for smoother performance
- [ ] Respect `prefers-reduced-motion` for viewers who prefer less movement

## 📌 Disclaimer

This is a fan-made learning project and is not affiliated with or endorsed by Nintendo. Mario, Luigi and Mario Kart are trademarks of Nintendo.

---

<div align="center">

Built with ❤️ and a lot of keyframes by [@karltayycodes](https://github.com/karltayycodes)

⭐ If this made you smile, drop a star!

</div>
