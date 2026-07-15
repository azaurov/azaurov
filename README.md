<div align="center">
  <img src="header.svg" alt="Alex Zaurov — Prod Support by Day · AI Builder by Night" width="900"/>
</div>

I don't just support software — I build it. My production support background gives me a systems-level lens that makes my personal projects unusually well-engineered. I've shipped AI-powered web apps, cross-platform mobile apps, and desktop tools built with modern frameworks and cloud APIs.

---

## 🛠 What I Build

### 🌍 [Silk Road Duo](https://github.com/azaurov/SilkRoadDuo) — AI Language Learning Platform
> *React Native · Expo · JavaScript · OpenRouter / Groq / Gemini*

A cross-platform language learning app teaching 7 ancient and classical languages of the Silk Road (Bukharian, Farsi, Sogdian, Arabic, Uzbek, Hebrew, Aramaic). **[Try it live →](https://azaurov.github.io/SilkRoadDuo/)**

- **AI-generated lessons** — 20 exercises per session via OpenRouter / Groq / Gemini with auto-fallback on rate limits; accurate vocabulary, native script (RTL for Arabic/Hebrew/Farsi), and romanized transliterations
- **4 exercise types** — MCQ, fill-in-the-blank, matching pairs, word arrangement; TTS for Arabic, Farsi, Hebrew, Uzbek
- **Local user profiles** — multiple profiles per device, each with independent XP, daily streak, and achievements persisted in AsyncStorage across cold restarts
- **PWA** — installable on iPhone via Safari → Share → Add to Home Screen; auto-deployed to GitHub Pages on every push; works offline after first load

---

### 🛡️ [SentinelWatch](https://github.com/azaurov/SentinelWatch) — AI Process Monitor
> *Electron · Node.js · Groq API · contextBridge IPC · PowerShell · ps aux*

Cross-platform Electron desktop app that polls live OS processes every 5 seconds, flags any process sustained at ≥10% CPU for 10+ minutes as `HANGING`, and surfaces **Groq AI-generated triage recommendations** on click. Built on Node 18+'s built-in `fetch` against Groq's OpenAI-compatible chat-completions endpoint — no LLM SDK dependency.

- **Hang detection**: rolling per-process state tracked across polls; Windows CPU% derived from `Get-Process` CPU-time delta normalized by core count; Linux/macOS uses `ps aux` CPU% directly
- **AI diagnosis via Groq**: default model `llama-3.3-70b-versatile`, overridable via `GROQ_MODEL`; structured output (What it is / Why hanging / Risk / Recommended action) parsed from a system-prompt template
- **Stale-process freeze**: detail panel stays open after the selected process dies so you can finish reading the AI diagnosis, with a `⚠ PROCESS ENDED` marker and the Kill button disabled
- **Security**: `contextIsolation: true`, `nodeIntegration: false`, all renderer access to the main process goes through a narrow audited `window.sentinel` API in `preload.js` (`onProcessUpdate` / `diagnoseProcess` / `killProcess`)

---

### 🤖 [AI Resume & Cover Letter Builder](https://github.com/azaurov/resume_builder)
> *TypeScript · React · Node.js/Express · Anthropic Claude API*

An AI-powered tool for instantly generating tailored resumes and cover letters. Reads your profile and job descriptions to generate personalized documents in seconds — ideal for rapid job applications and career transitions.

---

### 🕸️ [mywebsite](https://github.com/azaurov/mywebsite)
> *PHP · CSS*

A role-based access control website for personal and project showcase. High-performance PHP backend and custom CSS—built as a learning ground for secure authentication, web layouts, and feature-rich user experiences.

---

### 🤝 [phpmyadmin](https://github.com/azaurov/phpmyadmin)
> *PHP · JavaScript · Twig · SCSS*

A fork for custom tooling and experimentation with database management UIs. Tinkering with the legendary phpMyAdmin codebase to improve efficiency, tweak UI, and prototype extensions for production environments.

---

### 👻 [Pac-Man](https://github.com/azaurov/Pac-Man)
> *HTML*

A pure-HTML recreation of the arcade classic. A nostalgic side project focused on accessibility and fun browser dynamics.

---

### 🤖 [Zeev](https://github.com/azaurov/Zeev)
> *Python · Groq API · Piper TTS · SQLite · Raspberry Pi Zero 2W*

Personal AI companion running on a Raspberry Pi Zero 2W. Auto-routes between Groq's 8B, 70B, and DeepSeek R1 models per message; falls back to a local Ollama server when offline. Per-model rate-limit tracking automatically falls back to 8B when 70B/R1 hits a Groq daily or burst limit, and to OpenRouter's free tier if Groq itself is rate-limited — no errors surfaced to the user.

- **Torah RAG**: FTS5 SQLite corpus spanning Tanakh, Talmud, Zohar, Dead Sea Scrolls, and Sumerian literature — "parsha"/"parshah"/"portion" queries trigger Torah DB lookup with 70B model and 1,200-token limit; RAG index capped at 500 messages to prevent OOM on 512 MB Pi
- **Weekly reflection**: every Sunday an LLM synthesizes the past week of conversations into a structured reflection (recurring themes, emotional patterns, open questions) stored in SQLite and injected into every system prompt — Zeev arrives at each conversation already briefed on the week
- **Quantum reasoning**: daily quantum circuit simulations (Qiskit) explore human-dilemma scenarios; insights accumulate over time and compound future reasoning
- **Dual voice persona**: Zeev's voice is Groq Orpheus `daniel`; device mode is spoken by **Sarina** (Zeev's secretary) using Kokoro `af_heart` at natural speed — voice selectable per-request via the Go audio daemon; multilingual TTS (Hebrew/Spanish/Russian) activated by explicit `/lang` command (terminal/web) or spoken request like "speak Russian" (device mode) rather than auto-detection from character sets; Russian uses a local Piper voice ("Irina") on-device rather than cloud TTS
- **Bluetooth audio**: pair headphones by voice ("scan for bluetooth", "pair my headphones") — auto-detected at startup, all TTS and music routed and resampled (ffmpeg) to match A2DP format; physical disconnects (headphones powered off) detected automatically before each TTS call
- **Phone calls (HFP)**: dial and receive calls via Bluetooth HFP; auto-detects voicemail, IVR, or live callers; speculative pre-generation so the voicemail message is ready at the beep; live calls carry full conversation history across turns; early-speech-onset detection prevents Whisper hallucinations on 8kHz SCO audio from misclassifying a real pickup as voicemail; dial intent requires "call"/"dial" near the start of the utterance so it isn't triggered by mid-sentence mentions
- **Quantum conversation scenarios** (`quantum_convo.py`): runs a quantum circuit over conversation directions (empathy, playfulness, depth, small talk) and uses the interference pattern to prioritize call topics — `python3 zeev/quantum_convo.py --name NAME --call NUMBER`
- **GPS / geolocation**: WiFi-triangulated location via Google Geolocation API (10–100m), beacondb fallback, IP fallback; reverse-geocoded to city/region via Nominatim; injected into context automatically on location queries
- **Weather, spoken naturally**: web-search weather replies spell out units as full words ("degrees Fahrenheit", "miles per hour") instead of symbols, since every reply is read aloud via TTS
- **Web UI + device mode**: mobile-friendly SSE chat interface and a push-to-talk Whisplay HAT mode with thermal camera (MLX90640) and Pi NoIR camera support; say "what do you see" in device mode to capture a photo and get a vision-model description (Llama 4 Scout)
- **Voice-triggered LCD visuals**: say "show me some fire" or "do the matrix effect" in device mode and Zeev/Sarina renders demoscene-style fire, matrix rain, psychedelic, liquid, tunnel, plasma, or cartoon-face animations directly on the Whisplay LCD

