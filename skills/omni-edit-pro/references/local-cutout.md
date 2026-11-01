# Free Local Speaker Cutouts (Robust Video Matting MobileNetV3)

Cutout means isolating the presenter's natural silhouette from their background so they can float over high-tech animated backgrounds, diagrams, and motion graphics. OmniEdit Pro directs the agent to use **Robust Video Matting (RVM)** by PeterL1n (`https://github.com/PeterL1n/RobustVideoMatting`) with the lightweight **MobileNetV3** backbone.

---

## 1. Tool Specification: Robust Video Matting (RVM)

RVM is a recurrent neural network designed specifically for robust human video matting without green screen.

```
                    +-----------------------------+
Raw Camera Video -->|  RVM MobileNetV3 Backbone   |--> Foreground RGB Video
                    |  (15 MB Pretrained Weights) |
                    +-----------------------------+--> Grayscale Alpha Video
                                   |
                         Recurrent States (r1-r4)
                                   v
+--------------------------------------------------------------------------+
|                       FFmpeg Alphamerge Compositor                       |
|   [bg][fg][alpha]alphamerge[cutout];[bg][cutout]overlay=0:0[final_video]  |
+--------------------------------------------------------------------------+
```

### Key Technical Specs:
- **Repository**: [PeterL1n/RobustVideoMatting](https://github.com/PeterL1n/RobustVideoMatting)
- **Model Backbone**: `rvm_mobilenetv3.pth` (15MB lightweight weights, auto-cached via PyTorch Hub).
- **Execution Tool**: PyTorch in the user's workspace.
- **Hardware Compatibility**: Runs fast on CPU (standard laptop/workstation) and ultra-fast with CUDA GPU acceleration.
- **Temporal Recurrence**: Maintains internal recurrent memory states (`r1`, `r2`, `r3`, `r4`) across frames to prevent edge crawl and matte flicker.

---

## 2. Tool Invocation Recipe in the Workspace

When performing a Cutout edit, the agent executes RVM in the local working directory using the official PyTorch Hub API:

```python
import torch

# 1. Load the official RVM model with MobileNetV3 backbone
model = torch.hub.load("PeterL1n/RobustVideoMatting", "mobilenetv3").cuda() # or .cpu()
convert_video = torch.hub.load("PeterL1n/RobustVideoMatting", "converter")

# 2. Extract alpha matte and foreground video
convert_video(
    model,
    input_source="Working Files/video_01/source.mp4",
    output_type="video",
    output_composition=None,
    output_alpha="Working Files/video_01/alpha_matte.mp4",
    output_foreground="Working Files/video_01/foreground.mp4",
    output_video_mbps=4,
    downsample_ratio=0.25, # fast inference
    seq_chunk=12
)
```

---

## 3. Lossless Compositing with FFmpeg Alphamerge

Once the foreground and alpha matte are extracted, composite them over the animated background using standard **FFmpeg** CLI:

```bash
ffmpeg -y \
  -i "Working Files/video_01/background_motion.mp4" \
  -i "Working Files/video_01/foreground.mp4" \
  -i "Working Files/video_01/alpha_matte.mp4" \
  -filter_complex "[0:v]scale=1080:1920[bg];[1:v]scale=1080:1920[fg];[2:v]scale=1080:1920[alpha];[fg][alpha]alphamerge[cutout];[bg][cutout]overlay=0:0:shortest=1[outv]" \
  -map "[outv]" -map 1:a \
  -c:v libx264 -preset fast -crf 18 \
  -c:a copy \
  "Final Output Videos/video_01/final_cutout_1080x1920.mp4"
```

> **Windows Note**: In Windows paths, always replace drive colons with `D\:/` when referencing files inside the `filter_complex` string to avoid FFmpeg argument parsing errors.

---

## 4. Silhouette Space & Background Animation Rules

1. **No Bounding-Box Panel**: The cutout subject is strictly the person's true silhouette. Do not place a square backing card, border, or reserved rectangular opaque panel behind or around them.
2. **Transparent Negative Space is Usable**: Transparent gaps between arms and torso or above shoulders are genuine negative space. Dynamic background graphics can move continuously behind the presenter.
3. **Speech Sync Integrity**: The original narration stream is copied directly (`-c:a copy`) to preserve bit-identical lip sync with zero audio drift.
