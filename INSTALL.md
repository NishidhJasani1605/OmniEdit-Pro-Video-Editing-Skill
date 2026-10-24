# Installing the OmniEdit Pro suite

Install instructions only. Installation does not start an editing job, ask the two editing questions, spawn production teams, create a video project, or install processing tools/models.

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

The core includes SKILL.md, LICENSE and its complete references subtree. Each wrapper includes SKILL.md and LICENSE and loads the sibling core. Do not copy only an entry file, nest the suite under an undiscoverable extra directory, or combine versions. For a smaller installation, install the core plus selected wrappers. The core can also be invoked on its own.

Manual copying needs no Python, Node.js, application code or upstream skill installations.

## Optional Skills CLI

From a reviewed local checkout containing this release, with Git and a supported Node/npm runtime:

```sh
npx skills add . --global --agent <agent-id> --skill omni-edit-pro omni-pro-edit omni-pro-edit-horizontal-split omni-pro-edit-horizontal-cutout omni-pro-edit-horizontal-overlay omni-pro-edit-vertical-split omni-pro-edit-vertical-cutout omni-pro-edit-vertical-overlay omni-pro-edit-all
```

Replace `<agent-id>` with the host's verified CLI ID. For a smaller selection:

```sh
npx skills add . --global --agent <agent-id> --skill omni-edit-pro omni-pro-edit-vertical-overlay
```

Use `npx.cmd` in PowerShell if script policy blocks `npx.ps1`, without weakening the policy. Use `--copy` if links are unsuitable. Do not use a broad `--all` flag to guess the intended host. The previously tested CLI 1.7.2 requires Node.js >=22.20.0; check the selected CLI's requirements when using another release.

For remote installation, replace `.` with the repository URL/ref only after verifying that revision contains the complete suite. Local modifications are not published automatically. This repository's source URL is [NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill).

## Verify

1. Compare every installed file to the selected source revision. Verify the core's complete reference subtree and the selected wrappers' licenses.
2. Resolve each wrapper's relative link to `../omni-edit-pro/SKILL.md` in the installed layout. The dependency must actually be readable; a CLI success message is insufficient.
3. Reload the host when necessary and check its skill picker/list. Verify from an unrelated project with a harmless explanation-only prompt.
4. Report what was verified and what remains untested. A filesystem/CLI check does not prove app discovery, native subagent availability or video quality.
5. Use the host's supported invocation, such as `$omni-pro-edit` or its picker in Codex, or slash syntax where supported. Do not claim one syntax works in every agent.

No real video is required for installation verification. Runtime inventory, free-tool selection and media dependencies belong to a later authorized editing request.