---

### ...plus more public and private projects!

## 🧰 Tech Stack

**AI & APIs**
`Anthropic Claude API` `Prompt Engineering` `Claude Vision` `MCP` `GitHub Copilot` `Claude Code` `Prompt Caching`

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

**Independent Developer & AI Builder** | Self-employed  
*Nov 2025 - Present*  
Building AI-powered tools, Android apps, and full-stack projects using Claude API, Kotlin, React Native, and Python. Actively seeking production/application support roles in the Boston area.

**Production Support Engineer** | Parametric (Contract)  
*Jun 2025 - Nov 2025 · Boston, MA (Hybrid)*  
Production monitoring & incident management for Fixed Income trading systems · Automated PowerShell and GitLab deployment pipelines · SQL and Unix troubleshooting for real-time data issues

**Application Analyst** | New England Law | Boston (Contract)  
*Jan 2024 - Dec 2024 · Boston, MA (On-site)*  
ITSM & Change Management: Implemented ServiceNow workflows for Incident, Change, and Service Request processes, improving SLA compliance and formalizing change management with product owners and stakeholders.

**Support Engineer** | SimCorp  
*Apr 2019 - Jan 2024 · Greater Boston (Hybrid)*  
Led ITIL-aligned incident and problem management for client reporting on investment management platform, reducing mean time to resolution by 25% through standardized runbooks and shared knowledge bases.

**Support Engineer III** | Tangoe  
*Jun 2015 - Oct 2016 · Waltham (Hybrid)*  
Managed incident and problem lifecycles for global clients, authored runbooks and protocol documentation, and trained onshore/offshore teams to standardize support processes and improve SLA performance.

**Application Engineer I** | Orion Health  
*Mar 2014 - Jun 2015 · Greater Boston (On-site)*  
Queried terabyte-scale Oracle datasets and used Linux Bash for triage and root-cause analysis, supporting clinical applications with strict compliance and production deadlines. Trained staff on reporting accuracy.

**Client Service Analyst** | Boston Medical Center (Contract)  
*Jul 2013 - Mar 2014 · Greater Boston (On-site)*  
Performed incident triage and SQL-based root cause analysis for patient-facing systems, improving reporting accuracy and compliance and contributing to process improvements for production support teams.

**Senior Associate & Associate II** | State Street  
*May 2008 - Feb 2013 · Quincy, MA*  
Supported accounting and trade systems through incident and problem management; coordinated escalations to development; led root-cause analysis that resolved a major coding error and preserved client trust.

**Skills & Expertise:** ITIL · SLA Management · Incident & Problem Resolution · SQL & Unix/Linux · Production Support · ServiceNow · PowerShell Automation · CI/CD Pipelines

---

## 📍 About Me

Application Support Engineer based in the Greater Boston area, with a strong background in enterprise financial systems, incident management, and workflow automation. Passionate about building production-grade tools and AI-powered applications.

Currently open to hybrid or on-site Application/Production Support Engineer roles in the Boston area (remote EST/CST considered).

📧 azaurov@gmail.com · 🔗 [LinkedIn](https://www.linkedin.com/in/azaurov/) · 🌐 [sogdiana-gematria.net](https://sogdiana-gematria.net)
