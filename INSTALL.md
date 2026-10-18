# Install OmniEdit Pro at user scope

Use this guide when a user asks a coding agent to download and install OmniEdit Pro. Complete the installation and verify the result. Installation alone does not start an editing task.

Repository: [NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill). Canonical skill name: `omni-edit-pro`. Installable source folder: `skills/omni-edit-pro/`.

## 1. Detect the host and preserve the project

Identify the current coding agent, operating system, local or remote execution environment, and its supported user-level skill roots. Use actual environment information and host documentation; do not guess the host from the chosen language model. Consult the [compatibility guide](skills/omni-edit-pro/references/agent-compatibility.md) for documented directories, agent IDs, invocation methods, and known CLI path differences.

Place temporary downloads outside the current project and resolve the destination under the current user's supported skill root. Do not add project configuration, `.agents`, media, packages, or an editing project to the current project as part of installation. Do not alter existing project files. A remotely hosted agent needs an installation in its own supported environment; files on the user's computer may not be accessible to it.

Inspect the native and shared skill roots the host reads for an existing `omni-edit-pro`, including links and duplicate names. If the same complete revision is already installed, verify and reuse it. Preserve custom edits. Replace a differing installation only when the user has authorized the update; do not use an unattended overwrite flag to bypass a conflict.

## 2. Check installation prerequisites

- A performing agent needs filesystem access and a local shell or an equivalent supported file-installation capability.
- The Skills CLI route needs Git, network access, and compatible Node.js/npm. The previously tested CLI version, `skills@1.7.2`, requires Node.js >=22.20.0. Check actual versions before invoking it.
- Manual installation from an extracted ZIP needs no Node.js, npm, or Python. Git is required only if downloading with Git.

Do not install or upgrade Node.js, Python, FFmpeg, Remotion, browsers, GPU runtimes, speech packages, or model weights just to install these instructions. If the CLI prerequisites are missing, use the manual route when possible. Report any unresolved installation requirement precisely. Runtime editing dependencies are detected later, after the user requests an edit.

## 3. Download and install the complete skill

### Supported Skills CLI route

Choose an explicit supported agent ID from the compatibility guide, then substitute it for `<agent-id>`:

```sh
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent <agent-id>
```

For example, in Codex:

```sh
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent codex
```

Keep `--global`; do not replace it with a project installation or use `--all`. Add `--copy` if the host/filesystem needs copies instead of links. Use `npx.cmd` in PowerShell if needed. A selected agent ID must correspond to the actual host. For Antigravity or Windows Devin, use the documented manual destination when the CLI mapping does not match the host's recognized user directory.

Read the complete installation summary. The tested CLI's automatic agent selection can report a PromptScript failure even while installing other copies and exiting zero. A zero exit code alone is insufficient evidence of a correct installation.

### Manual download route

1. Download the [repository ZIP](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill/archive/refs/heads/main.zip) or clone the exact repository into a temporary directory outside the current project. Extract any archive there and inspect its contents.
2. Resolve the host's supported user-level skill root from the compatibility guide and check conflicts before writing. Create the parent directory if needed.
3. Copy the entire `skills/omni-edit-pro/` subtree into the root as `omni-edit-pro/`. The result must be `<user-skill-root>/omni-edit-pro/SKILL.md`, with `LICENSE` and `references/` beside it. Copying the repository root, an extra nested folder, or only `SKILL.md` will not produce the intended package.
4. Use a durable installed copy or a supported link to a durable location. Do not leave a skill linked to a temporary download that will be deleted.

The repository's root README, installation guide and attribution file are distribution documentation. The installable skill is self-contained within `skills/omni-edit-pro/`; it does not need these root documents or the five upstream skills at runtime.

## 4. Verify files and host discovery

The installed skill contains these **12 files**:

```text
omni-edit-pro/
├── SKILL.md
├── LICENSE
└── references/
    ├── workflow.md
    ├── environment.md
    ├── transcription-sync.md
    ├── visual-planning.md
    ├── broll-assets.md
    ├── motion-design.md
    ├── layouts-effects.md
    ├── audio-rendering.md
    ├── quality-assurance.md
    └── agent-compatibility.md
```

Compare every installed file with the chosen downloaded revision, allowing only normal platform line-ending differences. Verify that the YAML `name` is `omni-edit-pro`, the containing folder has the same name, and every relative Markdown reference resolves. Confirm that any installation link points to a location that will remain available.

If the CLI is available, inspect its global listing, optionally filtered to the selected host:

```sh
npx skills list --global
```

Then check the actual host's skill list or picker. Reload/restart it when required. Confirm `omni-edit-pro` is present and explain the correct activation method: `$omni-edit-pro` or `/skills` in Codex; `/omni-edit-pro` in supporting slash-command hosts; `/skill:omni-edit-pro` in Kimi Code CLI. Use the compatibility guide for other hosts rather than promising one command everywhere.

If a harmless invocation is available, ask the skill to describe its workflow only. Do not render, download processing dependencies, or create a video project as a discovery test. Confirm that the current project was not changed.

Distinguish verified files, CLI listing, and native host discovery. If the host cannot be queried or needs a new session, say exactly which check remains; do not claim it has loaded the skill merely because copying succeeded.

## 5. Confirm completion

Tell the user the detected agent, installed path and source revision, whether all 12 files match, the discovery result, the correct invocation, and any reload or prerequisite still needed. State that editing work starts only when requested. Remove disposable downloads when safe, leaving the installed skill and its durable link targets intact.
