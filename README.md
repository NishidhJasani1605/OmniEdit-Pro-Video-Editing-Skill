# OmniEdit Pro — Professional AI Video Editing Agent Skill

**One portable skill for planning, editing, captioning, compositing, and finishing video with an AI coding agent.**

OmniEdit Pro guides an agent from source inspection through a verified delivery, using Remotion for composition and FFmpeg/FFprobe for media preparation and checks. It supports talking-head videos, podcasts, YouTube, Shorts and Reels, lessons, explainers, product demos, promotional videos, interviews, documentaries and other genres supported by the available tools.

This repository contains reusable instructions, not an editor application or a rendering engine. Install once at user scope; invoke it from unrelated projects. No upstream skills or heavyweight video dependencies are installed with it.

## Install in one command

Requirements: a compatible coding agent, Git, network access, and Node.js/npm supported by the Skills CLI. The tested CLI release, **1.7.2**, requires **Node.js 22.20.0 or newer**. A manual folder installation needs no Node.js.

**Before running:** inspect your host's user/shared skill roots for an existing `omni-edit-pro` and preserve any edits. The CLI may replace same-name files and may skip confirmation inside agent environments. Resolve conflicts before installation; see the [installation guide](skills/omni-edit-pro/references/agent-compatibility.md).

```sh
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global
```

Choose your agent when prompted. `--global` means your user account, not a system-wide administrator install. It keeps skill files outside the current project. For predictable installation, use the explicit `--agent` command below: in our isolated test, CLI 1.7.2's automatic selection installed the skill but also printed a PromptScript global-install warning despite returning success. Antigravity and Windows Devin have path caveats: use the manual route below rather than assuming the CLI destination is recognized.

To inspect discovery and your installed skills:

```sh
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --list
npx skills list --global
```

Use `npx.cmd` in PowerShell if its script execution policy blocks `npx`. Add `--copy` if symlinks are unsuitable. For reproducible installation with this release's CLI, replace `skills` with `skills@1.7.2`.

## Or install with one prompt

Copy this into your AI coding agent:

> Install OmniEdit Pro from https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill.
>
> Detect my current AI coding environment and install the complete `omni-edit-pro` Agent Skill at user/global scope using the officially supported method.
>
> Verify that all skill instructions and references are installed correctly and that the skill is discoverable.
>
> Use `/omni-edit-pro` where supported or explain the correct equivalent invocation for my agent.
>
> Make it available across my projects without modifying the current project. Do not install heavyweight video-processing dependencies or create a video project until I explicitly request an editing task.

## Choose an individual agent

After the conflict check, run the appropriate command:

```sh
# OpenAI Codex
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent codex

# Claude Code
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent claude-code

# Cursor
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent cursor

# Kimi Code CLI
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent kimi-code-cli

# GitHub Copilot / compatible VS Code clients
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --skill omni-edit-pro --global --agent github-copilot
```

| Agent | Activate after installation |
| --- | --- |
| Codex | `$omni-edit-pro`, or `/skills` and select it |
| Claude Code, Cursor, supporting Copilot clients | `/omni-edit-pro`, or let the agent select it from your request |
| Kimi Code CLI | `/skill:omni-edit-pro` |
| Antigravity App / CLI | `/omni-edit-pro`; IDE also offers Customizations > Skills |
| Devin CLI | `/omni-edit-pro`; Desktop/Cascade uses `@omni-edit-pro` |
| DeepSeek Harness with skill components enabled | `/omni-edit-pro`; documented, not runtime-tested here |

For **Antigravity**, copy the complete `skills/omni-edit-pro` folder to `~/.gemini/config/skills/` for App/IDE, or `~/.gemini/antigravity-cli/skills/` for CLI. For **Devin CLI**, use its documented native directory or `~/.agents/skills/`; the native Windows path is `%APPDATA%/devin/skills/`. For **DeepSeek Harness**, use its configured filesystem skill root, normally `~/.dsh/skills/` or `~/.agents/skills/`. These are distinct products and surfaces, not promises about every cloud or chat interface.

The [compatibility guide](skills/omni-edit-pro/references/agent-compatibility.md) links each platform's official documentation, explains path discrepancies, and gives complete manual installation and conflict-handling steps. It also covers DeepSeek as a model backend, other Agent Skills hosts, remote environments and discovery troubleshooting.

## What it brings to an edit

- Source inspection: streams, FPS, aspect ratio, color, audio, existing cuts and semantic observations.
- Speech analysis: transcription, reviewed word or phrase timestamps, narration understanding and frame-based cue placement.
- Creative direction: genre-appropriate pacing, shot composition, typography, color and restrained transitions.
- Visual support: relevant B-roll, sourced images, original diagrams, illustrations and licensed assets.
- Motion and layouts: kinetic text, infographics, SVG-style animation, callouts, camera movement, face-safe captions, PiP and split screen.
- Finishing: original audio preservation, deliberate mixing/color treatment, previews, technical checks, visual review and listening review.

