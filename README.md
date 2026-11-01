# OmniEdit Pro (Unified Pure Skill Edition)

**A unified, instruction-only AI video editing skill equipped with local AI matting, dynamic speech-synced animation, and automated programmatic QA.**

OmniEdit Pro transforms raw video footage into polished, high-retention video deliverables across any orientation (9:16 vertical, 16:9 horizontal) and layout (Split Screen, Cutout with RVM, Full-Screen Overlay, Adaptive).

**Version:** 4.0.0 · **Architecture:** Single Unified Pure Skill (`skills/omni-edit-pro`) · **License:** MIT

```
+-----------------------------------------------------------------------------+
|                            USER INPUT                                       |
|               (Raw Footage + Optional Style Sample/Prompt)                  |
+-----------------------------------------------------------------------------+
                                     |
                                     v
+-----------------------------------------------------------------------------+
|                     SMART INTERACTIVE CLARIFICATION                         |
|         (Auto-detects or prompts user: Orientation, Layout & Style)         |
+-----------------------------------------------------------------------------+
                                     |
                                     v
+-----------------------------------------------------------------------------+
|                     OMNIEDIT PRO TOOL DIRECTIVES                            |
|  RVM MobileNetV3         Pillow (PIL) Geometry      FFmpeg Windows Engine   |
|  (Local AI Matting)      (Layout & Collision Math)  (Lossless Compositor)   |
+-----------------------------------------------------------------------------+
                                     |
                                     v
+-----------------------------------------------------------------------------+
|                    AUTOMATED PROGRAMMATIC REVIEWER                          |
|         (Mathematical Collision Checks + Audio Waveform Verification)       |
+-----------------------------------------------------------------------------+
                                     |
                                     v
+-----------------------------------------------------------------------------+
|                        FINAL OUTPUT PROMOTION                               |
|                 <workspace>/Final Output Videos/<video-id>/                 |
+-----------------------------------------------------------------------------+
```

---

## 1. Quick Start

### Basic Invocation:
Provide your raw footage and optionally a style reference or creative prompt:

```text
Edit my-video.mp4 using OmniEdit Pro.
```

If your prompt lacks orientation or layout details, OmniEdit Pro presents a clear interactive questionnaire before processing:

```text
Step 1: Target Video Orientation
1. 9:16 Vertical (Recommended for Mobile - Reels, Shorts, TikTok)
2. 16:9 Horizontal (Widescreen - YouTube, Desktop)
3. Auto-Detect from Source Footage

Step 2: Editing Style & Layout
1. Split Screen (Presenter on one side, diagrams on other)
2. Cutout (AI Background Removal via local RVM MobileNetV3)
3. Overlay (100% Intact camera footage with sleek titles/badges on top)
4. Auto-Select / Adaptive (AI chooses optimal layout scene-by-scene)
5. Custom Idea (Describe your own creative vision, e.g. PiP circle, code tutorial)
```

---

## 2. Tool Directives (Which Tool to Use for Which Purpose)

OmniEdit Pro is a **pure Markdown instruction skill** (no bundled `.py` files inside the skill repository). It directs the AI coding agent to leverage proven external tools in the workspace:

| Purpose | Recommended Tool | Directive & Execution in Workspace |
|---|---|---|
| **Speaker Background Cutout** | **Robust Video Matting (RVM)**<br/>(`PeterL1n/RobustVideoMatting`) | Load `rvm_mobilenetv3.pth` via PyTorch to extract clean foreground and alpha masks locally on CPU/GPU. |
| **Speech Transcription & Word Timings** | **OpenAI Whisper** | Run Whisper to generate word-level timestamped transcripts for speech-synced animation. |
| **Transcript Intelligence & Spelling** | **AI Content Agent** | Normalizes homophones, fixes brand/tech spelling, generates 3–5 word summary titles, and ensures modern version names. |
| **Typography & Layout Math** | **Pillow (`PIL.ImageFont`)** | Measures exact glyph bounding boxes, line wrapping, and ensures text does not collide with the speaker's face. |
| **Video Compositing & Audio Passthrough** | **FFmpeg CLI** | Blends video layers, downsamples graphics via Lanczos-3, preserves lossless audio (`-c:a copy`), and escapes Windows paths (`D\:/...`). |

---

## 3. How All 18 Identified Deadlocks Are Solved

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

## 4. Directory Structure

```text
OmniEdit-Pro-Video-Editing-Skill/
├── README.md
├── LICENSE
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
│           ├── batch-teams.md            <-- Automatic solo execution fallback
│           ├── reference-analysis.md     <-- Reference profiling & card backings
│           ├── quality-assurance.md      <-- Smart tolerance tuning
│           └── delivery.md               <-- Safe promotion to Final Output Videos
```

---

## 5. Verification & Tool Checking

Verify that required host tools are available on your system:

```bash
# Check FFmpeg and FFprobe
ffmpeg -version
ffprobe -version

# Check Python environment (PyTorch and Pillow)
python -c "import torch; print('PyTorch:', torch.__version__)"
python -c "import PIL; print('Pillow:', PIL.__version__)"
```
