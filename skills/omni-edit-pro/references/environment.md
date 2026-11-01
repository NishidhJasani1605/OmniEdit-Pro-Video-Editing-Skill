# Environment and dependency decisions

Installing this suite copies instructions and license notices only. Rendering requires tools provided by the host or installed separately in the editing workspace. Never treat skill discovery as evidence that an editor, model, GPU, playback capability or native agent-team interface is available. Begin with [Selection](selection.md): resolve file roles and creative mode first. Narrow source/reference inspection, read-only tool scouting and scoped analysis are allowed before Auto/Reference choices; explicit Manual keeps its missing-choice gate. Record resolved output/treatment decisions before creating variant/render jobs. No mode mandates a new package or model installation.

## Detect before installing

Inspect the OS, shell, permitted workspace, free storage, source access, existing project manifest/lockfile and available hardware. Locate executables with `Get-Command` in PowerShell or `command -v` in a POSIX shell; query the versions of tools actually found. Read local package manifests rather than assuming global packages. Avoid using `npx` as a presence check because it can download packages.

| Capability | Preferred tools | Tool usage directive |
| --- | --- | --- |
| Media metadata & FFmpeg execution | FFprobe & FFmpeg | Handles Windows path escaping (`D\:/`), streamcopy audio (`-c:a copy`), split/cutout/overlay filtergraphs. |
| Text measurement & geometry | PIL/Pillow (`ImageFont`) | Measures exact visible bounding boxes, ascender/descenders, wrapping, padding, visible centering, and collisions. |
| Speaker background cutout | PeterL1n RVM MobileNetV3 | Fast local AI matting with lightweight 15MB weights; outputs alpha video or RGBA PNG sequence. |
| Main composition engine | Native FFmpeg + Python PIL | Free local compositor with zero proprietary licensing risk or Chromium crash traps. |
| Speech recognition / alignment | Whisper / WhisperX | Transcribes dialogue, provides word-level timestamps; supported by contextual domain agent. |

Reference analysis and Auto direction are observation/decision procedures, not additional model requirements. Use available tools to inspect actual media and mark measured, inferred and unknown evidence. A missing/corrupt/inaccessible reference remains unavailable; do not upload it, claim a match or silently select Auto as recovery. Use an explicitly authorized fallback and report it, or identify the missing access/direction decision. A fixed frame-sampling rate cannot certify short events, motion or sound.

Ask before adding heavyweight runtimes, browser binaries, GPU stacks, models or processing packages unless already authorized. State the actual missing requirement, why it is needed, resource demands if known, destination and usable alternatives. Existing explicit authorization is sufficient; do not ask repeatedly. A basic package command may trigger large transitive downloads, so inspect requirements first. The nine upstream research repositories are not runtime dependencies; do not download or install them during ordinary edits.

Verify the actual renderer can resolve the chosen font and its required glyphs in a small preview. A system font family name alone does not prove resolution: headless/fontconfig setup may be unavailable. Use a verified font file or approved project-local font when needed, and recheck layout with that actual font instead of silently changing typography. This is a capability check, not a reason to install a new font stack automatically.

Prefer a project-local, version-locked Remotion setup when its terms allow this use without payment. Keep `remotion` and `@remotion/*` at compatible matching versions, and check React/Node/browser support. Reuse installed tools before upgrades. This suite's default is free/local execution: no paid APIs, credit-based services, cloud transcription/rendering, paid stock, paid model gates or silent uploads. A future user request for a paid service is a separate scope change; do not propose one as an automatic recovery path.

## One pipeline and bounded recovery

One selected local engine owns composition and time; FFmpeg handles preparation and finishing derived from that plan. If Remotion is unavailable or its terms require payment for this use, assess a free local alternative such as an available deterministic HTML compositor or an FFmpeg composition with agent-generated graphics. Validate capability on a representative difficult passage before expanding it, including actual motion/audio and applicable reference comparison. Do not maintain competing independent timelines or silently replace required graphics, composition, framing or reference attributes with an edit that fails the brief. For silent material validate visual/action timing without fabricating narration. If no available free path satisfies the task, preserve the plan/working files and report the specific gap. A local cutout preprocessing tool does not need to become the main composition engine.

On failure, capture the relevant error, isolate it with the smallest affected source or interval, and make a targeted repair. Check paths/escaping, codecs, fonts, memory and browser support before changing creative decisions. After two failed targeted attempts at the same issue, stop repeating identical commands; report evidence and the smallest dependency, permission, or user decision needed. Continue independent work that is still useful.

Do not overwrite originals, user configuration or installed skills to solve a runtime problem. Quote paths for the actual shell and pass untrusted filenames as arguments. Store generated code, packages, caches and previews under the editing workspace's `Working Files`, and checked exports under `Final Output Videos` as specified in [Delivery](delivery.md). Constrain GPU-heavy jobs separately from native agent count; do not lower required output quality merely to run more videos simultaneously.

Runtime tools carry separate terms: [Remotion license](https://www.remotion.dev/license), [FFmpeg licensing](https://ffmpeg.org/legal.html), [WhisperX setup](https://github.com/m-bain/whisperX), and [whisper.cpp setup](https://github.com/ggml-org/whisper.cpp). Confirm the selected versions and model/asset terms when relevant; the skill's MIT license does not license those tools or media.
