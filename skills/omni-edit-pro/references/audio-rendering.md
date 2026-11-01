# Audio Finishing, 2x Supersampling, and FFmpeg Rendering

Read when rendering, compositing, mixing audio, and encoding final video deliverables. Use **FFmpeg** directly in the workspace for all video composition, audio streamcopy, and rendering operations.

---

## 1. Bit-Identical Audio Streamcopy (Resolves Issue 14)

Audio quality is paramount in video editing:
- **Direct Streamcopy (`-c:a copy`)**: Whenever container and timeline allow, audio is passed through without re-encoding using native FFmpeg. This avoids generational loss, preserves original dynamic range, and maintains bit-identical sample accuracy.
- **Muxing Audio with Processed Visuals**:
  ```bash
  ffmpeg -y \
    -i "Working Files/video_01/visual_composite.mp4" \
    -i "raw_source.mp4" \
    -c:v copy \
    -c:a copy \
    -map 0:v:0 -map 1:a:0 \
    "Final Output Videos/video_01/delivered_video.mp4"
  ```
- **Lip-Sync Precision**: Direct streamcopy guarantees zero audio drift between the start, middle, and tail of the video.

---

## 2. Selective 2x Text Supersampling (Resolves Issue 11)

To achieve crisp typography and badge edges without crashing into 8K GPU memory limits:
- **Selective Vector/Pillow Rasterization**: Only text elements, badges, and graphic cards are rendered at 2x dimensions and downsampled with high-quality Lanczos-3 antialiasing.
- **Background Video at 1x**: Raw video footage remains at 1x resolution. This completely eliminates Chromium Puppeteer out-of-memory crashes and 8K frame buffer blowups.
- **Lanczos-3 Downsampling**: Downsample 2x raster cards using Pillow's `Image.Resampling.LANCZOS` before compositing onto the 1x video canvas.

---

## 3. Windows-Safe Path Escaping in Filtergraphs (Resolves Issue 18)

On Windows, absolute file paths contain drive colons and backslashes (e.g. `D:\OmniEdit-Pro-Video-Editing-Skill\...`):
- In FFmpeg `-filter_complex` expressions, `:` is a filter option delimiter and `\` is an escape character. Passing raw Windows paths directly into filtergraphs causes fatal syntax crashes.
- Escape drive colons and convert backslashes as follows:
  ```python
  def escape_ffmpeg_path(p: str) -> str:
      # e.g., "D:\videos\input.mp4" -> "D\:/videos/input.mp4"
      normalized = p.replace("\\", "/")
      if len(normalized) > 1 and normalized[1] == ":":
          return normalized[0] + "\\:" + normalized[2:]
      return normalized
  ```

---

## 4. Free Native FFmpeg Compositing (Resolves Issue 9)

Avoid proprietary licensing traps and Chromium browser dependencies by using native FFmpeg compositing:

- **Split Screen**:
  ```bash
  ffmpeg -y \
    -i "Working Files/speaker.mp4" \
    -i "Working Files/diagrams.mp4" \
    -filter_complex "[0:v]scale=960:1080[left];[1:v]scale=960:1080[right];[left][right]hstack[outv]" \
    -map "[outv]" -map 0:a \
    -c:v libx264 -crf 18 -c:a copy \
    "Final Output Videos/video_01/split_final.mp4"
  ```

- **Cutout Composite**:
  ```bash
  ffmpeg -y \
    -i "Working Files/motion_bg.mp4" \
    -i "Working Files/foreground.mp4" \
    -i "Working Files/alpha_matte.mp4" \
    -filter_complex "[0:v]scale=1080:1920[bg];[1:v]scale=1080:1920[fg];[2:v]scale=1080:1920[alpha];[fg][alpha]alphamerge[cutout];[bg][cutout]overlay=0:0[outv]" \
    -map "[outv]" -map 1:a \
    -c:v libx264 -crf 18 -c:a copy \
    "Final Output Videos/video_01/cutout_final.mp4"
  ```

---

## 5. High-Quality Delivery Encoding Standards

- **Codec**: `libx264`, `preset medium` or `slow`, `crf 18` (visually lossless delivery).
- **Pixel Format**: `yuv420p` for universal mobile and web playback compatibility.
- **Color Range & Primaries**: Preserve `bt709` tags from raw camera source.
