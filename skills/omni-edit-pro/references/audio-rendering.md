# Audio, finishing, previews, and rendering

## Own each sound once

In continuity mode, preserve the full selected original narration at its mapped start time and normal speed. Choose one audio owner: either the base video supplies narration, or a separately mapped narration track does and the base video's audio is muted. Multiple audible copies cause echo or phasing. Mute B-roll audio unless intentionally included. Do not add automatic silence removal, speech regeneration, or time stretching.

Keep full-quality source audio separate from recognition audio. Listen before denoising, gating, compressing or normalizing: a treatment that removes consonants is worse than mild steady noise. Use minimal corrective processing, and compare processed and original passages at matched listening levels. Measure integrated loudness and true peak against the requested delivery specification; there is no single mandatory loudness target for every platform or genre. Leave sufficient headroom and document any chosen target. Optional music should support the voice, with smooth level changes rather than pumping or masking.

## Prepare one deterministic render

Use the existing project's installed Remotion APIs and versioned dependencies. Derive all layers, audio offsets, composition dimensions, frame rate and duration from the same validated timeline. Resolve local asset paths, fonts and asynchronous loads before capture. Rendering a frame should not depend on wall-clock time, network races or unseeded randomness.

Choose codec, container, pixel format, audio codec/rate/channel layout, dimensions and color output for the requested destination. H.264/AAC MP4 is a common compatibility choice, not a universal master format. Use a suitable alpha-capable format only when transparency is required. Handle HDR and log material with a deliberate, tested color transform; do not fix washed-out colors by blindly increasing saturation or mislabeling color metadata.

For an already installed CLI, representative commands are:

```text
remotion compositions "src/index.ts"
remotion render "src/index.ts" OmniEdit "out/preview.mp4" --frames=0-149
remotion render "src/index.ts" OmniEdit "out/final.mp4"
```

These are templates: replace paths, composition ID and frame range using the actual project. Invoke the local binary or approved project runner, and inspect its version/help before using options. A CLI frame range can have inclusive endpoints, whereas the internal timeline uses exclusive ends; convert explicitly. A render may download a browser if missing, so complete dependency checks first.

## Preview and recover

Render representative clips with audio: an early speech cue, dense captions, a complex graphic, a layout change, and the ending. Include full-size stills for typography/crop inspection; low-resolution playback alone can hide fine text problems. Use the same media, timing and composition as final. Review motion at normal speed, listen and compare lips to speech; static screenshots cannot verify either.

If rendering fails, isolate the smallest failing frame range. Check missing assets/fonts, decode errors, failed asynchronous loading, unsupported browser APIs and memory. Lower concurrency or use a compatible intermediate where justified; do not alter frame rate or truncate narration to conceal failure. Keep diagnostic logs outside the skill install. Recheck repaired intervals and their boundaries.

After final rendering, probe the output and decode it end to end for errors. Compare its frames and audio duration with the planned duration, allowing only documented frame/sample or encoder padding. Never use a shortest-stream option blindly when muxing preserved narration; it can discard the end. Verify the muxed output, not just the intermediate composition. Stream copying may preserve audio encoding when compatible, but is not a guarantee of identical playback timing.

Deliver the final media and requested caption/project files with credits and concise QA notes. Mention output specifications, any processing applied, known limitations, and whether full playback review occurred. Keep source footage and editable dependencies available for revision.

Sources: [Remotion CLI](https://www.remotion.dev/docs/cli), [renderMedia](https://www.remotion.dev/docs/renderer/render-media), [FFmpeg filters](https://ffmpeg.org/ffmpeg-filters.html).
