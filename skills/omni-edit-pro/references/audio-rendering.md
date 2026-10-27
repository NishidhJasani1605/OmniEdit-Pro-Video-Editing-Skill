# Audio, finishing, previews, and rendering

## Own each sound once

In continuity mode preserve full original narration at its mapped time and normal speed. For authorized edits map source audio through the same segment/speed/transition decisions as picture and captions. Choose one audio owner: base video or separately mapped track with base audio muted. Multiple copies cause echo/phasing. Mute B-roll audio unless intentionally included. No unrequested silence removal, speech regeneration or time stretching. For non-speech footage protect intended ambience, music and system/action sounds. If no audio stream exists, record audio/listening as not applicable; do not invent narration or sound to satisfy a checklist.

Keep full-quality source audio separate from recognition audio. Listen before denoising, gating, compressing or normalizing: a treatment that removes consonants is worse than mild steady noise. Use minimal corrective processing, and compare processed and original passages at matched listening levels. Measure integrated loudness and true peak against the requested delivery specification; there is no single mandatory loudness target for every platform or genre. Leave sufficient headroom and document any chosen target. Optional music should support the voice, with smooth level changes rather than pumping or masking.

## Prepare one deterministic render

Use the selected free/local compositor and versioned dependencies; when using Remotion, inspect its installed APIs. Derive all layers, audio offsets, dimensions, frame rate and duration from the same validated timeline. Resolve local assets, fonts and asynchronous loads before capture. Rendering a frame should not depend on wall-clock time, network races or unseeded randomness. The normal edit request includes final export; do not stop at an interactive preview unless the user requested preview-only work.

Choose codec, container, pixel format, audio codec/rate/channel layout, dimensions and color output for the requested destination. H.264/AAC MP4 is a common compatibility choice, not a universal master format. Use a suitable alpha-capable format only when transparency is required. Handle HDR and log material with a deliberate, tested color transform; do not fix washed-out colors by blindly increasing saturation or mislabeling color metadata.

For an already installed CLI, representative commands are:

```text
remotion compositions "src/index.ts"
remotion render "src/index.ts" OmniEdit "out/preview.mp4" --frames=0-149
remotion render "src/index.ts" OmniEdit "out/final.mp4"
```

These are command examples, not bundled files: replace paths, composition ID and frame range with the actual project. Render previews and full candidates under `Working Files/<video-id>/` first; the example `out/final.mp4` is a candidate, not an accepted final. Invoke the local binary or approved project runner and inspect its version/help before options. A CLI frame range can have inclusive endpoints, whereas the internal timeline uses exclusive ends; convert explicitly. A render may download a browser if missing, so complete dependency checks first.

## Preview and recover

Render passages that exercise the actual plan: early speech/action, dense text, a complex graphic, layout/shot change and ending, with audio when present. Reference previews include the defining treatment and a difficult transfer case; compare against timecoded sample examples. Include full-size stills for type/framing checks. Use the final media/timeline. Review normal-speed motion and, where audio exists, listen and check sync. Static screenshots cannot certify motion or sound.

Include the middle of longer explanatory graphics to expose frozen-card treatment, not only entrances/exits. Review source-specific meaningful evolution and graphic transitions while narration stays continuous. For portrait presenter scenes inspect lower source/silhouette and upper animation in each requested composition; for Cutout include moving arms/hair over the actual full-canvas background and safe transparent gaps, checking contrast. Still-frame and end-to-end decode checks cannot replace that motion/occlusion review.

If rendering fails, isolate the smallest failing frame range. Check missing assets/fonts, decode errors, failed asynchronous loading, unsupported browser APIs and memory. Lower concurrency or use a compatible intermediate where justified; do not alter frame rate or truncate narration to conceal failure. Keep diagnostic logs outside the skill install. Recheck repaired intervals and their boundaries.

After final rendering, probe the output and decode it end to end for errors. Compare its frames and audio duration with the planned duration, allowing only documented frame/sample or encoder padding. Never use a shortest-stream option blindly when muxing preserved narration; it can discard the end. Verify the muxed output, not just the intermediate composition. Stream copying may preserve audio encoding when compatible, but is not a guarantee of identical playback timing.

Follow [Delivery](delivery.md) to promote only checked exports into `Final Output Videos/<video-id>/`. Link requested caption/project files, credits and QA notes from the working area. Mention output specifications, processing, known limitations and playback review coverage. Keep source footage and editable dependencies available for revision.

Sources: [Remotion CLI](https://www.remotion.dev/docs/cli), [renderMedia](https://www.remotion.dev/docs/renderer/render-media), [FFmpeg filters](https://ffmpeg.org/ffmpeg-filters.html).
