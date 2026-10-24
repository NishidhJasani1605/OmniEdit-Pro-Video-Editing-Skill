# Environment and dependency decisions

Installing this suite copies instructions and license notices only. Rendering requires tools provided by the host or installed separately in the editing workspace. Never treat skill discovery as evidence that an editor, model, GPU or native agent-team interface is available. Complete [Selection](selection.md) before runtime inspection or installation for an editing request.

## Detect before installing

Inspect the OS, shell, permitted workspace, free storage, source access, existing project manifest/lockfile and available hardware. Locate executables with `Get-Command` in PowerShell or `command -v` in a POSIX shell; query the versions of tools actually found. Read local package manifests rather than assuming global packages. Avoid using `npx` as a presence check because it can download packages.

| Capability | Preferred tools | Missing-tool response |
| --- | --- | --- |
| Media metadata and preparation | FFprobe and FFmpeg | Use an available equivalent for inspection; disclose any missing metadata. Request installation before processing that needs it. |
| Main composition | Compatible local Remotion where the intended use requires no paid license; otherwise a suitable free local compositor | Inspect versions, runtime needs and applicable terms. Preserve the selected style/quality when choosing an alternative. |
| Speech recognition/alignment | Available WhisperX, whisper.cpp, or another evidenced aligner | Reuse a supplied transcript, align where possible, or use manually reviewed phrase cues. |
| Preview review | Image/video/audio inspection tools | Render artifacts if possible, identify the missing review capability and request user review of specific intervals. |
| Speaker cutout | Existing alpha, local keying, or free local matting/segmentation | Follow [Local cutouts](local-cutout.md); do not call paid background-removal APIs. |
| Optional assets | User assets, free assets with compatible reuse terms, original code-drawn graphics, available free local generators | Simplify optional graphics within the selected style if a source is unavailable. |

Ask before adding heavyweight runtimes, browser binaries, GPU stacks, models or processing packages unless already authorized. State the actual missing requirement, why it is needed, resource demands if known, destination and usable alternatives. Existing explicit authorization is sufficient; do not ask repeatedly. A basic package command may trigger large transitive downloads, so inspect requirements first. The nine upstream research repositories are not runtime dependencies; do not download or install them during ordinary edits.

Prefer a project-local, version-locked Remotion setup when its terms allow this use without payment. Keep `remotion` and `@remotion/*` at compatible matching versions, and check React/Node/browser support. Reuse installed tools before upgrades. This suite's default is free/local execution: no paid APIs, credit-based services, cloud transcription/rendering, paid stock, paid model gates or silent uploads. A future user request for a paid service is a separate scope change; do not propose one as an automatic recovery path.

## One pipeline and bounded recovery

One selected local engine owns composition and time; FFmpeg handles preparation and finishing derived from that plan. If Remotion is unavailable or its terms require payment for this use, assess a free local alternative such as an available deterministic HTML compositor or an FFmpeg composition with agent-generated graphics. Validate capability on the difficult passage before expanding it. Do not maintain competing independent timelines or silently replace smooth, speech-matched graphics with a simpler edit that fails the brief. If no available free path satisfies the task, preserve the plan/working files and report the specific gap. A local cutout preprocessing tool does not need to become the main composition engine.

On failure, capture the relevant error, isolate it with the smallest affected source or interval, and make a targeted repair. Check paths/escaping, codecs, fonts, memory and browser support before changing creative decisions. After two failed targeted attempts at the same issue, stop repeating identical commands; report evidence and the smallest dependency, permission, or user decision needed. Continue independent work that is still useful.

Do not overwrite originals, user configuration or installed skills to solve a runtime problem. Quote paths for the actual shell and pass untrusted filenames as arguments. Store generated code, packages, caches and previews under the editing workspace's `Working Files`, and checked exports under `Final Output Videos` as specified in [Delivery](delivery.md). Constrain GPU-heavy jobs separately from native agent count; do not lower required output quality merely to run more videos simultaneously.

Runtime tools carry separate terms: [Remotion license](https://www.remotion.dev/license), [FFmpeg licensing](https://ffmpeg.org/legal.html), [WhisperX setup](https://github.com/m-bain/whisperX), and [whisper.cpp setup](https://github.com/ggml-org/whisper.cpp). Confirm the selected versions and model/asset terms when relevant; the skill's MIT license does not license those tools or media.
