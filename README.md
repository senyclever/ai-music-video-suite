# 🎬 AI Music Video Suite

**🌉 Lyric Bridge + ⚡ Beat Calculator — by Seny Clever**

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
![Single file](https://img.shields.io/badge/HTML5-single--file-orange)
![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen)
![Languages](https://img.shields.io/badge/languages-ES%20%7C%20EN-blue)
![Local](https://img.shields.io/badge/100%25-local%20%26%20free-purple)

> 🌐 **English** · [Español](README.es.md)

**From the lyrics of your song to a fully planned, AI-generated music video.**
Two free, local, bilingual, single-file apps that work as one pipeline: you bring the song and the lyrics — the suite handles rhythm, timing, the cinematic script and the production export. No accounts, no servers, no ads. Your music never leaves your machine.

---

## 🧩 The two apps

| App | What it does | Best on |
|---|---|---|
| **🌉 Lyric Bridge** (Puente Lírico) | Load audio, set the BPM (or tap it), write lyrics on the musical grid, export a **Master Prompt** for any AI | 📱 Mobile & desktop |
| **⚡ Beat Calculator** | Import the AI's JSON script, review/edit it on a pro 4-band timeline, export the **production report + markers** | 🖥️ Desktop workstation |

## 🔗 The pipeline

```
🎵 Your song + lyrics
        │
        ▼
🌉 LYRIC BRIDGE ── BPM · timeline · energy E0–E3
        │  exports 📋 Master Prompt (+ JSON skeleton)
        ▼
🤖 ANY AI (ChatGPT, Claude, Gemini, DeepSeek, local LLMs…)
        │  returns ONE valid .json with the full cinematic script
        ▼
⚡ BEAT CALCULATOR ── import JSON · review · edit · refine
        │  ⚠ do NOT press Generate/Update after importing
        ▼
📄 Production report  +  🎞 Markers (7 formats)
        │
        ▼
🎥 Your video AI (FramePack, Wan, Kling, Runway…) + your editor
```

**Hierarchy:** SONG ➜ SECTION (musical) ➜ SCENE (visual) ➜ CLIP (video segment).

## 🚀 Quick start

### Online (GitHub Pages)
- 🏠 [Suite home](https://senyclever.github.io/ai-music-video-suite/)
- 🌉 [Lyric Bridge](https://senyclever.github.io/ai-music-video-suite/apps/lyric-bridge/)
- ⚡ [Beat Calculator](https://senyclever.github.io/ai-music-video-suite/apps/beat-calculator/)

### Offline
**Code → Download ZIP**, unzip, open `index.html`. No install, no build, no server. Each app is a single `.html` file you can keep anywhere.

### Requirements
- A modern browser (Chrome, Edge, Firefox, Brave)
- Optional: [Sonic Visualiser](https://www.sonicvisualiser.org) (free) to export a beats CSV for Beat Calculator
- Any text AI for the Master Prompt · any video AI to generate the clips

## 🌉 Lyric Bridge — features
- 🎧 Optional audio with waveform; total duration auto-detected
- 🥁 BPM by hand or **Tap Tempo** (6+ taps, median interval + phase/offset detection)
- 🎵 Canvas timeline: drag/resize bars, zoom up to 50×, snaps (edges / beat / bar / phrase), live marking with `L` / `M`
- ✍️ Fluid lyric paste with `[Section | interpreter | instrumental]` headers, auto-placement on the grid, re-flow
- ⚡ Per-line energy **E0–E3** (manual or 🪄 auto) → camera intensity in the prompt
- 🎬 **Director Mode** bible (ES/EN) + Master Prompt with a layer contract and exact JSON schema
- 🧪 Self-Test (6 checks), validation, undo/redo (50), notification history, day/night themes
- 💾 Browser autosave + project / lyrics / skeleton exports

## ⚡ Beat Calculator — features
- 🎵 **4-band timeline**: Sections / Scenes / Auto clips / Manual clips + waveform + beats + ruler
- 🥁 Beats CSV from Sonic Visualiser, regularity analysis, CSV re-export
- 🎬 Balanced partition with **hard ceiling D**, soft minimum, beat snap (only shortens), overlap S
- 🔗 First-Last-Frame + cross-appearance continuity; manual clips never auto-chained
- 🎨 Aesthetics cascade **clip → scene → section**; reusable, exportable libraries
- 📝 Per-clip script + one-click full prompt (Universal + Aesthetic + Scene + Script + Params)
- 🎞 Markers ×7 + bilingual production report + built-in bilingual manual
- ⌨️ Shortcuts (`Space`, `M`/`S`/`C`, `Ctrl+Z`/`Y`, `Enter`, `Esc`), undo/redo (50), tooltips everywhere

## 📜 The contract between the apps (read this!)
- Both share the JSON envelope `{version:"1.0", state}` and the **same partition algorithm** (ceiling D, beat snap, overlap S, `frames = round(dur/1000 × fps)`).
- The Master Prompt declares the **musical layer immutable** (timings, BPM, events, sections, techConfig) and the **narrative layer re-authorable** (scenes, assignments, clips, aesthetics, prompts, notepad).
- ⚠️ **After importing the AI's JSON into Beat Calculator, do NOT press 🔄 Update / 🎬 Generate clips** — it would re-partition and remap the script. Clips arrive pre-computed with exact ids and frames.
- Recommended pipeline discipline: *Enhance My Prompt* OFF, character-only references, letterbox in post.

## 📁 File formats

| File | Produced by | Purpose |
|---|---|---|
| `*_PuenteLirico.json` | Lyric Bridge | Full lyric project backup |
| `*_letra.txt` (`#LYRICS_BRIDGE v1`) | Lyric Bridge | Lossless lyrics + timing backup |
| `*_MasterPrompt.txt` | Lyric Bridge | The prompt for your AI (auto-split in 2 parts if > 60 KB) |
| `*_esqueleto.json` | Lyric Bridge | Base skeleton `{version:"1.0", state}` |
| AI script `.json` | Your AI | Complete narrative project → import into Beat Calculator |
| `Project.json` | Beat Calculator | Full script backup (audio filename remembered) |
| `Project.txt` | Beat Calculator | Production report for your video AI |
| `Project_<format>_markers.*` | Beat Calculator | Universal / YouTube / DaVinci Resolve / Blender (`.py`) / Premiere / CapCut / NLE |
| `*_beats.csv` | Beat Calculator | Beats export (Sonic Visualiser compatible) |
| `aesthetic_*.txt` · `* - Prompt Universal.txt` | Beat Calculator | Reusable style libraries |

## 🔒 Privacy
100% local. No servers, no uploads, no accounts, no telemetry, no ads. Audio is decoded in your browser and never leaves your machine. Lyric Bridge autosaves to `localStorage`; Beat Calculator saves explicitly via JSON.

## 🎨 Beyond music videos
Use Lyric Bridge as a **lyric notebook** (`.txt` backups with timing) and Beat Calculator as a **script workstation** (`.json` backups) — for short films, ads, visualizers or any audiovisual piece.

## 🗂 Repository structure
```
ai-music-video-suite/
├── index.html                     # Bilingual suite home (GitHub Pages)
├── apps/
│   ├── lyric-bridge/index.html    # App 1 · single file
│   └── beat-calculator/index.html # App 2 · single file
├── README.md                      # English
├── README.es.md                   # Español
├── LICENSE                        # MIT
└── .gitignore
~~~

## 🛠 Development
No build step: edit the HTML files directly. Lyric Bridge includes a 🧪 **Self-Test** (Export tab) that checks the partition contract, lyric round-trip, ES/EN parity and frame math. If you modify the partition algorithm, keep **both apps in sync**.

## 🤝 Contributing
Issues and PRs welcome. Please keep the ES/EN parity and the single-file, dependency-free philosophy.

## 📄 License
MIT © 2026 Seny Clever — free forever, no ads.

Made with ❤️ for creators.
