# Layouts and effects

Read when composing presenter, screen, action or other footage with supporting visuals, captions and informational overlays. Composition is separate from creative treatment. The resolved contract in [Editing styles](editing-styles.md) takes precedence over general layout suggestions here; reference observations cannot override an explicit preset or user choice. Apply [Visual planning](visual-planning.md) and [Motion design](motion-design.md) within that contract.

## Establish the composition geometry

Set dimensions and display aspect from the resolved output record before variant/render jobs. Explicit user output choices outrank explicitly selected preset defaults, then applicable reference shape, then Auto/source evidence. When no stronger shape applies, Adaptive preserves the source display ratio, including square/custom shapes. Account for rotation and pixel aspect; select compatible encoded dimensions without distorting content. A later orientation override changes that dimension only.

Define a reusable spacing scale and regions for the main subject, supporting information, captions when present, and source attribution. Inspect actual footage to identify protected regions: moving faces, hands during demonstrations, product details, cursor/action paths, interface controls, existing subtitles, and significant action.

For a vertical/Reels scene with a real presenter, follow the shared [portrait ordering](editing-styles.md#reels-presenter-below-animation-above): speaking source or silhouette below, primary animation above in every composition. Fit original footage/background below for Split/Overlay and presenter-led Adaptive; do not silently keep a matching-ratio Overlay full-canvas. Cutout is a lower alpha silhouette over a full-canvas graphic scene, not a lower rectangular panel. Determine sizes from actual framing and readability; a visible or invisible fixed square around the person is not a Cutout geometry rule. An explicit placement override wins, and non-presenter footage keeps appropriate scene layout.

Treat safe areas as delivery-specific. Inspect the intended platform's current interface or supplied template before choosing margins for controls, titles, and captions. A generic percentage is only a starting assumption, not a guarantee. Check the exported video at its likely display size and review each requested aspect ratio independently; a portrait version needs composition decisions rather than a blind center crop.

Measure text with the actual font and language. Reserve space for longer strings, diacritics, right-to-left text, and font fallback. Ensure fonts and assets are loaded before capturing preview frames. Prefer a simpler stable layout when automatic tracking or reliable measurement is unavailable.

## Choose the layout by purpose

| Layout | Best use | Checks |
| --- | --- | --- |
| Source-native full frame | Performance, scenery, action, screen detail, or presenter expression | Preserve important picture/action, source aspect, screen text and caption space |
| Floating overlay | A label, small statistic, icon, or concise diagram | Place in genuine negative space; avoid competing focal points |
| Picture-in-picture | A demonstration with continuing presenter presence | Keep both the demonstrated detail and face readable |
| Split screen | A comparison, interview, or simultaneous explanation | Allocate width by information needs; preserve equal scales when comparing |
| Full-frame supporting visual | A detailed diagram or relevant footage | Preserve the underlying narrative clock and return without a discontinuity |

Use this vocabulary within the chosen composition: Split separates fitted source and explanation regions; Cutout uses only an isolated alpha foreground over the whole graphic scene; Overlay retains original footage/background together, in a lower source region for vertical presenter scenes. The six presets inherit these shared defaults. A reference or difficult passage does not authorize a different composition. Keep continuous source-time playback and one original-sound owner; never freeze or loop visibly speaking footage beneath continuing speech.

## Adaptive composition

Adaptive is available through the main workflow for source-native or scene-specific layouts. Vertical presenter scenes use the same lower-source/upper-animation default; non-presenter scenes may retain a performance or landscape full frame or protect a screen demonstration. Integrate meaningful dynamic graphics appropriate to those scenes. Record every layout state, source interval, purpose and protected region. Adaptive is not automatically added to All's six outputs.

Fit the complete source by default, using deliberate padding when ratios differ. A scene-specific layout may reflow graphics or the fitted source region without cutting, retiming or hiding essential source content. Full-frame B-roll replacement, source cropping, source camera pushes, speed changes, montage and reordered shots require corresponding editing permission. Choosing Adaptive alone does not supply that permission. If the source is a mixed-format file, route layout by the inspected scene and review every state and boundary.

Keep layout geometry coherent while graphic content actively develops. A source-native frame or static card alone does not satisfy the default request for dynamic editing. Use source-anchored highlights, diagrams, tracked callouts or other suitable animation without hiding existing action, and use graphic transitions as ideas change. Readable labels may settle while related visual elements evolve; a brief motivated reading hold is not a whole static scene. An explicit minimal/still treatment can override this default. Do not invent a presenter, captions, matting or audio for material without them. Adapt graphics inside a fixed composition rather than invoking Adaptive as a fallback.

## Cutout occupancy and background space

Size/crop metadata for an alpha asset may be rectangular; visible foreground occupancy is the real silhouette. Render the animated background across the entire canvas behind it. Use the time-varying alpha with a small justified safety margin to place foreground text/callouts; inspect the whole display interval and gestures. Do not use the asset's bounding box as a permanent exclusion rectangle. Verified transparent gaps between an arm and torso and clear space near the head remain available. Graphics can pass behind opaque subject pixels; essential text must stay readable in transparent areas or be reflowed/timed around the person. Preserve hair and semi-transparent moving edges without flicker or colored backing. See [Local cutouts](local-cutout.md).

## Protect faces and captions

Check whether existing captions are burned into pixels or carried in a selectable subtitle track. Avoid duplicate caption layers. Replacing burned-in text requires an explicitly agreed clean source or treatment and visual verification. Never crop off a subtitle band or mask it by default; preserve full framing. Do not assume the underlying picture can be recovered.

Plan caption regions against face, object, cursor and action motion across the entire cue, not a single screenshot. Move an overlay to another stable region, reduce its footprint, or reflow within the selected composition when a collision occurs. Avoid repeatedly chasing a face with captions; position changes can become a distraction themselves. Silent footage needs no invented transcript or compulsory caption layer.

Group captions into readable phrases and retain accurate timing, spelling, speaker meaning, and punctuation. Use sufficient contrast against changing footage, with a restrained backing plate or shadow where needed. Keep highlighted words synchronized through [transcription-sync.md](transcription-sync.md). Prevent overlap between subtitles, lower thirds, data labels, and platform controls. Do not encode essential distinctions solely by color.

## Use effects as information

Anchor callouts to the correct object and verify tracking through movement and occlusion. Do not let arrows imply an unsupported direction or relationship. For split-screen comparisons, keep labels persistent and disclose differing scale, time, or conditions when relevant. Limit blur, glow, and decoration when they weaken evidence or text clarity.

Transitions should signal a justified change in topic, time, place, or visual focus. Apply graphic transitions without shortening the protected source track. Translate reference motion to the current content's anchors rather than copying sample event times; a reference cut rhythm cannot override preserved source timing. Keep a consistent layer order and inspect mask edges, transparency, fit boundaries and overlap at entry/exit. Render the most crowded composition and hardest relevant motion before duplicating it, then check the final frame with captions, identifiers and source notes together. Inspect normal-speed playback as well as stills.
