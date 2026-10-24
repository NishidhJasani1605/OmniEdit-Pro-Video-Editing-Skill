# OmniEdit Pro

**An instruction-only AI skill suite for editing one video or a whole batch, with separate video teams, smooth animations, and protected speaker framing.**

Choose **horizontal 16:9** or **vertical 9:16**, then choose **Split**, **Cutout**, or **Overlay**. Use a direct preset when you know what you want, or let the main skill ask two simple questions. All mode requests every combination for each video.

**Version:** 2.0.0 · **Package:** Markdown instructions and license notices · **License:** MIT

The skill guides a capable AI agent through the edit. The agent can write processing code and use free local tools in your editing workspace. This repository contains no processing scripts, models, media, or editor application.

## Contents

- [Quick start](#quick-start)
- [Install the suite](#install-the-suite)
- [Choose a skill](#choose-a-skill)
- [The three editing styles](#the-three-editing-styles)
- [The two compulsory questions](#the-two-compulsory-questions)
- [Example requests](#example-requests)
- [A separate team for every video](#a-separate-team-for-every-video)
- [Quality and animation rules](#quality-and-animation-rules)
- [Free local processing](#free-local-processing)
- [Final output folders](#final-output-folders)
- [Sources and adaptations](#sources-and-adaptations)
- [Validation and current limits](#validation-and-current-limits)
- [Project guide](#project-guide)
- [Frequently asked questions](#frequently-asked-questions)

## Quick start

1. Install the complete suite using one of the methods below.
2. Supply your video files or accessible paths and an editing workspace.
3. Select `omni-pro-edit` to answer the two questions, a direct preset to choose immediately, or `omni-pro-edit-all` for all six versions.
4. The agent checks its tools, creates a separate job/team for each video, edits, reviews, and exports.
5. Find checked videos in **Final Output Videos**, separated by source video.

For example, select `omni-pro-edit-vertical-overlay` and say:

> Edit these three videos separately. Add smooth animations that explain what each speaker says. Keep the full original frame and dialogue. Use this folder as the editing workspace.

The agent needs access to the files and an environment capable of running the required local tools. Native agent-team support comes from the host.

## Install the suite

### Option 1 — Ask your agent to install it

Copy this prompt into your coding agent:

```text
Install the complete OmniEdit Pro suite from:
https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill

Read INSTALL.md. Detect this agent's supported user-level skill location
so I can use the suite across projects. Preserve any existing local edits.
Install all nine sibling skill folders, including the shared omni-edit-pro
core, every reference file, and each license notice from the same revision.
Verify the installed files and shared-core links, then check host discovery.
Tell me the correct invocation for this host.

Install only the skill instructions at this stage. Do not start a video
edit or install video tools, browser runtimes, or model weights.
```

Detailed installation, updating, and verification steps are in [INSTALL.md](INSTALL.md).

### Option 2 — Use the Skills CLI

The CLI needs Git and a compatible Node.js/npm runtime. First check for an existing installation and preserve local changes.

This example selects the Codex CLI target and all nine skills explicitly:

```sh
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --global --agent codex --skill omni-edit-pro omni-pro-edit omni-pro-edit-horizontal-split omni-pro-edit-horizontal-cutout omni-pro-edit-horizontal-overlay omni-pro-edit-vertical-split omni-pro-edit-vertical-cutout omni-pro-edit-vertical-overlay omni-pro-edit-all
```

Replace `codex` with your host's verified CLI agent ID. The [compatibility guide](skills/omni-edit-pro/references/agent-compatibility.md) records host-specific conventions and caveats; verify them for your installed host version. Use `npx.cmd` in PowerShell if its script policy blocks `npx.ps1`. Use `--copy` when filesystem links are unsuitable.

For a smaller installation, include **both the shared core and your chosen preset**:

```sh
npx skills add NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill --global --agent codex --skill omni-edit-pro omni-pro-edit-vertical-overlay
```

The previously checked Skills CLI 1.7.2 requires Node.js 22.20.0 or newer. Check requirements when selecting another CLI release. Installing instructions does not install video-processing dependencies.

### Option 3 — Download and copy manually

[Download the repository ZIP](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill/archive/refs/heads/main.zip), extract it, and copy all nine folders inside `skills/` into your agent's supported user-level skill directory as siblings.

Keep the full `omni-edit-pro` core, including its `references/` directory, and every selected preset's `SKILL.md` and `LICENSE`. Reload the host if needed and check its skill list. Manual copying needs no Node.js or Python.

**Preset dependency:** the eight new entries load the sibling `omni-edit-pro` shared core. They must come from the same release. If the core is missing, the preset reports an incomplete installation before processing anything.

## Choose a skill

| Skill | Orientation | Style / behavior |
| --- | --- | --- |
| [`omni-pro-edit`](skills/omni-pro-edit/SKILL.md) | Ask if missing | Main entry; asks only for missing choices |
| [`omni-pro-edit-horizontal-split`](skills/omni-pro-edit-horizontal-split/SKILL.md) | Horizontal 16:9 | Speaker footage beside explanations |
| [`omni-pro-edit-horizontal-cutout`](skills/omni-pro-edit-horizontal-cutout/SKILL.md) | Horizontal 16:9 | Isolated speaker over graphics |
| [`omni-pro-edit-horizontal-overlay`](skills/omni-pro-edit-horizontal-overlay/SKILL.md) | Horizontal 16:9 | Original footage with animations on top |
| [`omni-pro-edit-vertical-split`](skills/omni-pro-edit-vertical-split/SKILL.md) | Vertical 9:16 | Speaker footage above/below explanations |
| [`omni-pro-edit-vertical-cutout`](skills/omni-pro-edit-vertical-cutout/SKILL.md) | Vertical 9:16 | Isolated speaker over graphics |
| [`omni-pro-edit-vertical-overlay`](skills/omni-pro-edit-vertical-overlay/SKILL.md) | Vertical 9:16 | Original footage with animations on top |
| [`omni-pro-edit-all`](skills/omni-pro-edit-all/SKILL.md) | Both | All three styles in each orientation: six versions per video |
| [`omni-edit-pro`](skills/omni-edit-pro/SKILL.md) | Ask if missing | Original compatible entry and shared workflow |

Use your host's skill picker or supported command syntax. Slash commands work in supporting hosts; Codex can use `$omni-pro-edit` or its skill picker. The exact invocation and capabilities depend on the host, not just the model or IDE name.

## The three editing styles

| Style | What you see | Horizontal arrangement | Vertical arrangement |
| --- | --- | --- | --- |
| **1. Split** | Original video in one region; explanations in another | Speaker footage left or right | Speaker footage above or below |
| **2. Cutout** | Speaker's background removed; their real silhouette sits over graphics | Speaker placed to suit the scene, usually lower/central | Speaker placed to suit the tall scene, usually lower/central |
| **3. Overlay** | Original video and background kept together; graphics appear over clear areas | Original footage remains the main image | Original footage remains the main image, fitted to the tall canvas |

**Split:** fit the complete original source inside the speaker region. Choose its size to keep the person clear; diagrams, cards, labels, illustrations, and relevant clips use the explanation region.

**Cutout:** remove the background while protecting the person's face, hair, hands, shoulders, movement, and source detail. There is no separate rectangular presenter panel. Review moving edges and difficult gestures before accepting the result.

**Overlay:** keep the original footage and background together. Add useful cards, badges, captions, diagrams, and other animations without pushing the video to one side or removing its background.

A change of aspect ratio may need padding or a smaller fitted image. Preserve the full frame, adjust the graphics first, and review the speaker at the intended viewing size. Unchanged apparent person size, no cropping, and full-screen coverage cannot always be achieved together.

See [styles and framing](skills/omni-edit-pro/references/editing-styles.md) for the exact acceptance rules.

## The two compulsory questions

For an editing request, if orientation is missing from your prompt and you have not explicitly selected a preset, the agent first asks:

> Do you want a wide video for YouTube (horizontal 16:9) or a tall video for Reels/Shorts (vertical 9:16)?

It waits for your answer. If style is still missing, it then asks:

> Which style do you want: 1. Split — speaker beside or above/below explanations; 2. Cutout — speaker with the background removed over graphics; or 3. Overlay — original video with animations on top?

It waits again before processing.

| Your request | What happens |
| --- | --- |
| Neither choice supplied | Ask orientation first, then style |
| Orientation supplied | Ask only style |
| Style supplied | Ask only orientation |
| Both supplied or a direct preset explicitly selected | Start without repeating the questions |
| All preset explicitly selected | Request all six combinations |
| Clear prompt override of a preset | Follow the explicit user choice |
| Preset matched automatically by the host/model | Use the actual prompt; ask for missing choices |
| Explain, install, or improve the skill | Do that task without starting an edit |

No media probing, transcription, editing-team dispatch, or rendering starts while a required selection is unanswered. A timeout or preselected UI option is not an answer. Batch-wide choices apply once to all videos unless you give different choices for specific videos.

No separate question-asking skill is needed. These rules live in [selection.md](skills/omni-edit-pro/references/selection.md).

## Example requests

These examples use slash syntax; use the equivalent skill picker or command supported by your host.

**Let the skill ask:**

```text
/omni-pro-edit
Edit these three attached videos separately.
Use my Video Project folder as the workspace.
```

**Choose one result directly:**

```text
/omni-pro-edit-vertical-overlay
Edit this video as a Reel with useful animated cards and captions.
Keep the complete original frame and original dialogue.
```

**Choose the speaker position:**

```text
/omni-pro-edit-horizontal-split
Keep the original video on the left and explain the spoken ideas
with diagrams on the right. Preserve the person's full framing.
```

**Request every combination:**

```text
/omni-pro-edit-all
Make all six versions of each supplied video.
Use separate teams and save checked videos in Final Output Videos.
```

Two input videos in All mode request **12 final videos**. Five request **30**. A single preset requests one result per input. Asking for both orientations with only Overlay requests two versions per input, not all six.

## A separate team for every video

Each video receives a unique job ID, its own working folder, and specialist assignments linked to that video.

| Specialist role | Responsibility |
| --- | --- |
| Video lead | Own the plan, source identity, timeline integration, and delivery status |
| Speech and captions | Review wording, uncertainty, timestamps, and caption cues |
| Visual direction and assets | Choose the visual treatment and relevant, cleared supporting material |
| Layout and animation | Build the selected style and synchronize readable motion |
| Cutout specialist | Isolate the speaker locally and check detail, edges, and movement |
| Audio and export | Preserve narration, prepare sound, render previews and candidates |
| Independent reviewer | Check requirements plus actual visual, audio, and timing quality |

Assignments use real native subagent tools and real task handles. Roles describe responsibilities; they do not imply certified expertise.

The coordinator runs independent work in parallel where the host permits it and queues the rest. Agent slots, GPU memory, render capacity, and storage set concurrency. Videos with the same filename still get different identities and folders.

If nested agents are unavailable, the top-level coordinator dispatches specialists. If native subagents are unavailable entirely, the skill explains that limitation and asks whether to use one agent with the same role checklists or wait for a team-capable environment. It never labels imaginary workers as a team.

The workflow adapts **Dispatching Parallel Agents** and **Subagent-Driven Development**. You do not need to install an additional orchestration library or those upstream skills. See [per-video teams](skills/omni-edit-pro/references/batch-teams.md).

## Quality and animation rules

| Requirement | What the agent must do |
| --- | --- |
| Protect framing | Preserve the full decoded source in Split/Overlay; avoid unwanted crop, stretch, zoom, or face enlargement |
| Protect Cutout detail | Keep real subject appearance and motion; reject missing hands/hair, halos, flicker, holes, or soft faces |
| Preserve speech | Keep dialogue, order, pauses, original timing, and lip-sync unless you explicitly request changes |
| Animate meaning | Choose graphics from reviewed speech; reveal ideas when they are spoken |
| Keep motion readable | Use smooth entrances, enough reading time, clear exits, and a consistent visual style |
| Protect the person | Avoid covering faces, essential gestures, existing source text, or captions |
| Preserve factual meaning | Use real values for charts/badges; use actual audio for measurement-like waveforms |
| Review each version | Check horizontal and vertical compositions independently |
| Deliver honestly | Keep unreviewed or failed candidates out of the final folder |

The agent may use diagrams, original illustrations, information cards, typography, suitable B-roll, subtitles, progress badges, or other elements that fit the actual video. It should simplify crowded scenes instead of forcing effects into every moment.

No automatic pause removal, jump cuts, regenerated speech, or source punch-ins are part of the default workflow. A user can request specific editorial changes. Strong presentation and audience engagement are goals; virality is not guaranteed.

## Free local processing

The workflow uses free local media processing and suitable assets:

- Prefer a compatible local Remotion setup when its terms permit the intended use without payment, with FFmpeg/FFprobe for preparation and checks.
- Use a capable free local compositor if Remotion is unavailable or requires payment for that use.
- Use available local transcription/alignment, a supplied transcript, or manually reviewed cues.
- Reuse user-cleared assets, compatible free assets, or original graphics created by the agent.
- Keep generated code, dependencies, caches, and media in the editing workspace.

For **Cutout**, the agent assesses the actual footage and local options: supplied alpha/masks, genuine chroma key, suitable local matting/segmentation, or code-assisted tracking/rotoscoping. Simple rectangular cropping cannot isolate a person's silhouette.

The agent tests a difficult passage before processing the full video. If a free local method still fails quality checks, it reports the Cutout limitation and preserves a labeled preview. Split and Overlay work continues independently. In All mode, four completed variants plus two failed Cutouts remain a partial six-variant request.

There is no automatic paid API, credit-service, paid-stock, or hosted-processing fallback. The chosen AI host may have its own subscription or usage charges; the skill does not change those terms. Runtime tools, weights, fonts, and media also have their own licenses.

See [environment decisions](skills/omni-edit-pro/references/environment.md) and [local Cutout](skills/omni-edit-pro/references/local-cutout.md).

## Final output folders

Checked videos use the exact folder name **Final Output Videos**, unless you explicitly request a different destination.

```text
<editing-workspace>/
├── Final Output Videos/
│   ├── video-001-interview/
│   │   ├── video-001-interview-horizontal-split-v001.mp4
│   │   ├── video-001-interview-horizontal-cutout-v001.mp4
│   │   ├── video-001-interview-horizontal-overlay-v001.mp4
│   │   ├── video-001-interview-vertical-split-v001.mp4
│   │   ├── video-001-interview-vertical-cutout-v001.mp4
│   │   └── video-001-interview-vertical-overlay-v001.mp4
│   └── video-002-lesson/
│       └── ...checked versions of the second video
└── Working Files/
    ├── batch-progress.md
    └── video-001-interview/
        ├── plan.md
        ├── source-analysis/
        ├── assets/
        ├── project/
        ├── previews/
        ├── candidate-exports/
        └── review/
```

The six-file example applies to All mode after every version passes. A single preset produces only its requested variant. New version numbers preserve earlier finals.

The agent renders full candidates in Working Files, reviews them, then promotes checked files to Final Output Videos. Missing audiovisual review means **needs review**, not complete. Captions, editable projects, credits, and review evidence are linked separately from their working folders.

For every requested video/version, the delivery report includes status, exact file path when available, dimensions, frame rate, duration, checks performed, and remaining limitations. Editing does not automatically publish or upload the videos.

## Sources and adaptations

The suite was informed by **nine repositories containing ten selected source entries**. Both delegation skills come from Superpowers.

| Source | Contribution |
| --- | --- |
| [Official Remotion Skills](https://github.com/remotion-dev/skills) | Composition, captions, media, timing, and rendering guidance |
| [iArt Motion Design](https://github.com/iart-ai/motion-design-skills) | Art direction, smooth motion, composition, and visual hierarchy |
| [iArt Talking-Head B-roll](https://github.com/iart-ai/b-roll-skills) | Relevant speech-based visuals and continuous narration |
| [AI Self-Media Packaging](https://github.com/zhouyuechuan2025-ui/ai-self-media-video-packaging-skill) | Presenter layouts, cards, flow diagrams, and illustration ideas |
| [iArt TikTok Video](https://github.com/iart-ai/tiktok-video-skills) | Vertical presentation, captions, lower thirds, and short-form clarity |
| [iArt Kinetic Typography](https://github.com/iart-ai/kinetic-typography-skills) | Readable phrase reveals and spoken-keyword emphasis |
| [iArt Explainer Video](https://github.com/iart-ai/explainer-video-skills) | Storyboards, diagrams, and process explanations |
| [HyperFrames Media-Use](https://github.com/heygen-com/hyperframes/blob/main/skills/media-use/SKILL.md) | Relevant free local cutout, alpha, synchronization, and edge-quality guidance |
| [Dispatching Parallel Agents](https://github.com/obra/superpowers/blob/main/skills/dispatching-parallel-agents/SKILL.md) | Independent assignments, focused briefs, and combining results |
| [Subagent-Driven Development](https://github.com/obra/superpowers/blob/main/skills/subagent-driven-development/SKILL.md) | Specialist work, review, corrections, and progress tracking |

The sources were selected for relevance. This is not a claim that each one is the highest-ranked repository.

Their guidance is adapted into this suite: upstream processing scripts, software-development workflows, incompatible crop/zoom rules, and paid-provider requirements are not dependencies. Remotion instruction prose/code was not copied where no repository license grant was found.

See [pinned revisions and integration decisions](ATTRIBUTIONS.md) and [source notices](skills/omni-edit-pro/references/source-notices.md). The project is not affiliated with the upstream maintainers.

## Validation and current limits

The instruction package has been checked for:

- All nine skill names, valid YAML metadata, and matching license files.
- Complete same-release wrapper/core dependencies and relative documentation links.
- Instruction-only contents and an intact staged copy.
- Skills CLI discovery of all nine entries.
- Written behavior for question order, presets, same-name sources, limited worker capacity, missing capabilities, failed Cutout variants, and unreviewed exports.

See [VALIDATION.md](VALIDATION.md) for the evidence and scope.

**Real-video rendering and audiovisual output quality have not yet been tested in this repository.** Package checks and instruction reviews do not prove that every host can render, that every cutout will succeed, or that every generated video will meet the visual standard. The runtime workflow requires actual preview, listening, and final-output checks before delivery.

## Project guide

| Document | Purpose |
| --- | --- |
| [INSTALL.md](INSTALL.md) | Installation, dependencies between entries, updates, and host discovery |
| [IMPLEMENTATION.md](IMPLEMENTATION.md) | Detailed design and implementation plan |
| [ATTRIBUTIONS.md](ATTRIBUTIONS.md) | Source revisions, contributions, licenses, and adaptations |
| [VALIDATION.md](VALIDATION.md) | Checks performed, requirement audit, and test limits |
| [Shared SKILL.md](skills/omni-edit-pro/SKILL.md) | Main production rules used by every entry |
| [Selection](skills/omni-edit-pro/references/selection.md) | The questions, presets, overrides, and batch choices |
| [Teams](skills/omni-edit-pro/references/batch-teams.md) | Native specialist assignments, queues, review, and recovery |
| [Styles](skills/omni-edit-pro/references/editing-styles.md) | Split, Cutout, Overlay, and framing rules |
| [Delivery](skills/omni-edit-pro/references/delivery.md) | Final folders, versions, evidence, and partial results |

The installable package is entirely under `skills/`. The shared core includes its reference documents; the other eight folders contain the main entry or presets. All required instructions travel with the installed suite.

## Frequently asked questions

**Do I need another skill for the two questions or agent teams?**

No. The question flow and delegation instructions are included. Real subagent execution still requires native support in your host.

**Can I give any number of videos?**

You can supply a batch. Each video gets its own job/team, and jobs queue within the available agent and hardware capacity. There is no promise of unlimited simultaneous processing.

**Can I install only a vertical preset?**

Install the shared `omni-edit-pro` core plus that preset from the same release. A preset alone is incomplete.

**Does All combine my videos into one video?**

No. All requests six separate versions of every source video. Combining sources requires an explicit request.

**Does the package contain Python or JavaScript editing code?**

No. It contains instructions and licenses. During an editing task, the executing agent may generate code inside the editing workspace.

**Will it work in every agent or IDE?**

Only when that host can load the instructions and provide the required execution capabilities. Skill discovery, native teams, media inspection, and rendering are separate capabilities. Consult the [compatibility guide](skills/omni-edit-pro/references/agent-compatibility.md) and verify the actual host.

**Is it free?**

The original skill material is [MIT licensed](LICENSE), and its default media workflow uses free local options. Your AI host, chosen runtime, hardware, and assets retain their own terms and costs.
