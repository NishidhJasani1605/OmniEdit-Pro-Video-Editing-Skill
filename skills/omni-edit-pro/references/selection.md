# Intent, Input Roles, and Interactive Selection

Read this before starting an edit. OmniEdit Pro resolves user intent from the prompt, interactive questionnaire, and input file inspection.

---

## 1. Interactive Clarification Flow

When the user provides raw footage or a prompt without fully specifying the target orientation and layout style, the agent triggers the interactive clarification flow before dispatching any editing tasks:

### Step 1: Target Video Orientation
1. **9:16 Vertical (Recommended for Mobile)** — Optimized for Instagram Reels, TikTok, YouTube Shorts.
2. **16:9 Horizontal (Widescreen)** — Optimized for YouTube, desktop presentations, LinkedIn widescreen.
3. **Auto-Detect** — Match whatever orientation the raw video was recorded in.

### Step 2: Editing Style & Layout
1. **Split Screen** — Divides the canvas: presenter in one zone (left or bottom), diagrams and cards in the other.
2. **Cutout (AI Background Removal)** — Uses local RVM MobileNetV3 to extract the speaker like a clean sticker, floating over high-tech animated backgrounds.
3. **Overlay (Clean & Non-Intrusive)** — Keeps 100% of your camera video full-screen; layers stylish glassmorphic title plates, captions, and badges over natural empty spaces.
4. **Auto-Select / Adaptive** — Let the AI inspect the video and automatically pick the best look for the topic.
5. **Custom / Your Own Idea** — Have a specific look in mind? (e.g. "Picture-in-picture circle", "Documentary retro look", "Side-by-side code tutorial"). Describe it and the AI builds custom styling to match your idea!

---

## 2. Input Role Identification & Batch Safety (Resolves Issue 7)

Record each input file's role: **source target**, **style reference**, or **supporting asset**.

### Batch Input Protection:
In multi-video submissions, **all submitted videos are treated as independent source targets by default**. 
- A video with an intro card, participant name plate, or corner watermark (such as a Zoom recording) **MUST NOT** be automatically misclassified as a style reference for other videos in the batch.
- A file is treated as a style reference **only if** the user explicitly designates it as such (e.g. `--reference`, "use X as sample", or in interactive selection).
- Every source video gets its own independent edit job and output.

<a id="zero-configuration-automatic-role-classification"></a>
### Zero-Configuration Heuristic Classification (When Single Inputs Arrive):
When a single video arrives without instructions, inspect 2–3 FFmpeg-decoded frames:
- **Raw Camera Footage**: Natural room background, no pre-rendered graphics or burned-in titles -> **Source Target**.
- **Edited Video with Graphics**: Pre-rendered split-screen, topic cards, or burned-in subtitles -> Checked with user if intended as a reference sample or raw footage to re-edit.

---

## 3. Creative Directions

| Direction | Trigger Condition | Execution Behavior |
|---|---|---|
| **Interactive / Manual** | User did not specify orientation or style, or explicitly wants manual control | Prompts user with the 2-step questionnaire, then applies selected choices |
| **Reference** | An explicitly designated sample is provided | Analyzes reference typography, color palette, cut pacing, and animation style via [reference-analysis.md](reference-analysis.md) |
| **Auto** | Raw footage provided with instructions to auto-detect | Classifies content and selects optimal layout via [auto-direction.md](auto-direction.md) |

---

## 4. Unified Deliverables Matrix

All presets are unified under `omni-edit-pro`:

| Selected Orientation | Selected Layout | Output Deliverable |
|---|---|---|
| **9:16 Vertical** | Split | Vertical 9:16 Reel (Split screen: upper animation, lower footage) |
| **9:16 Vertical** | Cutout | Vertical 9:16 Reel (Speaker isolated via RVM over full-canvas background) |
| **9:16 Vertical** | Overlay | Vertical 9:16 Reel (100% full-screen camera video with top/bottom overlays) |
| **16:9 Horizontal** | Split | Horizontal 16:9 Master (Left/right split with quadrant subtitles) |
| **16:9 Horizontal** | Cutout | Horizontal 16:9 Master (Speaker isolated via RVM over animated canvas) |
| **16:9 Horizontal** | Overlay | Horizontal 16:9 Master (Full widescreen video with card-attached backings) |
| **Auto / Adaptive** | Adaptive | Dynamic scene-by-scene composition transitions |
| **Custom Idea** | Custom | Custom layouts matching user's specific prompt description |
