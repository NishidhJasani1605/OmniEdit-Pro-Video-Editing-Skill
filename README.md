# OmniEdit Pro

**The open-source AI video editing skill for high-retention, cinematic video content.**

Transform raw footage into polished, modern videos featuring speech-synchronized motion graphics, AI background cutout, glassmorphic typography, and intelligent multi-agent post-production.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Skill: Pure Markdown](https://img.shields.io/badge/Architecture-Pure%20Agent%20Skill-orange)](skills/omni-edit-pro)
[![Matting: RVM MobileNetV3](https://img.shields.io/badge/AI%20Cutout-RVM%20MobileNetV3-green)](https://github.com/PeterL1n/RobustVideoMatting)
[![Format: 9:16 & 16:9](https://img.shields.io/badge/Formats-9:16%20Reels%20%7C%2016:9%20Widescreen-purple)]()

---

## ⚡ 1-Click Install Prompt for Any AI Agent

Copy and paste this prompt into **Claude Code, Antigravity, Cursor, Codex, or Gemini** to install and activate OmniEdit Pro in seconds:

```text
Please download and install the OmniEdit Pro video editing skill from https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill.git. Set up skills/omni-edit-pro as my active video editing skill. Follow its pure Markdown tool directives (using OpenAI Whisper for speech alignment, PeterL1n's Robust Video Matting MobileNetV3 for background cutout, Pillow for layout math, and native FFmpeg for lossless compositing). When I provide a video without specifying style or orientation, present the interactive clarification questions (9:16 vs 16:9, Split vs Cutout vs Overlay vs Custom Idea) before editing.
```

---

## 🌟 What is OmniEdit Pro?

**OmniEdit Pro** is an intelligent video editing skill designed specifically for AI coding assistants. Instead of requiring heavy manual video editors (like Premiere Pro or DaVinci Resolve) or expensive cloud editing subscriptions, OmniEdit Pro provides a comprehensive, production-grade specification that turns any AI agent into an **autonomous video post-production studio**.

When you give an AI assistant raw footage and invoke OmniEdit Pro, the agent:
1. **Transcribes & Analyzes Audio**: Aligns spoken words to exact millisecond timestamps using Whisper.
2. **Applies Content Intelligence**: Detects key concepts, fixes spelling, ensures modern terminology, and creates sleek summary cards.
3. **Designs Geometric Visuals**: Generates clean typography, padded cards, and category pills that never collide with the speaker's face.
4. **Isolates the Speaker (Cutout Mode)**: Uses local AI video matting (RVM MobileNetV3) to remove backgrounds without green screens.
5. **Composites Losslessly**: Leverages native FFmpeg to assemble smooth animations, downsample crisp 2x vector graphics, and preserve bit-identical original audio.

```
+-----------------------------------------------------------------------------+
|                                USER INPUT                                   |
|                (Raw Footage + Optional Style Sample/Prompt)                 |
+-----------------------------------------------------------------------------+
                                       |
                                       v
+-----------------------------------------------------------------------------+
|                      SMART INTERACTIVE CLARIFICATION                        |
|          (Auto-detects or prompts user: Orientation, Layout & Style)        |
+-----------------------------------------------------------------------------+
                                       |
                                       v
+-----------------------------------------------------------------------------+
|                      OMNIEDIT PRO TOOL DIRECTIVES                           |
|   RVM MobileNetV3         Pillow (PIL) Geometry      FFmpeg Windows Engine  |
|   (Local AI Matting)      (Layout & Collision Math)  (Lossless Compositor)  |
+-----------------------------------------------------------------------------+
                                       |
                                       v
+-----------------------------------------------------------------------------+
|                     AUTOMATED PROGRAMMATIC REVIEWER                         |
|          (Mathematical Collision Checks + Audio Waveform Verification)      |
+-----------------------------------------------------------------------------+
                                       |
                                       v
+-----------------------------------------------------------------------------+
|                         FINAL OUTPUT PROMOTION                              |
|                  <workspace>/Final Output Videos/<video-id>/                |
+-----------------------------------------------------------------------------+
```

---

## 🚀 Key Features & Capabilities

### 1. 🎯 Dynamic Speech-Synchronized Animation
- **Reveals as You Speak**: Titles, bullet cards, and badges animate on screen **in exact sync with spoken words** (using snappy 0.15s spring curves) rather than being displayed statically before the speaker introduces them.
- **Persistent Card Stacking**: Sequential points accumulate into a sleek stacked list, giving viewers ample time to read and absorb information naturally.
- **Zero-Collision Spacing**: Cards carry local glassmorphic backings that guarantee contrast without casting awkward shadows across the speaker's body.

### 2. ✂️ Local AI Speaker Cutout (Robust Video Matting)
- **Green-Screen Free**: Isolates the speaker's natural moving silhouette using PeterL1n's lightweight (15MB) **Robust Video Matting (RVM) MobileNetV3** model.
- **Fast Local Execution**: Runs locally on your CPU or GPU—no cloud API costs or subscription limits.
- **Dynamic Backgrounds**: The speaker floats seamlessly over animated motion graphics, diagrams, and video layers.

### 3. 📐 4 Flexible Composition Layouts
- **Split Screen**: Divides canvas into clear visual quadrants (e.g. presenter on one side, animated diagrams on the other).
- **Cutout**: Background removed; speaker floats over full-canvas motion backgrounds and animations.
- **Full-Screen Overlay**: Keeps 100% of the raw camera footage full-screen ($1080 \times 1920$ or $1920 \times 1080$), tastefully layering title plates, subtitles, and badges in natural empty spaces.
- **Adaptive**: The AI dynamically switches layouts scene-by-scene based on what is being discussed.

### 4. 📱 Any Video Orientation
- **9:16 Vertical (Mobile First)**: Perfectly optimized for TikTok, Instagram Reels, and YouTube Shorts.
- **16:9 Horizontal (Widescreen)**: Engineered for YouTube main videos, desktop presentations, and LinkedIn.
- **Auto-Detect**: Automatically matches the source video's native resolution and frame rate.

### 5. 💬 Smart Interactive Clarification Flow
If you give OmniEdit Pro a video without specifying what look you want, it stops and interactively asks:
- **Orientation**: 9:16 Vertical, 16:9 Horizontal, or Auto-Detect?
- **Style**: Split Screen, Cutout, Overlay, Auto/Adaptive, or **Your Own Custom Idea**!
  *(Tell the AI your custom idea—e.g. "Picture-in-picture circle in bottom corner" or "Split screen with live code on right"—and it builds styling to match!)*

### 6. 🧠 Smart Spelling & Modern Context Agent
- **Phonetic Repair**: Automatically catches and fixes transcription errors in medical, technical, business, and regional names.
- **Temporal Freshness**: Ensures all references, model names, and software versions cited in graphics are current and up-to-date.
- **High-Impact Headlines**: Condenses spoken thoughts into punchy 3–5 word headlines.

### 7. 👥 Full-Mesh Multi-Agent Team + CEO Oversight
- **CEO Agent (Video Lead)**: Sets direction, dispatches tasks, reviews deliverables from each specialist, and gives final release sign-off.
- **High-Speed Parallel Tracks**: Audio transcription, background cutout, and visual styling run **simultaneously in parallel**, cutting turnaround time by up to 60%.
- **Omni-Directional (Any-to-Any) Communication**: Every subagent can directly message ANY other subagent whenever they need to coordinate (e.g. Reviewer alerts Layout Animator to adjust a card; Cutout alerts Visuals to clothing colors).
- **Auto Solo Fallback**: Runs smoothly and sequentially in single-agent environments (VS Code, Cursor) without stalling.

### 8. 🎧 Bit-Identical Lossless Audio
- Uses native FFmpeg direct audio streamcopy (`-c:a copy`) to preserve original microphone quality, dynamic range, and perfect lip-sync with zero generational re-compression.

---

## 🛠️ Tool Directives (Which Tool is Used for What)

OmniEdit Pro is a pure skill package. It directs the AI coding agent to utilize standard, high-performance tools available on the host machine:

| Capability | Recommended Tool | Purpose & Usage |
|---|---|---|
| **Speaker Background Cutout** | **Robust Video Matting (RVM)**<br/>(`PeterL1n/RobustVideoMatting`) | Lightweight 15MB MobileNetV3 model loaded via PyTorch in the workspace for fast local alpha mask extraction. |
| **Speech Alignment & Timings** | **OpenAI Whisper** | Generates word-level timestamps to trigger syllable-synchronized animations. |
| **Layout & Typography Math** | **Pillow (`PIL.ImageFont`)** | Measures exact visible bounding boxes, line wrapping, badge padding, and verifies zero facial collision. |
| **Video Compositing & Mixing** | **FFmpeg CLI** | Lossless compositing, 2x text raster downsampling (Lanczos-3), Windows path escaping (`D\:/...`), and audio streamcopy (`-c:a copy`). |

---

## 📁 Repository Structure

```text
OmniEdit-Pro-Video-Editing-Skill/
├── README.md                             <-- Complete documentation & quick install prompt
├── LICENSE                               <-- MIT License
├── skills/
│   └── omni-edit-pro/                    <-- The Single Unified Skill
│       ├── SKILL.md                      <-- Main orchestrator & interactive flow
│       └── references/                   <-- Detailed production guidelines
│           ├── selection.md              <-- Interactive questionnaire & custom idea mode
│           ├── local-cutout.md           <-- RVM MobileNetV3 matting instructions
│           ├── motion-design.md          <-- Dynamic speech-synced animation curves
│           ├── transcription-sync.md     <-- Smart spelling & modern content agent
│           ├── layouts-effects.md        <-- Full-screen overlay & quadrant subtitles
│           ├── editing-styles.md         <-- Split, Cutout, Overlay, & Adaptive layouts
│           ├── audio-rendering.md        <-- FFmpeg streamcopy & 2x rasterization
│           ├── video-reviewer.md         <-- Programmatic automated QA gate
│           ├── batch-teams.md            <-- Full-mesh multi-agent coordination & CEO oversight
│           ├── reference-analysis.md     <-- Reference profiling & card backings
│           ├── quality-assurance.md      <-- Adaptive tolerance tuning
│           └── delivery.md               <-- Safe promotion to Final Output Videos/
```

---

## 💻 System Requirements

To use OmniEdit Pro with your AI assistant, ensure the following tools are available on your system:
- **FFmpeg & FFprobe**: `ffmpeg -version`
- **Python 3.8+**: with `torch` and `Pillow` installed (`pip install torch torchvision pillow`)
- **OpenAI Whisper**: for speech transcription (`pip install openai-whisper`)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
