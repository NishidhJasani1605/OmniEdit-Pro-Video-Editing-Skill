# Layouts and effects

Read when composing presenter footage, supporting visuals, captions, and informational overlays. Apply the selected treatment from [visual-planning.md](visual-planning.md); use [motion-design.md](motion-design.md) only when motion helps explain or emphasize the content.

## Establish the composition geometry

Set the target dimensions and aspect ratio from the brief. Define a reusable spacing scale and regions for the main subject, supporting information, captions, and source attribution. Inspect the actual footage to identify protected regions: moving faces, hands during demonstrations, product details, interface controls, existing subtitles, and significant action.

Treat safe areas as delivery-specific. Inspect the intended platform's current interface or supplied template before choosing margins for controls, titles, and captions. A generic percentage is only a starting assumption, not a guarantee. Check the exported video at its likely display size and review each requested aspect ratio independently; a portrait version needs composition decisions rather than a blind center crop.

Measure text with the actual font and language. Reserve space for longer strings, diacritics, right-to-left text, and font fallback. Ensure fonts and assets are loaded before capturing preview frames. Prefer a simpler stable layout when automatic tracking or reliable measurement is unavailable.

## Choose the layout by purpose

| Layout | Best use | Checks |
| --- | --- | --- |
| Full-frame presenter | Expression, explanation, personal connection | Preserve eye line, headroom, gestures, and usable caption space |
| Floating overlay | A label, small statistic, icon, or concise diagram | Place in genuine negative space; avoid competing focal points |
| Picture-in-picture | A demonstration with continuing presenter presence | Keep both the demonstrated detail and face readable |
| Split screen | A comparison, interview, or simultaneous explanation | Allocate width by information needs; preserve equal scales when comparing |
| Full-frame supporting visual | A detailed diagram or relevant footage | Preserve the underlying narrative clock and return without a discontinuity |

For talking-head and narrated material, keep continuous source footage underneath when applicable. Reframe that playback without resetting its source time. If separate instances are necessary for a layout change, maintain identical source-time mapping and avoid duplicated audio. Do not freeze or loop a visibly speaking presenter while their speech continues.

## Protect faces and captions

Check whether existing captions are burned into pixels or carried in a selectable subtitle track. Avoid duplicate caption layers. Replacing burned-in text requires an agreed clean source, crop, or masking treatment and visual verification; do not assume the underlying picture can be recovered.

Plan caption regions against face and object motion across the entire cue, not a single screenshot. Move an overlay to another stable region, reduce its footprint, or choose another layout when a collision occurs. Avoid repeatedly chasing a face with captions; position changes can become a distraction themselves.

Group captions into readable phrases and retain accurate timing, spelling, speaker meaning, and punctuation. Use sufficient contrast against changing footage, with a restrained backing plate or shadow where needed. Keep highlighted words synchronized through [transcription-sync.md](transcription-sync.md). Prevent overlap between subtitles, lower thirds, data labels, and platform controls. Do not encode essential distinctions solely by color.

## Use effects as information

Anchor callouts to the correct object and verify tracking through movement and occlusion. Do not let arrows imply an unsupported direction or relationship. For split-screen comparisons, keep labels persistent and disclose differing scale, time, or conditions when relevant. Limit blur, glow, and decoration when they weaken evidence or text clarity.

Transitions should signal a justified change in topic, time, place, or visual focus. Apply overlay transitions without shortening the continuous source track. Keep a consistent layer order and inspect mask edges, transparency, crop boundaries, and overlap at entry and exit. Render the most crowded composition before duplicating it, then check the final frame with captions, identifiers, and source notes all visible together.
