# Final Outputs and Delivery

Resolve the user's chosen editing workspace during intake. Never use an installed skill folder as the editing workspace. Use the folder name **Final Output Videos** unless the user explicitly requests another delivery directory.

---

## 1. Directory Structure

Inside the user's editing workspace:

```text
Working Files/
    <video-id>/
        plan.md
        audio/
        cutout/
        previews/
        candidate_renders/
Final Output Videos/
    <video-id>/
        <video-id>_final.mp4
```

---

## 2. Programmatic Final Promotion Gate (Resolves Issue 1)

Renders are authored and checked in `Working Files/<video-id>/` first. 
- Promotion to `Final Output Videos/<video-id>/` occurs immediately upon the candidate achieving a **PASS** verdict from the Production Video Reviewer.
- Passing the automated mathematical checks (bounding box non-collision via Pillow, verified text containment, audio stream and duration match) and milestone frame spot-checks constitutes full QA clearance.
- Once verified, the completed video is promoted to `Final Output Videos/<video-id>/`.

---

## 3. Delivery Report

Upon promoting final video files, provide the user with:
1. Exact file paths to deliverables in `Final Output Videos/`.
2. Output specifications: resolution, aspect ratio, frame rate, duration, and codec.
3. Summary of chosen layout (Split, Cutout, Overlay, Adaptive, or Custom) and creative styling applied.
