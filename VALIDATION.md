# Validation evidence — OmniEdit Pro 2

Validated on 24 October 2026 in the local Windows checkout. This evidence covers instruction-package structure and the behaviors specified by its instructions. No source video was edited or rendered during this skill-authoring task.

## Package checks

| Check | Observed result |
| --- | --- |
| YAML parsing | All nine SKILL.md frontmatters parsed with PyYAML; required names/descriptions and version 2.0.0 verified |
| Name discovery | Skills CLI 1.7.2, `npx.cmd --yes skills@1.7.2 add . --list`, discovered exactly the expected nine entries |
| License distribution | Every entry's LICENSE matched the root license byte for byte |
| Instruction-only inventory | 34 files under skills/: 9 SKILL.md, 9 LICENSE and 16 shared Markdown references; no processing scripts, templates, model weights, runtime packages or media |
| Shared dependencies | All eight wrappers linked to the sibling core; all 56 relative links within the installable instructions resolved |
| Staged manual installation | Copied the entire suite into a fresh temporary staging root; compared every package file by SHA-256 and resolved each wrapper's shared-core path |
| Isolated CLI installation | Skills CLI 1.7.2 installed all nine explicitly named entries with `--agent codex --copy --yes` at project scope in a new temporary directory; all 34 installed files matched the source byte for byte and all 56 installed relative links resolved |
| Source checkout identity | All nine research repositories' actual origin URLs and HEAD revisions matched ATTRIBUTIONS.md |
| Whitespace check | `git diff --check` passed after normalizing line endings/trailing whitespace |

Both installation checks used temporary locations, not the user's live global skill installation. CLI discovery was list-only; the additional CLI installation check used an isolated project scope. These checks establish package installation and readable dependencies, not that every IDE has loaded the suite; host discovery is a separate check.

## Behavioral dry run

A separate reviewer read the actual wrappers/shared instructions and traced these cases without performing media operations:

| Scenario | Required behavior confirmed in the instructions |
| --- | --- |
| Three videos; main entry; both choices missing | Ask orientation, wait; ask style, wait; then dispatch selected per-video jobs |
| Cutout supplied; orientation missing | Ask only orientation; preserve the existing Cutout choice |
| Vertical Split preset | Retain both choices and proceed without either selection question |
| All; two same-basename sources; limited workers/no nesting | Keep unique source IDs, twelve requested pairs, isolated paths and queued genuine specialist assignments |
| Both Cutout variants fail for one source | Repair/report those variants; deliver other passing variants; batch remains partial |
| Explanation-only request | Explain without selection questions, media processing or production teams |
| Wide source to Vertical Overlay; playback unavailable | Fit the entire source with padding; candidate stays needs-review in Working Files |
| Native subagents unavailable | Explain actual capability gap and ask about solo fallback; never fabricate teams |
| Preset contradicted by a clear user override | Honor the explicit new orientation/style without redundant confirmation |

The dry run found and prompted fixes to an unconditional Remotion timeline requirement, an outdated reference-file count, incomplete state vocabulary, and missing-source/provisional-ID wording. These findings were repaired in the current instructions. Other reported considerations—worker capacity and portrait prominence—remain explicit capability/preview decisions rather than fixed unsupported promises.

This was an instruction-routing review, not an execution test of a real renderer, matting engine or host agent API.

## Publication review

The publication audit on 24 October 2026 rechecked the current suite against the user's requirements and expanded the README with installation methods, all preset names, the three style contracts, sequential questions, team roles, quality rules, free/local processing, final folders, sources and limitations. All 110 relative file links across the repository and all 14 README contents anchors resolved; skill metadata, license distribution, Markdown fences and whitespace checks passed.

It also closed an implicit-selection gap: a host/model automatically matching a preset no longer supplies missing user choices. The shared selection rules and all seven fixed-mode wrappers now reserve preset defaults for explicit user selection. A manual instruction trace confirmed that a generic editing request automatically routed to Vertical Split still asks orientation and style, while a prompt already specifying vertical asks only style. Explicit preset invocation still skips resolved questions, and explicit user overrides still win.

These are instruction-level checks. They do not turn the earlier dry run into an executed video-production test. Repository publication is tracked by Git history and the remote branch, separately from video-quality evidence.

## Requirement audit

| Requirement | Authoritative implemented evidence |
| --- | --- |
| Use all nine repositories / ten source entries | Downloaded Git checkouts and pinned source/contribution table in [ATTRIBUTIONS.md](ATTRIBUTIONS.md) |
| Adapt both requested delegation skills | [batch-teams.md](skills/omni-edit-pro/references/batch-teams.md): native assignments, isolated ownership, dependency order, review and repair; no software-development scripts required |
| Markdown instruction package only | File inventory and [core SKILL.md](skills/omni-edit-pro/SKILL.md); generated processing code belongs to the editing workspace |
| Main entry, six direct presets, All, original compatibility | Nine parsed/discovered folders; mode table in [selection.md](skills/omni-edit-pro/references/selection.md) |
| Compulsory easy questions in sequence | [selection.md](skills/omni-edit-pro/references/selection.md), core entry and behavioral cases |
| Separate team for each input video | [batch-teams.md](skills/omni-edit-pro/references/batch-teams.md): actual host handles, specialists, capacity queue, same-name isolation and truthful unsupported-host path |
| Both output shapes and three distinct styles | [editing-styles.md](skills/omni-edit-pro/references/editing-styles.md) and preset entries |
| Protect source framing/person quality | Styles: full-source contain fitting for Split/Overlay; [local-cutout.md](skills/omni-edit-pro/references/local-cutout.md): subject-detail/edge/motion acceptance |
| Preserve narration and synchronize useful animations | [transcription-sync.md](skills/omni-edit-pro/references/transcription-sync.md), [visual-planning.md](skills/omni-edit-pro/references/visual-planning.md), [motion-design.md](skills/omni-edit-pro/references/motion-design.md), [audio-rendering.md](skills/omni-edit-pro/references/audio-rendering.md) |
| Free/local Cutout and agent-created coding option | [local-cutout.md](skills/omni-edit-pro/references/local-cutout.md) and [environment.md](skills/omni-edit-pro/references/environment.md): local choices, workspace-only code, no paid/cloud fallback |
| Preserve excellent Split/Overlay work if Cutout fails | Local-cutout, batch All accounting and [delivery.md](skills/omni-edit-pro/references/delivery.md) explicitly retain incomplete Cutout rows |
| Separate Final Output Videos folder | Delivery: exact folder, unique IDs, version names, checked-only promotion and preservation of earlier finals |
| Detailed plan and source explanations | [IMPLEMENTATION.md](IMPLEMENTATION.md), [README.md](README.md), attribution and source notices |
| Installation completeness | [INSTALL.md](INSTALL.md), staged copy comparison and wrapper dependency checks |

The artifact requested here is a skill instruction suite. The evidence above proves its written requirements and package structure; it does not certify the future output of every agent using it.

## Not run

- A real-video edit, cutout inference or final video export.
- Full audiovisual quality review of rendered media.
- Live installation/reload/discovery in every listed host.
- Updating a live global skill installation.

Those are not prerequisites for authoring this instruction-only package. They must be reported accurately when a later installation or editing task is requested. The runtime workflow requires actual audiovisual evidence before treating a rendered candidate as a checked final.
