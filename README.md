**Application Support Engineer** · Canton, MA · Seeking hybrid/on-site roles in Boston

I spend my days keeping financial systems alive (production support, incident triage, Control-M, ServiceNow, SQL) — and my evenings building things that shouldn't exist yet.

---

## 🛠 What I Build

### 🛡️ [SentinelWatch](https://github.com/azaurov/sentinelwatch) — AI Process Monitor
> *Electron · Node.js · Anthropic Claude API · PowerShell · ps aux*

Cross-platform desktop app that polls live OS processes every 5 seconds, detects hangs via CPU-delta analysis over configurable windows, and surfaces **Claude AI-generated triage recommendations** on demand — with one-click process kill. Works on Windows (PowerShell `Get-Process`) and Linux/macOS (`ps aux`). Secure `contextIsolation` IPC architecture.

---

### 🤖 [AI Resume & Cover Letter Builder](https://github.com/azaurov/resume-builder) — Claude-Powered PWA
> *React · Vite · Node.js/Express · Anthropic Claude API · Prompt Caching*

Full-stack PWA that reads your profile + a job description and generates a tailored resume and cover letter in under 60 seconds. Features live token tracking, a debug panel, and PDF export. Prompt caching cuts API latency significantly on repeat calls.

---

### 📱 [DoomscrollGuard](https://github.com/azaurov/doomscrollguard) — Android Accessibility App
> *Kotlin · Android SDK · AccessibilityService · ViewBinding · Material 3 · Firebase*

Production-quality Android app (Kotlin, ViewBinding, Material 3) using `AccessibilityService` to detect doomscrolling via a sliding-window scroll-event counter across 13 tracked social media apps. Fires a `NotificationCompat` alert mirrored to an Amazfit GTR 3 via Zepp. Fully configurable thresholds (scroll count, time window, cooldown) persisted via `SharedPreferences`. Includes `BootReceiver` for post-reboot resilience. Privacy-first: zero content read — scroll event counts only. Built in `Android Studio`, versioned on `GitHub`, with `Firebase` project integration.

---

### 💧 HydroReminder — Android WorkManager App
> *Kotlin · Jetpack WorkManager · Android Notification API*

Hydration reminder app using Jetpack `WorkManager` for reliable background scheduling and persistent notification delivery — targeting correct behavior across Android battery optimization constraints.

---

### 🌍 [Bukharian Language Learning App](https://github.com/azaurov/SilkRoadDuo) — Duolingo-style
> *Expo · React Native · TypeScript*

Cross-platform mobile app for **Bukharian Judeo-Tajik, Farsi, and Sogdian** — endangered languages with virtually no existing app coverage. Gamified lessons, vocabulary decks, hearts/XP/streaks, and four game modes. CEFR A1–B1 scaffolding.

---

### 🎨 AI Photo Colorization Tool
> *Vanilla JS · Claude Vision API · Canvas API*

Web tool that uses Claude Vision for semantic region detection (sky, skin, foliage, fabric) and Canvas API pixel manipulation to colorize black-and-white photos with luminance-preserving blending. Includes a before/after comparison slider and graceful API-failure fallback to luminance-only mode.

---

### ⚛️ Interactive Quantum Mechanics Simulator
> *React · Expo · Canvas/SVG*

Visualizes wave functions, superposition states, and measurement collapse interactively. Built out of curiosity; shipped because why not.

---

### 📖 Illustrated Ancestral Storybook PDFs
> *Python · ReportLab · Noto Fonts · BiDi/RTL*

Three programmatically generated illustrated PDF storybooks — Bukharian Jewish, Litvak Ashkenazi, and Iberian/Venezuelan ancestral narratives. Solved BiDi Hebrew RTL rendering, multi-script typography (Hebrew / Latin / Cyrillic), and complex multi-column layout challenges in ReportLab.

---


## 🧰 Tech Stack

**AI & APIs**
`Anthropic Claude API` `Prompt Engineering` `Claude Vision` `MCP` `GitHub Copilot` `Claude Code`

**Android**
`Kotlin` `Android SDK` `AccessibilityService` `ViewBinding` `Material 3` `WorkManager` `NotificationCompat` `SharedPreferences` `BootReceiver` `Firebase` `Gradle`

**Web / Frontend**
`React` `React Native` `Expo` `TypeScript` `JavaScript` `Node.js` `Express` `Vite` `Canvas API` `HTML/CSS`

**Desktop**
`Electron` `IPC / contextBridge` `PowerShell` `Cross-Platform`

**Python**
`ReportLab` `PDF Generation` `BiDi/Unicode` `Pillow`

**Production Support**
`SQL` `PowerShell` `ServiceNow` `Control-M` `Azure DevOps` `GitLab` `ITIL` `Charles River (CRD)`

---

## 💼 Work Background

| Company | Role |
|---|---|
| State Street | Application Support — accounting & trade systems |
| Morgan Stanley / Parametric | Application Support Engineer — portfolio management systems |
| Beacon Hill | Contract Application Support |

ITIL-aligned incident management · Root cause analysis · SLA ownership · Financial systems production environments

---

## 📍 About Me

Application Support Engineer based in the Greater Boston area, with a strong background in enterprise financial systems, incident management, and workflow automation. Passionate about building practical tools at the intersection of AI, systems reliability, and software engineering.

Currently open to hybrid or on-site Application/Production Support Engineer roles in the Boston area (remote EST/CST considered).

📧 azaurov@gmail.com · 🔗 [LinkedIn](https://www.linkedin.com/in/azaurov/)
