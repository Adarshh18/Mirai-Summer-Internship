<div align="center">

# ✨ Calcy

### A calculator, but make it *glow*.

A glassmorphism-themed calculator built entirely in **Streamlit** — animated gradients, floating orbs, glowing displays, and buttery-smooth interactions. No JavaScript framework, no build step, just Python.

[![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.59-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](CONTRIBUTING.md)

<img src="docs/preview.png" alt="Calcy preview" width="480">

*(Drop a screenshot or screen recording at `docs/preview.png` — a quick GIF of the theme switch + button glow sells it instantly.)*

</div>

---

## 🌈 Features

| | |
|---|---|
| 🪟 **Glassmorphism UI** | Frosted-glass display panel with blur, soft shadows, and layered depth |
| 🌌 **Animated aurora background** | Slow-shifting gradient with three drifting, blurred light orbs |
| 🎨 **3 built-in themes** | `Aurora`, `Sunset`, and `Ocean` — swap instantly from a dropdown |
| ✨ **Shimmering title text** | Gradient text animation that never sits still |
| 💫 **Glow-pulse on result** | The display pulses with a soft glow every time you hit `=` |
| 🧮 **Full operator set** | `+  −  ×  ÷  %  √  ±` plus clear (`AC`) and backspace (`⌫`) |
| 🛡️ **Bulletproof input handling** | Blocks double operators, stray decimals, and leading operators — no more `Error` spam |
| 🕘 **Live history panel** | Your last 6 calculations, animated in as they happen |
| 📱 **Responsive, chrome-free layout** | Streamlit's menu/footer/header are hidden for an app-like feel |

---

## 🚀 Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/<your-username>/calcy.git
cd calcy

# 2. (Optional) create a virtual environment
python -m venv venv
source venv/bin/activate      # Windows: venv\Scripts\activate

# 3. Install dependencies
pip install streamlit

# 4. Run it
streamlit run app.py
```

Calcy will open automatically at **http://localhost:8501** 🎉

---

## 🧠 How It Works

Calcy is a single-file Streamlit app (`app.py`) built around three pieces:

1. **Theming engine** — a `THEMES` dictionary defines colors per theme (background gradient stops, accent colors, glow color). CSS is generated dynamically from whichever theme is active in `st.session_state`.
2. **Custom CSS injection** — `st.markdown(..., unsafe_allow_html=True)` injects a `<style>` block that restyles Streamlit's native buttons, containers, and layout into the glass/aurora look, plus keyframe animations for the background, title shimmer, and result glow.
3. **State machine calculator** — button presses run through a single `press()` function that manages the expression string in `st.session_state`, validates input (no double operators, no stray decimals), evaluates safely with a restricted `eval`, and pushes results into a rolling history list.

---

## 🎨 Themes

| Aurora | Sunset | Ocean |
|:---:|:---:|:---:|
| Purple → Cyan | Crimson → Amber | Deep Teal → Sky Blue |

Switch anytime from the dropdown at the top of the app — no reload needed.

---

## 🗂️ Project Structure

```
calcy/
├── app.py            # The entire app — UI, styling, and logic
├── README.md          # You are here
└── docs/
    └── preview.png     # Screenshot / demo GIF for this README
```

---

## 🛣️ Roadmap

- [ ] Scientific mode (`sin`, `cos`, `log`, `ln`, `x²`, `xʸ`)
- [ ] Physical keyboard input support
- [ ] Light-mode theme
- [ ] Persistent history across sessions (local storage / file)
- [ ] Copy-to-clipboard on result
- [ ] Custom theme builder (pick your own accent colors)

Have an idea? Open an [issue](../../issues) — contributions are very welcome.

---

## 🤝 Contributing

1. Fork the repo
2. Create a branch: `git checkout -b feature/my-idea`
3. Commit your changes: `git commit -m "Add my idea"`
4. Push and open a Pull Request

---

## 📄 License

Released under the [MIT License](LICENSE) — do whatever you'd like with it, just keep the credit.

---

<div align="center">

Built with 🐍 Python, 🎈 Streamlit, and an unreasonable love for gradients.

If Calcy made you smile, consider ⭐ starring the repo!

</div>
