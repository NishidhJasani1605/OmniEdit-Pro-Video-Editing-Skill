# Installing OmniEdit Pro 3.1.2

Install instructions only. Installation does not start an editing job, ask creative-selection questions, spawn production teams, create a video project, or install processing tools/models. No external skill is a mandatory runtime dependency.

## Select the destination and preserve existing work

Identify the actual agent and its supported user-level skill root. See [Agent compatibility](skills/omni-edit-pro/references/agent-compatibility.md) for previously checked conventions and host limitations. Inspect both native and shared roots for existing names or symlinks. Preserve local edits; resolve conflicting replacements using the user's actual update authorization. A CLI can skip confirmation in an agent environment, so absence of a confirmation flag is not an overwrite safeguard.

Use user scope when the user wants the skill across projects. Do not change the current project's configuration merely to install a personal skill.

## Install the same-release sibling folders

Copy these complete directories from `skills/` into the selected skill root:

- `omni-edit-pro` — shared core and compatible original entry
- `omni-pro-edit` — main entry
- `omni-pro-edit-horizontal-split`
- `omni-pro-edit-horizontal-cutout`
- `omni-pro-edit-horizontal-overlay`
- `omni-pro-edit-vertical-split`
- `omni-pro-edit-vertical-cutout`
- `omni-pro-edit-vertical-overlay`
- `omni-pro-edit-all`

The complete suite contains 38 Markdown/license files: the core's SKILL.md, LICENSE and 20 reference files, plus SKILL.md and LICENSE for each of eight wrappers. References include reference analysis, automatic direction, portrait composition, full-duration motion, per-source visual planning and the new dedicated [Production Video Reviewer](skills/omni-edit-pro/references/video-reviewer.md). Each wrapper loads the sibling core. Do not copy only an entry file, nest the suite under an undiscoverable extra directory, or combine versions. For a smaller installation, install the core plus selected wrappers. The core can also be invoked on its own.

Manual copying needs no Python, Node.js, application code or upstream skill installations.

## Optional Skills CLI

From a reviewed local checkout containing all nine 3.1.2 entries, with Git and a supported Node/npm runtime:

```sh
npx skills add . --global --agent <agent-id> --skill omni-edit-pro omni-pro-edit omni-pro-edit-horizontal-split omni-pro-edit-horizontal-cutout omni-pro-edit-horizontal-overlay omni-pro-edit-vertical-split omni-pro-edit-vertical-cutout omni-pro-edit-vertical-overlay omni-pro-edit-all
```

Replace `<agent-id>` with the host's verified CLI ID. For a smaller selection:

```sh
npx skills add . --global --agent <agent-id> --skill omni-edit-pro omni-pro-edit-vertical-overlay
```

Use `npx.cmd` in PowerShell if script policy blocks `npx.ps1`, without weakening the policy. Use `--copy` if links are unsuitable. Do not use a broad `--all` flag to guess the intended host. The previously tested CLI 1.7.2 requires Node.js >=22.20.0; check the selected CLI's requirements when using another release.

For remote installation, replace `.` with the repository URL/ref only after verifying that revision contains the complete 3.1.2 suite. Local v3.1.2 modifications are not published automatically, and a repository URL alone does not establish that this revision is available there. This repository's source URL is [NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill).

## Verify

1. Compare every installed file to the selected source revision and check matching 3.1.2 metadata/license notices. A complete installation has nine entries, 20 core references and 38 Markdown/license files; verify the selected files rather than relying on counts alone.
2. Resolve each wrapper's relative link to `../omni-edit-pro/SKILL.md` in the installed layout. The dependency must actually be readable; a CLI success message is insufficient.
3. Reload the host when necessary and check its skill picker/list. Verify from an unrelated project with a harmless explanation-only prompt.
4. Report what was verified and what remains untested. A filesystem/CLI check does not prove app discovery, native subagent availability or video quality.
5. Use the host's supported invocation, such as `$omni-pro-edit` or its picker in Codex, or slash syntax where supported. Do not claim one syntax works in every agent.

No real video is required for installation verification. Runtime inventory, free-tool selection and media dependencies belong to a later authorized editing request.

## Migrate from v3.1.1

Version 3.1.2 keeps the same nine entries and 38-file/20-reference package, existing routing and output counts, source permissions, Cutout geometry and independent release gate. It adds resolution-scaled upper-caption headroom, stable complete phrase captions with verified color-only highlighting, measured heading centering, explicit padded badge measurements, 2× graphics rendering or an evidenced equivalent, decoded-export text-quality inspection, event/credential verification and accurate source-audio handling. No fixed phrase quota, Y coordinate, bitrate cap or encoder setting is a universal quality guarantee.

