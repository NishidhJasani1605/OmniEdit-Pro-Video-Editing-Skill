# Layouts, Effects, and Geometric Precision

Read when composing video footage with graphic cards, titles, subtitle badges, and overlays. Use **Pillow (PIL)** in the workspace for all layout and bounding-box calculations.

---

<a id="geometry-and-layouts"></a>
## 1. Full-Screen 9:16 Vertical Overlay (Resolves Issue 2)

In Vertical Overlay mode ($1080 \times 1920$):
- **Intact Camera Footage**: When raw source footage is recorded in 9:16 portrait, it remains **100% full-screen ($1080 \times 1920$)**.
- **No Shrunken Thumbnail Collapse**: The source footage is **never** shrunken down to fit inside a lower 600px box (which previously produced a 337.5px pillarbox thumbnail with black bars).
- **Non-Intrusive Layering**: Clean glassmorphic cards, category pills, and title plates layer directly on top of the video in natural empty spaces (headroom, upper canvas, or lower third), keeping the presenter full-size and natural.

---

## 2. Quadrant-Anchored Horizontal Split Subtitles (Resolves Issue 3)

In Horizontal Split mode ($1920 \times 1080$):
- **Dividing Seam**: The screen is split into two halves: Left Column ($X=0\text{ to }960$) and Right Column ($X=960\text{ to }1920$).
- **No Seam Collisions**: Subtitles are **never** centered on the dividing line ($X=960$), which collides with the speaker's body.
- **Quadrant Anchoring**: Subtitles are anchored cleanly within their designated active quadrant:
  - Inside Speaker Quadrant: Centered at $X \approx 480$ in the lower third.
  - Inside Graphic Quadrant: Centered at $X \approx 1440$ below the active diagram/card stack.

---

## 3. Card-Attached Local Backings (Resolves Issue 5)

In Overlay and Widescreen layouts:
- **Card-Attached Backing**: Instead of painting a canvas-wide dark gradient scrim (which cuts off before wide cards or casts an unwanted shadow across the speaker's body), **each text card and badge carries its own local soft blur plate or glassmorphic container**.
- **100% Contrast Everywhere**: The local backing moves with the card, guaranteeing WCAG AAA contrast regardless of whether the background footage changes from light to dark, while keeping the presenter's clothing and face completely unshaded.

---

<a id="allocate-space-before-sizing-panels"></a>
## 4. Text Measurement & Containment Using Pillow (Resolves Issue 8)

The agent measures text bounds accurately using Python's Pillow library in the workspace:

```python
from PIL import ImageFont

font = ImageFont.truetype("arial.ttf", size=44)
bbox = font.getbbox("PATIENT CONFIDENTIALITY") # (left, top, right, bottom)
text_width = bbox[2] - bbox[0]
text_height = bbox[3] - bbox[1]

# Padding specifications:
min_h_pad = 24  # min 24px horizontal padding per side
min_v_pad = 16  # min 16px vertical padding top and bottom

pill_width = text_width + (2 * min_h_pad)
pill_height = text_height + (2 * min_v_pad)
```

- **Minimum Horizontal Padding**: At least 24 pixels per side at 1080px canvas width, scaled proportionally with resolution (`scale = max(1.0, width / 1080)`).
- **Vertical Padding**: At least 16 pixels top and bottom, accounting for font ascenders and descenders.
- **Visible Bounds Centering**: Headings and titles are centered inside their content boxes by optical visible glyph bounds, compensating for left bearing:
  $$X_{\text{origin}} = X_{\text{box}} + \frac{W_{\text{box}} - W_{\text{visible}}}{2} - \text{bearing}_{\text{left}}$$

---

## 5. Automated Collision Avoidance (Resolves Issue 4)

Before rendering, verify that the card layout rectangle does not intersect the speaker's bounding box:

```python
def check_collision(box_card, box_speaker):
    # box format: [x1, y1, x2, y2]
    overlap_x = max(0, min(box_card[2], box_speaker[2]) - max(box_card[0], box_speaker[0]))
    overlap_y = max(0, min(box_card[3], box_speaker[3]) - max(box_card[1], box_speaker[1]))
    return (overlap_x * overlap_y) > 0

# If collision detected: apply an automatic 10px-20px offset or shift to opposite quadrant
```
