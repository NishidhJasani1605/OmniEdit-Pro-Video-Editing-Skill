# Compositions and Framing Styles

OmniEdit Pro supports four core composition layouts across both 9:16 vertical and 16:9 horizontal formats:

---

## 1. Split Screen

Divides the canvas into distinct, dedicated visual zones:
- **Horizontal 16:9 ($1920 \times 1080$)**: 
  - Left Half ($X=0\text{--}960$): Presenter footage.
  - Right Half ($X=960\text{--}1920$): Animated diagrams, stacked cards, and graphic explanations.
  - Subtitles are quadrant-anchored within the active half (never on the $X=960$ seam).
- **Vertical 9:16 ($1080 \times 1920$)**:
  - Upper Half ($Y=0\text{--}960$): Primary graphic animation, stacked cards, key takeaways.
  - Lower Half ($Y=960\text{--}1920$): Presenter camera footage.
- Continuous audio and natural camera motion are preserved throughout.

---

## 2. Cutout (AI Background Removal via RVM MobileNetV3)

Extracts the speaker's natural silhouette from raw camera footage using PeterL1n's Robust Video Matting (RVM MobileNetV3):
- **Full-Canvas Background**: The speaker floats cleanly over high-tech animated backgrounds and dynamic scene graphics.
- **Natural Negative Space**: No rectangular box or panel is placed around the speaker; animated background elements flow naturally through transparent gaps (such as between arms and torso).
- **Fast Local Execution**: Runs locally without cloud APIs or paid services using bundled MobileNetV3 weights.

---

## 3. Overlay (Clean & Non-Intrusive)

Retains 100% of the original camera video and background:
- **Vertical 9:16 Full-Screen (Resolves Issue 2)**: 
  - When the source video is recorded in 9:16 portrait, it stays **100% full-screen ($1080 \times 1920$)**.
  - It is **never** shrunken into a 337.5px pillarbox thumbnail in the lower canvas!
  - Sleek glassmorphic cards, category badges, and captions layer directly over open negative space (headroom, upper canvas, or lower third).
- **Horizontal 16:9 Full-Screen**:
  - Widescreen camera video displays full canvas, with text plates floating over open background areas.
  - Cards carry their own soft blur backing plates, preventing contrast loss without needing harsh dark scrims across the speaker.

---

## 4. Adaptive Composition

Automatically switches layout modes scene-by-scene based on content:
- Uses Full-Screen Overlay for personal presenter introductions.
- Transitions smoothly to Split Screen when presenting side-by-side technical diagrams or data comparisons.
- Uses Cutout when high-impact visual explanations benefit from an isolated floating subject.
- Preserves continuous timeline and single-track dialogue throughout all state changes.
