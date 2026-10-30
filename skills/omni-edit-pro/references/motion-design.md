# Motion design

Read when implementing animated text, diagrams, callouts, or camera moves. Use the creative brief from [visual-planning.md](visual-planning.md), frame events from [transcription-sync.md](transcription-sync.md), and geometry from [Editing styles](editing-styles.md) and [Layouts and effects](layouts-effects.md). Create implementation code only in the user's editing workspace.

## Develop the graphics throughout the edit

Across Split, Cutout, Overlay and Adaptive, plan purposeful visual development from opening through ending. Build explanations in speech- or action-anchored semantic units as specified below. Animate a relevant mechanism or relationship, advance an active highlight among already introduced items, or transition between source-grounded visual states as the meaning develops. Highlighting a complete future explanation exposed at the start does not count as progressive disclosure. A long frozen card with only an entrance fade and exit fade does not meet this default. Ordinary source playback or an unchanged source-native frame alone does not satisfy the graphic-development plan.

Keep readable labels settled while connectors, examples, focus states or other useful graphic parts progress. Serious, quiet or visually dense scenes can use restrained, low-amplitude development. A short reading hold must have a source interval, a reason and a planned next state; it is not a standing excuse for long static passages. If the user explicitly requests stillness or a static treatment, record its scope and honor that override.

Maintain a per-source motion-coverage and transition plan: source/output interval, semantic purpose, active graphic development, readable settled elements, next state, transition purpose and any justified short hold or explicit stillness override. Cover the whole output rather than just a lively introduction. Suitable transitions connect topics, steps or visual focus without requiring a layout swap or a source cut. Avoid nonstop decorative pulses, random template changes, arbitrary loops and motion that competes with reading. This default grants no permission to cut, zoom, crop or retime the source.

## Reveal one small idea at its source anchor

Before animating, split explanatory graphics into the smallest useful **semantic units**, rather than one paragraph, whole list or full scene card. A unit is one claim, step, comparison item or relationship, usually a short heading with at most one concise supporting clause. Keep a negation, qualification, number and its unit with the claim they modify; a fragment that changes meaning is not a valid chunk. These are explanatory graphics, not a replacement for the complete stationary caption phrases in [Transcription](transcription-sync.md).

Give each unit a verified speech phrase/word ID or inspected action anchor, output onset, first semantically visible frame, settled frame, readable hold, exit and next state. The first pixel that reveals new meaning must occur at or after its mapped anchor. Neutral framing can anticipate; future labels, descriptions, answers and outcomes cannot. Use accurate phrase onset when word alignment is unavailable, without inventing within-phrase precision. For silent footage use observed action/shot events and omit speech fields.

Introduce distinct units one by one at their own anchors. Reveal a title, then its supported detail or connector when that meaning arrives; an atomic qualified claim may arrive together. Previously introduced context may stay in stable positions when it helps understanding and still fits the reading/space budget. Remove or compact stale context before it becomes a wall of boxes. Show a complete comparison or recap only after its relevant content has been introduced, or when an explicit user overview instruction calls for it; record that scope. Do not expose future bullets and merely light them up later.

Use one primary reveal/focal action at a time. A short supporting keyword or relevant symbol can accompany it in a smaller safe region, with quieter motion. A mechanical stagger of every row by the same number of frames is not speech synchronization. If multiple meanings arrive too quickly for readable units, simplify explanatory copy or select fewer useful cues while retaining the source and full captions. Do not speed up the reveal train, delete narration, or turn every spoken word into a bouncing graphic.

Budget reading **after** the unit settles, at its final type size and actual viewing scale; entrance time is not readable hold time. Inspect whether a viewer can read while listening. Retain a relevant settled unit longer, or reduce its copy/visual complexity if the available interval is too short. A motivated reading hold is valid; do not fill it with pointless pulsing to claim continuous motion. The coverage plan must connect the hold to the next semantic development.

### Example timeline, not reusable source timestamps

At 30 fps, a source introduces “Measure demand” at 0s, “Compare capacity” at 2s and “Adjust the schedule” at 4s. A possible graphic plan is:

| Unit | Entrance and first visibility | Readable state | Handoff |
| --- | --- | --- | --- |
| Measure demand | Entry frames 0–9; opacity 0 at 0, positive from 1 | Settled from 9; hold through 51 | For one shared slot, fade out 52–59, reaching 0 at 59 |
| Compare capacity | Entry 60–69; positive from 61 | Settled from 69; hold through 111 | Fade out 112–119, reaching 0 at 119 |
| Adjust the schedule | Entry 120–129; positive from 121 | Hold only as long as relevant and readable | Budget exit within the actual remaining source interval |

