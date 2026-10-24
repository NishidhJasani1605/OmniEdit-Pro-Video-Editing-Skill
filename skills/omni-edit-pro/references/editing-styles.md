# Three styles in two orientations

The selected style is a composition contract. General layout suggestions in other references must stay within it. Read [Layouts and effects](layouts-effects.md) for caption placement and [Motion design](motion-design.md) for animation. Horizontal is 16:9; vertical is 9:16. Choose delivery dimensions from the source, destination and brief rather than upscaling everything by default.

## Source framing and person size

For Split and Overlay, display the full decoded source frame after honoring rotation and pixel aspect ratio. Use a uniform fit, never stretch or fill-by-cropping. For a source of display size `Ws × Hs` and an available region `Wr × Hr`, the contain scale is `min(Wr/Ws, Hr/Hs)`. Center or deliberately align the resulting rectangle and fill spare canvas outside it with a calm designed background. Do not crop away existing subtitles or source borders without an explicit change request.

The speaker's original on-screen detail is the quality reference. Inspect the face, head, shoulders, visible body and moving gestures across the clip. Avoid making the speaker a tiny thumbnail to fit excessive graphics. Enlarge the speaker region, simplify graphics and change their arrangement first. No automatic punch-ins, source camera pushes, face tracking that trims the body, stretched footage or artificial face reconstruction.

Fit may require downscaling or padding. Preserving full source framing, identical displayed person size and full-screen coverage can be incompatible across shapes. Explain the concrete geometry if the brief demands all three; show a fitted preview or ask for the specific tradeoff. Do not silently compromise framing or promise pixel-identical re-encoded output. Never invent body parts outside the source.

## Split

- Horizontal: speaker region on the left or right, explanation region beside it.
- Vertical: speaker region above or below, explanation region in the remaining height.
- Use the user's specified position; otherwise choose from actual gaze/gestures and available content, then keep it stable.
- Fit the entire original video inside the speaker region. Choose the region's size from the source aspect ratio and person visibility, not an arbitrary 50/50 split. A wide source may need a wider speaker region; simplify the explanation to protect the speaker.
- Use cards, diagrams, labels, original illustrations or relevant clips in the explanation region. Keep the underlying speaker playing continuously with original sound. Do not replace this style with a tiny floating head or full-screen B-roll.
- Reflow explanation content for portrait output. A detailed horizontal diagram can become a progressive vertical sequence while speech timing stays unchanged.

## Cutout

Read [Local cutouts](local-cutout.md). Isolate the speaker from the background using real frame-derived alpha/masks, preserving visible subject detail, movement and timing. Place that foreground over a coherent graphic background, usually lower/central if the content supports it. There is no separate rectangular presenter panel. Do not cut off head, hair, hands or shoulders to imitate a reference image.

Keep explanations away from the moving silhouette and reserve caption space. Use the available canvas to make the speaker readable without excessive enlargement. Background removal does not authorize skin smoothing, face changes, regenerated speech or retiming. Reject unstable mattes rather than disguising defects with heavy blur.

## Overlay

Keep the original footage and background together as the main continuous image. If source and target shapes match, it occupies the canvas; otherwise fit the complete source with deliberate padding. Do not push it into a side/top presenter panel, remove its background, or cover it with a replacement full-frame scene.

Add suitable cards, progress/day badges, diagrams, labels and captions directly over protected free areas. Keep the speaker prominent. Prefer one useful visual idea at a time; reduce density when the source has little free space. Make the card adapt to the footage, not the footage zoom/crop to fit the card. Any audio waveform must be derived from the audio if it is presented as a measurement; decorative movement must not imply measured data.

## Acceptance per variant

Check the delivered shape, selected style and position; full source fit for Split/Overlay; speaker visibility at actual viewing size; hair/hand integrity for Cutout; no unwanted zoom/stretch/crop; no face or gesture obstruction; readable holds; preserved speech and timing. Compare matching source/output timestamps, including movement extremes, not only a flattering still. A different style needs a user instruction, not an agent's convenience.
