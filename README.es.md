# 🎬 AI Music Video Suite

**🌉 Puente Lírico + ⚡ Beat Calculator — por Seny Clever**

[![Licencia: MIT](https://img.shields.io/badge/Licencia-MIT-green.svg)](LICENSE)
![Un archivo](https://img.shields.io/badge/HTML5-un--solo--archivo-orange)
![Dependencias](https://img.shields.io/badge/dependencias-ninguna-brightgreen)
![Idiomas](https://img.shields.io/badge/idiomas-ES%20%7C%20EN-blue)
![Local](https://img.shields.io/badge/100%25-local%20y%20gratis-purple)

> 🌐 [English](README.md) · **Español**

**De la letra de tu canción a un videoclip con IA, completamente planificado.**
Dos aplicaciones gratuitas, locales, bilingües y de un solo archivo que funcionan como un único flujo: tú pones la canción y la letra — la suite se encarga del ritmo, el timing, el guion cinematográfico y la exportación de producción. Sin cuentas, sin servidores, sin anuncios. Tu música nunca sale de tu equipo.

---

## 🧩 Las dos aplicaciones

| App | Qué hace | Ideal en |
|---|---|---|
| **🌉 Puente Lírico** (Lyric Bridge) | Cargar audio, fijar el BPM (o tap-tap), escribir la letra sobre la rejilla musical y exportar un **Prompt Maestro** para cualquier IA | 📱 Móvil y PC |
| **⚡ Beat Calculator** | Importar el guion JSON de la IA, revisarlo/editarlo en un timeline profesional de 4 bandas y exportar el **informe de producción + marcadores** | 🖥️ Estación de trabajo |

## 🔗 El flujo de trabajo

```
🎵 Tu canción + letra
        │
        ▼
🌉 PUENTE LÍRICO ── BPM · timeline · energía E0–E3
        │  exporta 📋 Prompt Maestro (+ esqueleto JSON)
        ▼
🤖 CUALQUIER IA (ChatGPT, Claude, Gemini, DeepSeek, LLMs locales…)
        │  devuelve UN .json válido con el guion cinematográfico completo
        ▼
⚡ BEAT CALCULATOR ── importar JSON · revisar · editar · afinar
        │  ⚠ NO pulses Generar/Actualizar tras importar
        ▼
📄 Informe de producción  +  🎞 Marcadores (7 formatos)
        │
        ▼
🎥 Tu IA de video (FramePack, Wan, Kling, Runway…) + tu editor
```

**Jerarquía:** CANCIÓN ➜ SECCIÓN (musical) ➜ ESCENA (visual) ➜ CLIP (segmento de video).

## 🚀 Inicio rápido

### En línea (GitHub Pages)
- 🏠 [Portada de la suite](https://senyclever.github.io/ai-music-video-suite/)
- 🌉 [Puente Lírico](https://senyclever.github.io/ai-music-video-suite/apps/lyric-bridge/)
- ⚡ [Beat Calculator](https://senyclever.github.io/ai-music-video-suite/apps/beat-calculator/)

### Sin conexión
**Code → Download ZIP**, descomprime y abre `index.html`. Sin instalación, sin compilación, sin servidor. Cada app es un único archivo `.html` que puedes guardar donde quieras.

### Requisitos
- Un navegador moderno (Chrome, Edge, Firefox, Brave)
- Opcional: [Sonic Visualiser](https://www.sonicvisualiser.org) (gratis) para exportar el CSV de beats hacia Beat Calculator
- Cualquier IA de texto para el Prompt Maestro · cualquier IA de video para generar los clips

## 🌉 Puente Lírico — características
- 🎧 Audio opcional con forma de onda; duración total autodetectada
- 🥁 BPM a mano o **Tap Tempo** (6+ golpes, mediana + detección de fase/offset)
- 🎵 Timeline en canvas: arrastrar/redimensionar barras, zoom hasta 50×, snaps (bordes / beat / compás / frase), marcado al vuelo con `L` / `M`
- ✍️ Pegado fluido de letra con encabezados `[Sección | intérprete | instrumental]`, autocolocación en la rejilla y re-flow
- ⚡ Energía por línea **E0–E3** (manual o 🪄 auto) → intensidad de cámara en el prompt
- 🎬 Biblia **Modo Director** (ES/EN) + Prompt Maestro con contrato de capas y esquema JSON exacto
- 🧪 Self-Test (6 pruebas), validación, deshacer/rehacer (50), historial de avisos, temas día/noche
- 💾 Autoguardado en el navegador + exportación de proyecto / letra / esqueleto

## ⚡ Beat Calculator — características
- 🎵 **Timeline de 4 bandas**: Secciones / Escenas / Clips auto / Clips manuales + onda + beats + regla
- 🥁 CSV de beats desde Sonic Visualiser, análisis de regularidad, reexportación CSV
- 🎬 Partición balanceada con **techo duro D**, mínimo blando, snap al beat (solo acorta), solapamiento S
- 🔗 First-Last-Frame + continuidad entre apariciones; los clips manuales nunca se auto-encadenan
- 🎨 Estéticas en cascada **clip → escena → sección**; bibliotecas reutilizables y exportables
- 📝 Guion por clip + prompt completo en un clic (Universal + Estética + Escena + Guion + Parámetros)
- 🎞 Marcadores ×7 + informe de producción bilingüe + manual bilingüe integrado
- ⌨️ Atajos (`Espacio`, `M`/`S`/`C`, `Ctrl+Z`/`Y`, `Enter`, `Esc`), deshacer/rehacer (50), tooltips en todo

## 📜 El contrato entre las apps (¡léelo!)
- Ambas comparten el sobre JSON `{version:"1.0", state}` y el **mismo algoritmo de partición** (techo D, snap al beat, solapamiento S, `frames = round(dur/1000 × fps)`).
- El Prompt Maestro declara la **capa musical inmutable** (tiempos, BPM, events, secciones, techConfig) y la **capa narrativa reautorizable** (scenes, assignments, clips, aesthetics, prompts, notepad).
- ⚠️ **Tras importar el JSON de la IA en Beat Calculator, NO pulses 🔄 Actualizar / 🎬 Generar clips** — re-particionaría y remapearía el guion. Los clips ya llegan calculados con ids y frames exactos.
- Disciplina recomendada del pipeline: *Enhance My Prompt* OFF, referencias solo de personaje, letterbox solo en post.

## 📁 Formatos de archivo

| Archivo | Producido por | Propósito |
|---|---|---|
| `*_PuenteLirico.json` | Puente Lírico | Respaldo completo del proyecto de letra |
| `*_letra.txt` (`#LYRICS_BRIDGE v1`) | Puente Lírico | Respaldo de letra + tiempos sin pérdida |
| `*_MasterPrompt.txt` | Puente Lírico | El prompt para tu IA (se divide en 2 partes si > 60 KB) |
| `*_esqueleto.json` | Puente Lírico | Esqueleto base `{version:"1.0", state}` |
| Guion `.json` de la IA | Tu IA | Proyecto narrativo completo → importar en Beat Calculator |
| `Proyecto.json` | Beat Calculator | Respaldo completo del guion (recuerda el nombre del audio) |
| `Proyecto.txt` | Beat Calculator | Informe de producción para tu IA de video |
| `Proyecto_<formato>_markers.*` | Beat Calculator | Universal / YouTube / DaVinci Resolve / Blender (`.py`) / Premiere / CapCut / NLE |
| `*_beats.csv` | Beat Calculator | Exportación de beats (compatible con Sonic Visualiser) |
| `aesthetic_*.txt` · `* - Prompt Universal.txt` | Beat Calculator | Bibliotecas de estilo reutilizables |

## 🔒 Privacidad
100% local. Sin servidores, sin subidas, sin cuentas, sin telemetría, sin anuncios. El audio se decodifica en tu navegador y nunca sale de tu máquina. El Puente Lírico autoguarda en `localStorage`; Beat Calculator guarda explícitamente vía JSON.

## 🎨 Más allá de los videoclips
Usa el Puente Lírico como **cuaderno de letras** (respaldos `.txt` con tiempos) y Beat Calculator como **estación de guiones** (respaldos `.json`) — para cortos, anuncios, visualizers o cualquier pieza audiovisual.

## 🗂 Estructura del repositorio
~~~
ai-music-video-suite/
├── index.html                     # Portada bilingüe de la suite (GitHub Pages)
├── apps/
│   ├── lyric-bridge/index.html    # App 1 · un solo archivo
│   └── beat-calculator/index.html # App 2 · un solo archivo
├── README.md                      # English
├── README.es.md                   # Español
├── LICENSE                        # MIT
└── .gitignore
~~~

## 🛠 Desarrollo
Sin compilación: edita los HTML directamente. El Puente Lírico incluye un 🧪 **Self-Test** (pestaña Exportar) que verifica el contrato de partición, el round-trip de letra, la paridad ES/EN y el cálculo de frames. Si modificas el algoritmo de partición, mantén **ambas apps sincronizadas**.

## 🤝 Contribuir
Issues y PRs bienvenidos. Por favor mantén la paridad ES/EN y la filosofía de un solo archivo sin dependencias.

## 📄 Licencia
MIT © 2026 Seny Clever — gratis para siempre, sin anuncios.

Hecho con ❤️ para creadores.
