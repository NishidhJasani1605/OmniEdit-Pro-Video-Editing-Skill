# Motion design

Read when implementing animated text, diagrams, callouts, or camera moves. Use the creative brief from [visual-planning.md](visual-planning.md), frame events from [transcription-sync.md](transcription-sync.md), and composition constraints from [layouts-effects.md](layouts-effects.md). Create implementation code only in the user's editing workspace.

## Keep animation reproducible

Use one Remotion composition timeline for footage, graphics, captions, and audio. Derive visible animation state from the requested frame and fixed inputs so frames render consistently when visited out of order. Avoid wall-clock timers, CSS animation timelines, render-order counters, and unseeded randomness. Remotion explicitly recommends frame-driven animation through [`useCurrentFrame()`](https://www.remotion.dev/docs/animating-properties).

Determine the installed Remotion version before choosing APIs. Use compatible timed components to position each event; direct `Sequence` remains supported, although current documentation favors timing props on appropriate components. Keep placement and visibility intervals explicit. See the official [timing component reference](https://www.remotion.dev/docs/sequence).

Distinguish composition frames from component-local frames. Inside a timed parent, [`useCurrentFrame()`](https://www.remotion.dev/docs/use-current-frame) is relative to that parent's start; nested timing can shift it further. Convert an absolute transcript cue once, then animate in the appropriate local frame space. Do not subtract a start offset twice.

## Define a motion phrase

For each event, specify the reason for movement, entrance, readable hold, exit, and destination. Use the frame rate from the composition when converting planned durations. Time changes to validated spoken meaning, not an arbitrary animation cycle. Never retime narration to accommodate motion.

Use acceleration and deceleration to make movement legible. Reserve overshoot or elastic motion for a suitable tone; a scientific value or sober interview does not automatically benefit from bounce. Stagger items to reveal order, causality, or hierarchy. Keep already introduced information stable while new information arrives.

For controlled ramps, [`interpolate()`](https://www.remotion.dev/docs/interpolate) maps frame ranges to values; clamp extrapolation when an attribute must stay within its intended bounds. For physical settling, [`spring()`](https://www.remotion.dev/docs/spring) uses frame and composition FPS; tune damping and overshoot deliberately. Avoid relying on default spring behavior for opacity, clipping, or other bounded properties.

## Typography, diagrams, and camera movement

Animate typography as readable words or meaningful phrases. Preserve language shaping and punctuation; do not split grapheme clusters to create letter effects. Settle important text before expecting the viewer to read it. Keep a stable location for recurring labels.

Build SVG-style diagrams from verified relationships and values. Animate reveals, connectors, highlights, and labels from the same frame clock. Preserve units, denominators, axis ranges, sign, dates, source notes, and uncertainty. Do not use decorative growth that suggests an unobserved trend, change a chart baseline during a comparison, or scale symbols in a way that misstates magnitude. Label illustrative diagrams as conceptual when they are not measurements.

Use pans and zooms to guide attention toward a relevant detail. Establish the subject first, retain enough context to understand the move, and check the source resolution at maximum enlargement. Avoid constant drift, gratuitous rotations, rapid flashes, and motion behind dense text.

## Preview the whole event

Inspect the first, peak, settled, and final frames plus real-time playback. Check that entrances and exits fit inside the allocated interval, text does not overshoot safe areas, and transition overlap leaves narration timing unchanged. Scrub to arbitrary frames and render a representative preview to expose state-dependent animation. If a visual needs more reading time than the speech allows, simplify it or extend its visual hold without moving the underlying dialogue.
