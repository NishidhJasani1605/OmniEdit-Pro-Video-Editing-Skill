# OmniEdit Pro (Unified Pure Skill Edition v4.0.0)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Architecture: Pure Skill](https://img.shields.io/badge/Architecture-Pure%20Skill%20(Markdown)--orange)](skills/omni-edit-pro)
[![Matting: RVM MobileNetV3](https://img.shields.io/badge/AI%20Cutout-RVM%20MobileNetV3-green)](https://github.com/PeterL1n/RobustVideoMatting)
[![Platform: Cross-Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20macOS%20%7C%20Linux-brightgreen)]()

**OmniEdit Pro is an open-source, production-ready AI video editing skill. It transforms raw video footage into cinematic, high-retention deliverables across any orientation (9:16 vertical, 16:9 horizontal) and layout (Split Screen, Cutout with RVM, Full-Screen Overlay, Adaptive).**

---

## ⚡ Direct Copy & Paste Prompt for Any AI Agent

Copy and paste this exact prompt into **any AI coding assistant** (such as Claude Code, Antigravity, Cursor, Codex, or Gemini) to automatically download, install, and activate OmniEdit Pro in your workspace:

```text
Please download and install the OmniEdit Pro video editing skill from https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill.git. Set up skills/omni-edit-pro as my active video editing skill. Follow its pure Markdown tool directives (using OpenAI Whisper for speech alignment, PeterL1n's Robust Video Matting MobileNetV3 for background cutout, Pillow for layout math, and native FFmpeg for lossless compositing). When I provide a video without specifying style or orientation, present the interactive clarification questions (9:16 vs 16:9, Split vs Cutout vs Overlay vs Custom Idea) before editing.
```

---

## 🎬 How OmniEdit Pro Works

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

## 1. Quick Start & Interactive Questionnaire

When you invoke OmniEdit Pro without specifying orientation or style:

```text
Edit my-video.mp4 using OmniEdit Pro.
```

The skill automatically pauses and prompts you with clear multiple-choice options:

### Step 1: Target Video Orientation
1. **9:16 Vertical (Recommended for Mobile)** — Optimized for Instagram Reels, TikTok, YouTube Shorts.
2. **16:9 Horizontal (Widescreen)** — Optimized for YouTube, desktop presentations, LinkedIn.
3. **Auto-Detect** — Match whatever orientation the raw video was recorded in.

### Step 2: Editing Style & Layout
1. **Split Screen** — Divides the canvas: presenter in one zone (left or bottom), dynamic diagrams and cards in the other.
2. **Cutout (AI Background Removal via RVM)** — Uses local Robust Video Matting (MobileNetV3) to isolate the speaker like a clean sticker, floating over high-tech animated backgrounds.
3. **Overlay (Clean & Non-Intrusive)** — Keeps 100% of your camera video full-screen; layers stylish glassmorphic title plates, captions, and badges over natural empty spaces.
4. **Auto-Select / Adaptive** — Let the AI inspect the video and automatically pick the best look for the topic scene-by-scene.
5. **Custom / Your Own Idea** — Have a specific look in mind? *(e.g. "Picture-in-picture circle", "Documentary retro look", "Side-by-side code tutorial")*. Describe it in the prompt and the AI will build custom styling to match your vision!

---

## 2. Tool Directives (Which Tool to Use for Which Purpose)

OmniEdit Pro is a **pure Markdown instruction skill** containing zero `.py` or binary code files inside the skill repository. Instead, it directs the AI coding agent to invoke proven external tools in the workspace:

| Purpose | Recommended Tool | Directive & Execution in Workspace |
|---|---|---|
| **Speaker Background Cutout** | **Robust Video Matting (RVM)**<br/>(`PeterL1n/RobustVideoMatting`) | Load `rvm_mobilenetv3.pth` (15MB) via PyTorch to extract clean foreground RGB and alpha masks locally on CPU/GPU without green screen. |
| **Speech Transcription & Word Timings** | **OpenAI Whisper** | Run Whisper to generate word-level timestamped transcripts for speech-synced animation. |
| **Transcript Intelligence & Spelling** | **AI Content Agent** | Normalizes homophones, fixes brand/tech spelling, generates 3–5 word summary titles, and ensures modern version names. |
| **Typography & Layout Math** | **Pillow (`PIL.ImageFont`)** | Measures exact glyph bounding boxes, calculates text wrapping, sets badge padding ($\ge 24\text{px}$), and ensures zero facial collision. |
| **Video Compositing & Audio Passthrough** | **FFmpeg CLI** | Blends video layers, downsamples graphics via Lanczos-3, preserves lossless audio (`-c:a copy`), and escapes Windows paths (`D\:/...`). |

---

## 3. Full-Mesh Multi-Agent Team & CEO Approval

When executed in multi-agent environments (such as Antigravity):
- **CEO Agent (Video Lead)**: Oversees project strategy, dispatches tasks, reviews deliverables from each specialist, and gives final sign-off before release.
- **High-Speed Parallel Tracks**: Speech transcription (Whisper), background cutout (RVM), and visual styling run **concurrently at the exact same time**, reducing turnaround time by up to 60%.
- **Omni-Directional (Any-to-Any) Communication**: Every single subagent can directly message ANY other subagent whenever they need to coordinate (e.g. Reviewer alerts Layout Animator to nudge a card by 10px; Cutout alerts Visuals to speaker clothing colors).
- **Auto Solo Fallback**: If run in single-agent environments (VS Code, Cursor), the agent executes the specialist roles sequentially without stalling.

---

## 4. How All 18 Identified Deadlocks Are Solved

| # | Flaw / Deadlock | Solution in Unified Architecture |
|---|---|---|
| 1 | **Human Playback Paradox** | **Automated Programmatic QA Gate**: Evaluates bounding box math, non-collision, and audio waveform decodes programmatically; passing tests promotes candidate to `Final Output Videos`. |
| 2 | **9:16 Portrait Space Collapse** | **Full-Screen 9:16 Overlay**: Keeps 9:16 footage 100% full-screen ($1080 \times 1920$); graphics layer over natural negative space without shrinking into a 337px thumbnail. |
| 3 | **Split Caption Seam Collision** | **Quadrant-Anchored Subtitles**: Anchors captions comfortably inside active speaker or graphics quadrant, never on the center dividing seam ($X=960$). |
| 4 | **Zero-Defect 2-Try Halt** | **Smart Tolerance Tuning**: Replaces hard crashes with adaptive parameter adjustments (10px margin padding, automatic quadrant shifting). |
| 5 | **Dark Scrim vs Speaker Collision** | **Card-Attached Backing**: Each card carries its own local glassmorphic or blur backing plate, eliminating full-canvas dark scrim collisions. |
| 6 | **Fast Speech Pacing Deadlock** | **Dynamic Micro-Transitions**: 0.15s spring animations matching speaker tempo, accumulating into persistent multi-item lists for ample reading time. |
| 7 | **Multi-Video Batch Misclassification** | **Explicit Batch Confirmation**: Batch files treated as independent sources unless explicitly flagged with `--reference`. |
| 8 | **Explicit Tool Directives** | **Explicit External Tool Directives**: Replaces guessing or bundled scripts with explicit CLI/API instructions for RVM, FFmpeg, Whisper, and Pillow. |
| 9 | **Remotion Commercial Licensing** | **Native Free FFmpeg + PIL Engine**: 100% free, open-source compositor with zero proprietary licensing traps or headless browser crashes. |
| 10 | **Local Cutout Feasibility** | **Robust Video Matting (RVM) MobileNetV3**: Fast 15MB model that runs locally on CPU or GPU without green screen. |
| 11 | **2x Supersampling 8K Blowup** | **Selective Vector/PIL Rasterization**: Only text and badges are rendered at 2x and downsampled; raw video remains at 1x to prevent 8K memory exhaustion. |
| 12 | **Subagent Spawning Stalls** | **Automatic Solo Pipeline**: If host editor does not support dynamic subagents, the agent executes specialist roles sequentially without stalling. |
| 13 | **Proper Name Verification Freeze** | **Modern Context & Phonetic Fallback**: Intelligent phonetic fallback and domain dictionaries prevent release freezes on unlisted proper names. |
| 14 | **Remotion Streamcopy Myth** | **Native FFmpeg Streamcopy**: Uses FFmpeg `-c:a copy` for genuine zero-loss audio passthrough. |
| 15 | **"All" Mode Resource Explosion** | **Selective On-Demand Rendering**: Replaces brute-force 12-variant exports with targeted on-demand rendering. |
| 16 | **Zero Real-World Video Tests** | **Reference-Calibrated Baseline**: Pacing and visual rules calibrated against real-world video footage (`Dr_Rajiv_AI_Invitation_Premium_Vertical_9x16.mp4`). |
| 17 | **Still Gate Context Explosion** | **Programmatic Spot-Check Gate**: Verifies geometry in code, passing only 2–3 key milestone frames for visual spot-checks. |
| 18 | **Windows Path Colon Crashes** | **Windows Path Normalizer**: Converts `D:\path` to safe FFmpeg syntax (`D\:/path`) in filtergraphs. |

---

## 5. Repository Structure

```text
OmniEdit-Pro-Video-Editing-Skill/
├── README.md                             <-- Quick start, copy-paste prompt & architecture
├── LICENSE                               <-- MIT License
├── skills/
│   └── omni-edit-pro/                    <-- SINGLE UNIFIED PURE SKILL
│       ├── SKILL.md                      <-- Main hub + interactive question flow
│       └── references/                   <-- Consolidated, defect-free guidelines
│           ├── selection.md              <-- Interactive inquiry & mode rules
│           ├── local-cutout.md           <-- RVM MobileNetV3 specs & invocation
│           ├── motion-design.md          <-- Dynamic speech-synced animation rules
│           ├── transcription-sync.md     <-- Smart spelling & modern content agent
│           ├── layouts-effects.md        <-- Fixed geometry & quadrant subtitles
│           ├── editing-styles.md         <-- Composition layouts (Full-screen Overlay)
│           ├── audio-rendering.md        <-- FFmpeg streamcopy & 2x rasterization
│           ├── video-reviewer.md         <-- Programmatic automated QA gate
│           ├── batch-teams.md            <-- Full-mesh multi-agent coordination
│           ├── reference-analysis.md     <-- Reference profiling & card backings
│           ├── quality-assurance.md      <-- Smart tolerance tuning
│           └── delivery.md               <-- Safe promotion to Final Output Videos
```

---

## 6. Verification & System Requirements

Ensure the following core tools are installed on your host system:

```bash
# Check FFmpeg and FFprobe
ffmpeg -version
ffprobe -version

# Check Python environment (PyTorch and Pillow)
python -c "import torch; print('PyTorch:', torch.__version__)"
python -c "import PIL; print('Pillow:', PIL.__version__)"
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
