# Installing OmniEdit Pro 3.2.0

Install instructions only. Installation does not start an editing job, ask creative-selection questions, spawn production teams, create a video project, or install processing tools/models. No external skill is a mandatory runtime dependency.

## Select the destination and preserve existing work

Identify the actual agent and its supported user-level skill root. See [Agent compatibility](skills/omni-edit-pro/references/agent-compatibility.md) for previously checked conventions and host limitations. Inspect both native and shared roots for existing names or symlinks. Preserve local edits; resolve conflicting replacements using the user's actual update authorization. A CLI can skip confirmation in an agent environment, so absence of a confirmation flag is not an overwrite safeguard.

Use user scope when the user wants the skill across projects. Do not change the current project's configuration merely to install a personal skill.

## Install the same-release sibling folders

Copy these complete directories from `skills/` into the selected skill root:

- `omni-edit-pro` — main entry and shared core
- `omni-edit-pro-horizontal-split`
- `omni-edit-pro-horizontal-cutout`
- `omni-edit-pro-horizontal-overlay`
- `omni-edit-pro-vertical-split`
- `omni-edit-pro-vertical-cutout`
- `omni-edit-pro-vertical-overlay`
- `omni-edit-pro-all`

The complete suite contains 36 Markdown/license files: the core's SKILL.md, LICENSE and 20 reference files, plus SKILL.md and LICENSE for each of seven wrappers. References include reference analysis, automatic direction, portrait composition, full-duration motion, per-source visual planning and the new dedicated [Production Video Reviewer](skills/omni-edit-pro/references/video-reviewer.md). Each wrapper loads the sibling core. Do not copy only an entry file, nest the suite under an undiscoverable extra directory, or combine versions. For a smaller installation, install the core plus selected wrappers. The core can also be invoked on its own.

Manual copying needs no Python, Node.js, application code or upstream skill installations.

## Optional Skills CLI

From a reviewed local checkout containing all eight 3.2.0 entries, with Git and a supported Node/npm runtime:

```sh
npx skills add . --global --agent <agent-id> --skill omni-edit-pro omni-edit-pro-horizontal-split omni-edit-pro-horizontal-cutout omni-edit-pro-horizontal-overlay omni-edit-pro-vertical-split omni-edit-pro-vertical-cutout omni-edit-pro-vertical-overlay omni-edit-pro-all
```

Replace `<agent-id>` with the host's verified CLI ID. For a smaller selection:

```sh
npx skills add . --global --agent <agent-id> --skill omni-edit-pro omni-edit-pro-vertical-overlay
```

Use `npx.cmd` in PowerShell if script policy blocks `npx.ps1`, without weakening the policy. Use `--copy` if links are unsuitable. Do not use a broad `--all` flag to guess the intended host. The previously tested CLI 1.7.2 requires Node.js >=22.20.0; check the selected CLI's requirements when using another release.

For remote installation, replace `.` with the repository URL/ref only after verifying that revision contains the complete 3.2.0 suite. Local v3.2.0 modifications are not published automatically, and a repository URL alone does not establish that this revision is available there. This repository's source URL is [NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill).

## Verify

1. Compare every installed file to the selected source revision and check matching 3.2.0 metadata/license notices. A complete installation has eight entries, 20 core references and 36 Markdown/license files; verify the selected files rather than relying on counts alone.
2. Resolve each wrapper's relative link to `../omni-edit-pro/SKILL.md` in the installed layout. The dependency must actually be readable; a CLI success message is insufficient.
3. Reload the host when necessary and check its skill picker/list. Verify from an unrelated project with a harmless explanation-only prompt.
4. Report what was verified and what remains untested. A filesystem/CLI check does not prove app discovery, native subagent availability or video quality.
5. Use the host's supported invocation, such as `$omni-edit-pro` or its picker in Codex, or slash syntax where supported. Do not claim one syntax works in every agent.

No real video is required for installation verification. Runtime inventory, free-tool selection and media dependencies belong to a later authorized editing request.

## Migrate from earlier releases

Version 3.2.0 standardizes every entry on the `omni-edit-pro` naming order.
The main entry is the shared core itself; the former duplicate main wrapper is
merged into it. Install the eight unique folders above: one main/core, six
format/composition presets and All. The suite contains 36 files and 20 shared
references. The number of skill entries is separate from the six output variants
requested by unrestricted All mode.

1. Inventory the installed suite and back it up outside active skill roots.
   Compare local edits against the prior revision and migrate them before replacement.
2. Install the complete `omni-edit-pro` core and the renamed preset folders from
   the same 3.2.0 revision. Do not rename the shared core into a preset or overwrite
   it with the former main wrapper; the core contains the full production workflow.
3. Verify installed bytes, frontmatter names, sibling core links and discovery.
   Remove only verified obsolete suite folders from active discovery after their
   contents have been backed up and any local changes reconciled. Do not keep
   duplicate main aliases or a mixture of old and new preset names.
4. Update saved invocation prompts and installation commands to the eight names
   above. Use the host's supported syntax, such as `$omni-edit-pro`,
   `$omni-edit-pro-vertical-split` or `$omni-edit-pro-all` in Codex.
5. Reload the host if needed and check from an unrelated project. A filesystem
   check does not establish that an already-open host has refreshed its skill list.

The generic entry retains Reference, Auto and Manual, with Adaptive available.
The six direct presets retain their named orientation and composition, and All
still requests six variants per source unless explicitly narrowed. All prior
caption, framing, motion, spelling, audio and independent-review requirements
remain in the core. A rename does not authorize video processing or change source
editing permissions.

Older behavior changes are retained: v3 removed the compulsory selection gate
from Auto/Reference, v3.1 added shared portrait placement and motion rules, and
v3.1.1–3.1.2 added strict text/reviewer and finishing requirements. Manual still
waits for genuinely missing creative choices. Existing videos and editing
projects stay in their own workspaces; installation updates instructions only.
See [VALIDATION.md](VALIDATION.md) for historical checks and the current naming
and installation evidence.
