# Environment and dependency decisions

Installing this skill copies instructions only. Rendering requires tools provided by the host or installed separately in the editing workspace. Never treat skill discovery as evidence that an editor, model, GPU, or paid service is available.

## Detect before installing

Inspect the OS, shell, permitted workspace, free storage, source access, existing project manifest/lockfile and available hardware. Locate executables with `Get-Command` in PowerShell or `command -v` in a POSIX shell; query the versions of tools actually found. Read local package manifests rather than assuming global packages. Avoid using `npx` as a presence check because it can download packages.

| Capability | Preferred tools | Missing-tool response |
| --- | --- | --- |
| Media metadata and preparation | FFprobe and FFmpeg | Use an available equivalent for inspection; disclose any missing metadata. Request installation before processing that needs it. |
| Main composition | Existing compatible Node.js, React, Remotion packages and supported browser | Inspect project versions and renderer requirements. Prepare the plan; request the needed installation if absent. |
| Speech recognition/alignment | Available WhisperX, whisper.cpp, or another evidenced aligner | Reuse a supplied transcript, align where possible, or use manually reviewed phrase cues. |
| Preview review | Image/video/audio inspection tools | Render artifacts if possible, identify the missing review capability and request user review of specific intervals. |
| Optional assets | Authorized local libraries, licensed stock or available generators | Use a simpler original graphic or preserve the presenter if a service is unavailable. |

Ask before adding heavyweight runtimes, browser binaries, GPU stacks, models, or processing packages. State what is missing, why it is needed, approximate resource demands if known, installation destination, and a usable fallback. Existing explicit authorization is sufficient; do not ask repeatedly. A basic package command may trigger large transitive downloads, so inspect requirements first. Do not install the five upstream skills.

Prefer a project-local, version-locked Remotion setup. Keep `remotion` and `@remotion/*` packages at compatible matching versions, and check React/Node/browser support for that release. Reuse installed tools before considering upgrades. Obtain the user's authorization before sending private footage to hosted transcription, storage, or rendering services. Keep tokens in the host's secret mechanism, never in a timeline or command output.

## One pipeline and bounded recovery

Remotion owns composition and time; FFmpeg handles preparation and finishing derived from that same plan. Do not independently recreate the edit in MoviePy, an NLE, and Remotion. If Remotion cannot run and installation is declined, deliver the plan and dependency gap. For a simple operation already possible with FFmpeg, explain the reduced capability and use it as the sole fallback only when it satisfies the user's request; record that choice.

On failure, capture the relevant error, isolate it with the smallest affected source or interval, and make a targeted repair. Check paths/escaping, codecs, fonts, memory and browser support before changing creative decisions. After two failed targeted attempts at the same issue, stop repeating identical commands; report evidence and the smallest dependency, permission, or user decision needed. Continue independent work that is still useful.

Do not overwrite originals, user configuration, or an existing skill installation to solve a runtime problem. Quote paths for the actual shell and pass untrusted filenames as arguments. Store generated code, packages, caches, previews and final media in the editing workspace, not the skill directory.

Runtime tools carry separate terms: [Remotion license](https://www.remotion.dev/license), [FFmpeg licensing](https://ffmpeg.org/legal.html), [WhisperX setup](https://github.com/m-bain/whisperX), and [whisper.cpp setup](https://github.com/ggml-org/whisper.cpp). Confirm the selected versions and model/asset terms when relevant; the skill's MIT license does not license those tools or media.