1. Preserve and compare local edits, then update the complete core and installed wrappers together from one reviewed 3.1.2 revision.
2. Verify installed bytes, metadata and shared links; check host reload/discovery separately.
3. Use explanation-only cases for sliding captions, abbreviation/sentence boundaries, odd-width or italic headings, 720p/4K headroom, jagged decoded text and unavailable playback. Require a documented post-render evidence/repair/review loop without inventing media checks. Real-video acceptance still requires actual output inspection.

## Migrate from v3.1.0

Version 3.1.1 keeps the same nine entry names, Reference/Auto/Manual routing, all preset output counts, portrait presenter placement, full-duration motion and source-preservation contracts. It adds mandatory middle-channel captions for vertical presenter scenes, every-frame face clearance, measured padded backgrounds that contain all text through animation, source-scoped verified spellings and a dedicated independent Production Video Reviewer. All known defects, including cosmetic and brief defects, block release; the reviewer assesses the complete revised export after repairs. Explicit user choices still govern their named dimensions without silently waiving face protection.

1. Preserve and compare installed local edits against their original revision before replacement.
2. Update core and installed wrappers together from one reviewed 3.1.2 revision, including all 20 shared references. The `omni-edit-pro/references/video-reviewer.md` added in 3.1.1 is required; the reviewer is a role in the existing workflow, not a tenth entry. Include the additional 3.1.2 rules above.
3. Verify installed bytes, matching metadata, shared links and host discovery separately. Existing names in a picker do not establish an updated installation.
4. Use explanation-only checks for a moving vertical presenter, a long animated badge, uncertain proper names and a revised export with a small defect. Require the center caption channel, no face overlap, full padded text containment, evidence-backed wording and an independent release decision. These checks establish planned behavior only; actual video acceptance still needs full viewing/listening and technical evidence.

## Migrate from v3.0

Version 3.1 retains Reference/Auto/Manual routing, all nine entry names and All's six default variants per source. It changes vertical/Reels presenter defaults across Split, Cutout, Overlay and Adaptive: the real speaking video or silhouette goes below the primary animation. Split/Overlay and presenter-led Adaptive fit intact original footage and background below; matching 9:16 Overlay footage no longer defaults to filling the canvas. Cutout uses a real unboxed alpha silhouette over a full-canvas dynamic background, with transparent gaps available for safe graphics rather than a reserved rectangle.

Meaningful graphics and suitable transitions develop throughout every output format. Text settles for reading while useful visuals progress, with justified short holds where needed. Each batch source receives its own topic, scene, subject/clothing, lighting and contrast analysis; no automatic blue/navy palette or cloned animation template supplies that direction. Blue and shared brand systems remain valid when supported, and variants of one source may share a coherent treatment. Explicit placement, stillness and palette instructions win; references are adapted and deviations recorded. Non-presenter scenes do not gain a presenter, and horizontal layouts do not inherit the lower-presenter placement.

1. Back up or compare local modifications before updating. Resolve which changes to retain using the actual update authorization.
2. Replace the shared core and installed wrappers together from one reviewed 3.1.2 revision. Include all references and licenses, including the reviewer additions described above; never mix release versions.
3. Recheck installed bytes, sibling links and host discovery. The nine familiar names alone do not establish that the files were updated.
4. Verify explanation-only prompts for the portrait ordering in all four compositions, matching-ratio Overlay, alpha-gap Cutout, full-duration motion, per-source direction and explicit overrides. A live edit is not needed to check routing, but these checks cannot establish video quality.

## Migrate from v2

Version 3 intentionally changes the main entry and original compatible entry. A designated editing sample selects Reference mode; without one, Auto inspects the source and chooses a treatment. These modes no longer require the v2 wide/tall and Split/Cutout/Overlay answers before media inspection. Use explicit Manual mode for question-led selection.

All nine entry names remain the same. Explicitly selected direct presets retain their named format and composition defaults; clear user overrides change only the named choice. All retains the existing six variants per source before explicit narrowing/override. Adaptive is available in the main workflow and is not added to All.

Follow the same-release update steps above, and verify harmless explanation-only prompts for Auto, Reference, Manual, an explicit preset and All. Do not leave v2 wrappers linked to a v3.1.2 core or the reverse. A live edit is not needed to check the advertised routing contract.

Existing video projects, generated code, working media, and final exports live in their editing workspaces and are separate from a skill-instruction update. Installation does not certify runtime capability or output quality. See [VALIDATION.md](VALIDATION.md) for historical v2/v3.0/v3.1.0/v3.1.1 evidence and separately recorded current v3.1.2 checks.