For talking-head and narrated content, the default is **all original dialogue, in order, on its original timeline**. The presenter track stays continuous underneath supporting visuals when applicable. Pause trimming, jump cuts, speech regeneration and retiming require explicit creative instructions. Other genres follow your brief. Timing is bounded by output frames and the accuracy of the available alignment, not a promise of impossible millisecond precision.

## Try it

In Codex:

```text
$omni-edit-pro Edit my supplied interview for YouTube. Preserve every word,
pause, and lip-sync. Add accurate phrase captions and selective supporting
visuals. Inspect the source first, use the existing local tools, and ask
before installing large dependencies. Put the editable project and exports
in the workspace I specify.
```

In a slash-command host:

```text
/omni-edit-pro Create a portrait product explainer from my footage and
narration. Use clear diagrams and a readable presenter window. Keep the
narration intact, verify asset rights, preview difficult sections, then
deliver the final video and editable project.
```

For discovery testing without starting an edit:

```text
Use omni-edit-pro to explain your workflow for a narrated video.
Do not install dependencies, create a project, or render anything.
```

## Tools needed when editing

The agent needs local file/terminal access and a workspace for generated project code. Rendering normally uses compatible Node.js, React and Remotion packages plus a supported browser. FFmpeg/FFprobe can be available system tools or compatible tools supplied by the chosen runtime. Speech tasks can use an available WhisperX, whisper.cpp, another suitable recognizer/aligner, or a reviewed supplied transcript. GPU acceleration and models are optional according to the chosen engine.

The skill detects what exists and asks before installing heavyweight dependencies. Hosted APIs, stock services, models and media can have separate costs, terms and authorization requirements. No particular API key or paid service is mandatory. Remotion has [separate engine licensing](https://www.remotion.dev/license); this skill's MIT license does not replace it.

## Troubleshooting and limits

- **Skill missing:** verify the complete folder and correct user scope, reload the host, inspect its picker, and check for same-name project skills. Global files on one machine do not automatically reach remote agents.
- **No footage:** the agent can prepare a provisional brief but needs source files for a real edit.
- **No renderer:** it reports missing tools and can prepare the plan. A simpler FFmpeg fallback is appropriate only if it satisfies the task.
- **Poor or missing word timing:** use reviewed phrase captions or obtain alignment; do not invent precise word timestamps.
- **Unsupported media or render failure:** preserve originals, diagnose a small interval, and verify any compatible intermediate before continuing.
- **Unclear asset rights:** replace the asset or obtain permission before a cleared final delivery.
- **No audiovisual review tools:** exports must disclose the review gap. A successful render command is not proof of professional quality.

## Structure

```text
.
├── README.md
├── LICENSE
├── ATTRIBUTIONS.md
├── .gitignore
└── skills/omni-edit-pro/
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

The lightweight entrypoint loads focused references only when needed. There are no installers, application source files, media, model weights or upstream repositories in the published package. Future editing projects are created separately in the user's chosen workspace.

## Validation

Release checks passed for frontmatter/naming, all internal Markdown links, the exact 16-file repository allowlist, secret/path scans, and CLI discovery. Skills CLI 1.7.2 on Node 24.19.0 installed all 12 skill files with matching hashes in eight isolated agent-target tests, preserving unrelated working directories. Automatic selection's PromptScript warning and the Antigravity/Windows Devin path differences are documented above.

The local Codex app-server parsed and listed the skill as enabled using an explicit isolated skill root. This verifies native parsing/discovery; it does not establish automatic global-root discovery or a completed model invocation. Other host applications were not launched. Scenario checks covered conflicting duration requests, rational frame timing, missing dependencies and asset-rights uncertainty. These checks validate packaging and instruction behavior; **no real video render or professional editing-quality benchmark is claimed by this release**.

## License and acknowledgments

Original OmniEdit Pro material is [MIT licensed](LICENSE), with the notice also bundled inside the installable skill. Research drew on Remotion's official skills, iart.ai's B-roll and motion-design skills, Ethan Woo's video-editing skills, and Nana AI's talking-head packaging skill. The result is a new coordinated workflow, not concatenated upstream instructions.

See [ATTRIBUTIONS.md](ATTRIBUTIONS.md) for inspected revisions, license findings, capability boundaries and integration decisions. Installation is independent of all five upstream skills. The package follows the [Agent Skills specification](https://agentskills.io/specification).
