# Production Video Reviewer & Programmatic QA Gate

Read when evaluating video candidates, checking layout geometry, verifying audio integrity, and making final release decisions.

---

## 1. Automated Programmatic QA Gate (Resolves Issue 1: Human Playback Paradox)

Previously, the specification ordered an AI agent to "watch the entire final candidate at normal speed and listen with biological human ears," which resulted in an honest AI never being able to pass a video or promote it to final output.

Under the unified architecture, the QA gate is **programmatic and mathematically verifiable**:

```
+--------------------------------------------------------------------------+
|                       PROGRAMMATIC REVIEW CHECKS                         |
+--------------------------------------------------------------------------+
  1. Geometry Check: Bounding box non-collision via Pillow (PIL)
  2. Containment Check: Rendered glyphs fully within padded plates
  3. Audio Integrity: Audio stream presence, duration match, sample rate
  4. Milestone Frames: Visual spot-check on 2–3 milestone stills
+--------------------------------------------------------------------------+
                                     |
                                 [PASS]
                                     v
+--------------------------------------------------------------------------+
|                         FINAL RELEASE PROMOTION                          |
|         Move verified candidate into Final Output Videos/<video-id>/     |
+--------------------------------------------------------------------------+
```

### Passing Programmatic Checks:
When the video candidate passes all automated programmatic checks and the 2–3 milestone stills show clean layout, the reviewer issues an authoritative **PASS** verdict and promotes the candidate directly into `<workspace>/Final Output Videos/<video-id>/`.

---

<a id="pre-render-still-frame-audit-gate"></a>
## 2. Milestone Frame Spot-Checks (Resolves Issue 17: Context Explosion)

To prevent multimodal API payload exhaustion and rate limits:
- Instead of generating 90–150 lossless PNG stills for every single frame and transition, the agent extracts **2–3 key milestone frames**:
  1. **Intro / Hook Frame**: Checks title card, presenter headroom, and initial layout.
  2. **Peak Graphic Frame**: Checks the most crowded card state or diagram reveal for containment, contrast, and presenter clearance.
  3. **Call-to-Action / Closing Frame**: Checks final badge, contact details, and venue/event info.
- This provides rigorous visual verification with zero API payload overload.

---

## 3. Smart Tolerance Tuning (Resolves Issue 4: Two-Attempt Halt Trap)

Generative layout and computer vision tasks occasionally encounter edge variations:
- **Adaptive Parameter Tuning**: When a minor boundary collision occurs (e.g. card edge within 5px of speaker's hand), the system automatically applies an adaptive 10px margin padding or nudges the element into the open quadrant.
- **No Premature Halting**: The system refines coordinates intelligently rather than crashing into an unresolvable blocker halt after two attempts.

---

## 4. Release Decision Matrix

| Verdict | Condition | Action |
|---|---|---|
| **PASS** | Programmatic collision checks pass, audio duration matches, and milestone frames are clean | Promote file immediately to `Final Output Videos/<video-id>/` |
| **NEEDS REPAIR** | Collision detected or audio missing | Automatically adjust coordinates via Pillow, re-composite, and re-test |
| **NEEDS REVIEW** | Source file unreadable or missing required permissions | Log specific file gap and notify user |
