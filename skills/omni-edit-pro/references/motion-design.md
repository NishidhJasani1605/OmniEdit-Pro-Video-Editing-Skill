# Motion design

Read when implementing animated text, diagrams, callouts, or camera moves. Use the creative brief from [visual-planning.md](visual-planning.md), frame events from [transcription-sync.md](transcription-sync.md), and geometry from [Editing styles](editing-styles.md) and [Layouts and effects](layouts-effects.md). Create implementation code only in the user's editing workspace.

## Develop the graphics throughout the edit

Across Split, Cutout, Overlay and Adaptive, plan continuous purposeful visual development from opening through ending. Build explanations progressively, animate a relevant mechanism or relationship, advance an active highlight, or transition between source-grounded visual states as the meaning develops. A long frozen card with only an entrance fade and exit fade does not meet this default. Ordinary source playback or an unchanged source-native frame alone does not satisfy the graphic-development plan.

Keep readable labels settled while connectors, examples, focus states or other useful graphic parts progress. Serious, quiet or visually dense scenes can use restrained, low-amplitude development. A short reading hold must have a source interval, a reason and a planned next state; it is not a standing excuse for long static passages. If the user explicitly requests stillness or a static treatment, record its scope and honor that override.

Maintain a per-source motion-coverage and transition plan: source/output interval, semantic purpose, active graphic development, readable settled elements, next state, transition purpose and any justified short hold or explicit stillness override. Cover the whole output rather than just a lively introduction. Suitable transitions connect topics, steps or visual focus without requiring a layout swap or a source cut. Avoid nonstop decorative pulses, random template changes, arbitrary loops and motion that competes with reading. This default grants no permission to cut, zoom, crop or retime the source.

## Keep animation reproducible

Use the selected local engine's single authoritative composition timeline for footage, graphics, captions, and audio. Derive visible animation state from the requested frame and fixed inputs so frames render consistently when visited out of order. Avoid wall-clock timers, CSS animation timelines, render-order counters, and unseeded randomness. When using Remotion, its frame-driven animation guidance uses [`useCurrentFrame()`](https://www.remotion.dev/docs/animating-properties). The following Remotion API details apply only to that engine; preserve the timing invariants in an alternative engine.

When using Remotion, determine its installed version before choosing APIs. Use compatible timed components such as `Sequence` to position events, consulting the selected version's documentation. Keep placement and visibility intervals explicit. See the official [timing component reference](https://www.remotion.dev/docs/sequence).

Distinguish composition frames from component-local frames. Inside a timed parent, [`useCurrentFrame()`](https://www.remotion.dev/docs/use-current-frame) is relative to that parent's start; nested timing can shift it further. Convert an absolute transcript cue once, then animate in the appropriate local frame space. Do not subtract a start offset twice.

## Define a motion phrase

For each event specify the reason, entrance, development states, readable hold, exit and destination. Use composition FPS for durations. Time changes to reviewed speech or observed action/shot events, not an arbitrary cycle. Never retime narration to accommodate motion. In Reference direction derive the motion vocabulary from observed examples and explain adaptations needed for the current content and continuous graphic development; record an explicit user stillness instruction separately.

Use acceleration and deceleration to make movement legible. Reserve overshoot or elastic motion for a suitable tone; a scientific value or sober interview does not automatically benefit from bounce. Stagger items to reveal order, causality, or hierarchy. Keep already introduced information stable while new information arrives.

For controlled ramps, [`interpolate()`](https://www.remotion.dev/docs/interpolate) maps frame ranges to values; clamp extrapolation when an attribute must stay within its intended bounds. For physical settling, [`spring()`](https://www.remotion.dev/docs/spring) uses frame and composition FPS; tune damping and overshoot deliberately. Avoid relying on default spring behavior for opacity, clipping, or other bounded properties.

## Typography, diagrams, and camera movement

Animate typography as readable words or meaningful phrases. Preserve language shaping and punctuation; do not split grapheme clusters to create letter effects. Settle important text before expecting the viewer to read it. Keep a stable location for recurring labels.

Build SVG-style diagrams from verified relationships and values. Animate reveals, connectors, highlights, and labels from the same frame clock. Preserve units, denominators, axis ranges, sign, dates, source notes, and uncertainty. Do not use decorative growth that suggests an unobserved trend, change a chart baseline during a comparison, or scale symbols in a way that misstates magnitude. Label illustrative diagrams as conceptual when they are not measurements.

Use motion within diagrams/supporting graphics to guide attention. Under fitted-source presets preserve the original picture; apply a source camera move/crop only with corresponding user authority and a checked exception in the plan. Adaptive follows the same authority rule. Establish graphic context and keep text readable. Avoid constant drift, gratuitous rotations, rapid flashes and motion behind dense text.

## Speech-led craft

Set one compact motion vocabulary for this video from its inspected topic, tone, actions and explanation needs: a principal easing family, entrance/exit rhythm, development behavior, transition vocabulary, intensity and typography hierarchy. Keep one primary focal element; supporting motion should be quieter. Let the main text settle for reading while useful supporting graphics continue to develop, or record a justified short reading hold in the coverage plan. Typical short entrances around 0.3–0.5 seconds and shorter exits are starting points, not universal timing rules; tune them to speech and reading time.

For calm explanations reveal a line or phrase together; emphasize selected words when verified timing supports it. Character reveals are reserved for short strings and must preserve shaping/graphemes. Avoid a spring bounce on every word. Use masks/wipes only within graphics, not to crop the speaker. Stagger a list to express order or dependency, not arbitrary visual activity.

Reveal diagram entities, connectors and outcomes when their meanings are spoken. An empty container or non-revealing structural lead can precede speech intentionally, but do not expose a decisive number, negation, answer or conclusion prematurely. Count-ups must represent real values; progress/day badges must come from actual source meaning. Draw-on illustrations should reach a readable completed state. Waveform bars representing sound must use the actual audio, not invented activity.

## Preview the whole event

Include **full-duration normal-speed motion review for every output** as a named release check in the plan before rendering. Inspect all active graphic lifetimes, interior states, reading holds and transitions against the coverage record. A representative clip, attractive first/last frame, source movement, successful encode or full technical decode cannot satisfy this whole-output viewing check. Missing playback evidence leaves the candidate needs-review, not final.

Inspect the first, peak, settled, and final frames plus real-time playback. Check that entrances, development and exits fit inside the allocated interval, text does not overshoot safe areas, and transition overlap leaves narration timing unchanged. Review full-output motion coverage for long frozen cards, unexplained inactivity and repetitive decorative motion. Scrub to arbitrary frames and render a representative preview to expose state-dependent animation. If a visual needs more reading time than the speech allows, simplify it or retain its readable labels while other useful parts progress without moving the underlying dialogue.