In a spatially clear progressive diagram, the earlier labels may instead remain and a connector may join them when supported by speech. Frame 0 must not expose all three labels. The example does not prescribe 2-second units or omit source captions; derive intervals from each real source.

## Keep animation reproducible

Use the selected local engine's single authoritative composition timeline for footage, graphics, captions, and audio. Derive visible animation state from the requested frame and fixed inputs so frames render consistently when visited out of order. Avoid wall-clock timers, CSS animation timelines, render-order counters, and unseeded randomness. When using Remotion, its frame-driven animation guidance uses [`useCurrentFrame()`](https://www.remotion.dev/docs/animating-properties). The following Remotion API details apply only to that engine; preserve the timing invariants in an alternative engine.

When using Remotion, determine its installed version before choosing APIs. Use compatible timed components such as `Sequence` to position events, consulting the selected version's documentation. Keep placement and visibility intervals explicit. See the official [timing component reference](https://www.remotion.dev/docs/sequence).

Distinguish composition frames from component-local frames. Inside a timed parent, [`useCurrentFrame()`](https://www.remotion.dev/docs/use-current-frame) is relative to that parent's start; nested timing can shift it further. Convert an absolute transcript cue once, then animate in the appropriate local frame space. Do not subtract a start offset twice.

## Define a motion phrase

For each event specify the reason, entrance, development states, readable hold, exit and destination. Use composition FPS for durations. Time changes to reviewed speech or observed action/shot events, not an arbitrary cycle. Never retime narration to accommodate motion. In Reference direction derive the motion vocabulary from observed examples and explain adaptations needed for the current content and continuous graphic development; record an explicit user stillness instruction separately.

Use acceleration and deceleration to make movement legible. Reserve overshoot or elastic motion for a suitable tone; a scientific value or sober interview does not automatically benefit from bounce. Stagger items to reveal order, causality, or hierarchy. Keep already introduced information stable while new information arrives.

### Smooth ramps and continuous handoffs

For each changing property record start/end frames, from/to values, easing, transform origin and clamp behavior. A neutral starting treatment is a small translation (about 1–2.5% of the shorter output dimension) with opacity over 0.24–0.40s, and a quieter exit over 0.16–0.28s. These are tunable starting values, not universal durations: use actual FPS, semantic timing, safe travel and readable hold. Keep text at a readable final scale; routine large zooms and elastic bounce are not a smoothness fix.

An engine-independent non-overshooting ramp is `u = clamp((frame - a) / (b - a), 0, 1)` followed by `ease(u) = u*u*u*(u*(u*6 - 15) + 10)`. Use the eased value between the declared property endpoints. For an N-frame ramp, choose `N >= 2` and inclusive endpoints `a` and `b = a + N - 1`; derive N from the composition FPS. This reaches both endpoints with zero endpoint velocity, avoiding a reset or removal before the intended value is reached. Opacity and mask progress stay clamped to [0,1]. A different easing is valid when its observed behavior satisfies the same fit, continuity and readability checks.

Keep persistent headings, frames and introduced labels mounted with stable identities, coordinates and transforms across a state change; animate only changed parts. Do not restart their entrance because a new row is added. Measure the next unit and its plate before showing them. Animate content and backing as one coordinated group; if a container must resize, keep all visible glyphs padded throughout and hold already readable text still. Preplanned slots may avoid reflow, but must also satisfy [content- and space-sized panels](layouts-effects.md#allocate-space-before-sizing-panels).

At a same-slot replacement, fade the outgoing text completely out before the incoming prose becomes visible. A shared container/background can persist or crossfade; two readable bodies of text cannot be overprinted. Budget the outgoing exit before the next semantic anchor, or use a later safe onset without losing reading time. In distinct safe regions, brief overlap of already introduced context is allowed after checking the combined footprint and attention load. Never reveal the next meaning early to conceal a scheduling error. Caption replacement follows its separate no-overlap contract.

Verify position, scale, opacity, crop/mask and layer order on both sides of every handoff. The outgoing final visible state must connect to its intended endpoint; the incoming state must connect to its declared start, without a one-frame jump, flash, hard pop or unexpected blank. Keep the continuous source/audio clock untouched. If the slot cannot accommodate entry, reading and exit, simplify content or change the permitted graphic layout; do not shorten narration or truncate an animation above zero opacity. A source cut needs its own authority and does not excuse a graphic glitch.

For controlled ramps, [`interpolate()`](https://www.remotion.dev/docs/interpolate) maps frame ranges to values; clamp extrapolation when an attribute must stay within its intended bounds. For physical settling, [`spring()`](https://www.remotion.dev/docs/spring) uses frame and composition FPS; tune damping and overshoot deliberately. Avoid relying on default spring behavior for opacity, clipping, or other bounded properties.

## Typography, diagrams, and camera movement

Animate explanatory typography as readable words or meaningful phrases. Preserve language shaping and punctuation; do not split grapheme clusters to create letter effects. Settle important text before expecting the viewer to read it. Keep a stable location for recurring labels. Spoken subtitles follow the stricter [stable phrase caption contract](transcription-sync.md#stable-phrase-captions-and-word-highlighting): a complete stationary phrase, fixed box/word geometry and color-only active-word emphasis. Decorative typography techniques do not authorize sliding-window subtitles, word bounce, font-weight changes or recentering on each spoken word. Center headings using [measured visible bounds](layouts-effects.md#center-headings-from-measured-bounds).

Build SVG-style diagrams from verified relationships and values. Animate reveals, connectors, highlights, and labels from the same frame clock. Preserve units, denominators, axis ranges, sign, dates, source notes, and uncertainty. Do not use decorative growth that suggests an unobserved trend, change a chart baseline during a comparison, or scale symbols in a way that misstates magnitude. Label illustrative diagrams as conceptual when they are not measurements.

Use motion within diagrams/supporting graphics to guide attention. Under fitted-source presets preserve the original picture; apply a source camera move/crop only with corresponding user authority and a checked exception in the plan. Adaptive follows the same authority rule. Establish graphic context and keep text readable. Avoid constant drift, gratuitous rotations, rapid flashes and motion behind dense text.

## Speech-led craft

Set one compact motion vocabulary for this video from its inspected topic, tone, actions and explanation needs: a principal easing family, entrance/exit rhythm, development behavior, transition vocabulary, intensity and typography hierarchy. Keep one primary focal element; supporting motion should be quieter. Let the main text settle for reading while useful supporting graphics continue to develop, or record a justified short reading hold in the coverage plan. Typical short entrances around 0.3–0.5 seconds and shorter exits are starting points, not universal timing rules; tune them to speech and reading time.

For calm explanations reveal a line or phrase together; emphasize selected words when verified timing supports it. Character reveals are reserved for short non-caption graphic strings and must preserve shaping/graphemes. Subtitles show the complete phrase together; use verified active-word color without moving or resizing anything. Avoid a spring bounce on every word. Use masks/wipes only within graphics, not to crop the speaker. Stagger a list to express order or dependency, not arbitrary visual activity.

Reveal diagram entities, connectors and outcomes when their meanings are spoken. For explanatory graphic reveals, an empty container or non-revealing structural lead can precede speech intentionally, but do not expose a decisive number, negation, answer or conclusion prematurely. This does not prohibit showing the complete verified caption phrase at its reviewed onset; within that stationary phrase only active-word emphasis follows each word's onset. Count-ups must represent real values; progress/day badges must come from actual source meaning. Draw-on illustrations should reach a readable completed state. Waveform bars representing sound must use the actual audio, not invented activity.

## Preview the whole event

Include **full-duration normal-speed motion review for every output** as a named release check in the plan before rendering. Inspect all active graphic lifetimes, interior states, reading holds and transitions against the coverage record. A representative clip, attractive first/last frame, source movement, successful encode or full technical decode cannot satisfy this whole-output viewing check. Missing playback evidence leaves the candidate needs-review, not final.

Inspect the first, peak, settled, and final frames plus real-time playback. Check that entrances, development and exits fit inside the allocated interval, text does not overshoot safe areas, and transition overlap leaves narration timing unchanged. Review full-output motion coverage for long frozen cards, unexplained inactivity and repetitive decorative motion. Scrub to arbitrary frames and render a representative preview to expose state-dependent animation. If a visual needs more reading time than the speech allows, simplify it or retain its readable labels while other useful parts progress without moving the underlying dialogue.

Check each semantic unit against its actual speech/action anchor, including the frame before first visibility. Review every intra-card reveal and scene handoff at normal speed and step through adjacent frames around entry, settling and exit; endpoint stills cannot prove smoothness. Reject a full future card with moving highlights, simultaneous unrelated bullet reveals, unreadably fast chunks, easing resets, growing plates that expose text early, and a safe final position reached by an unsafe travel path. Verify the entire animated footprint using [Layouts](layouts-effects.md), including the combined old/new states.

For subtitles, inspect consecutive frames around each word highlight and phrase replacement. Text and plate coordinates must remain constant inside a cue, with no bold-induced width shift, line rewrap, horizontal jitter, cross-sentence window or old/new replacement-phrase overlap within one speaker lane. Genuine concurrent speakers may have separate identified stationary lanes with actual overlapping timing under the transcription contract. Confirm normal-speed reading and highlight sync by listening; still midpoints alone cannot prove temporal stability. Treat any observed jump or bleed as a defect to repair before release.
