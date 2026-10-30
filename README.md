# OmniEdit Pro

**An instruction-only AI skill suite that edits from a designated sample or chooses a treatment from the source video.**

Give the main skill your footage and an editing reference for **Reference** mode. Give it footage without a reference for **Auto** mode. It inspects the media, plans a treatment, tests a representative passage, and reviews each requested export. Explicit presets and **Manual** mode remain available when you want to choose the format and composition yourself.

**Version:** 3.2.1 · **Package:** Markdown instructions and license notices · **License:** MIT

This repository supplies the workflow, not an editor application. A capable agent uses actual local media tools and may create processing code in your editing workspace. The package contains no processing scripts, model weights, media, or dependency trees. No additional skill is a mandatory runtime dependency.

## Install globally: copy and paste

Copy this entire prompt into your AI agent:

```text
Install the complete OmniEdit Pro skill suite globally for the AI agent I am
using, so it is available across my projects.

Repository: https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill

Download or clone the repository and read INSTALL.md and
skills/omni-edit-pro/references/agent-compatibility.md. Detect this agent's
supported user-level skill directory; use its documented global installation
method rather than a project-local folder. Preserve existing local changes.
When updating an earlier release, follow INSTALL.md's migration steps to retire
obsolete suite names after backing up and verifying their replacements.

Install all eight skill folders from the same repository revision as siblings:
omni-edit-pro, omni-edit-pro-all,
omni-edit-pro-horizontal-split, omni-edit-pro-horizontal-cutout,
omni-edit-pro-horizontal-overlay, omni-edit-pro-vertical-split,
omni-edit-pro-vertical-cutout, omni-edit-pro-vertical-overlay.

Include every SKILL.md, the complete shared references folder, and licenses.
Verify installed files and wrapper-to-core links. Check agent discovery where
available, and tell me the installed location, version, how to invoke
omni-edit-pro in this agent, and whether a reload is needed. Report any check
you could not perform. Install the instructions only; video tools, models and
an actual edit belong to a later video-editing request.
```

[Open the GitHub repository](https://github.com/NishidhJasani1605/OmniEdit-Pro-Video-Editing-Skill) · [Installation details](INSTALL.md) · [Agent compatibility](skills/omni-edit-pro/references/agent-compatibility.md)

Use this prompt with any agent that supports local Agent Skills and file access.
Global installation makes the suite available across projects for that agent
and user account. Other agents or devices may need their own installation;
agents without local installation support can read the workflow for planning.

## Quick start

1. Install the complete suite using [INSTALL.md](INSTALL.md).
2. Supply accessible source files and an editing workspace. Label any sample as an **editing reference**, and identify which source it applies to.
3. Select `omni-edit-pro` and use either request below, or select a direct preset.
4. The agent records input roles, permissions, output settings, and one job per source. References do not create extra edit jobs.
5. Checked exports go in **Final Output Videos**, separated by source. Failed or unreviewed candidates stay in Working Files.

**With an editing reference:**

```text
Edit my-video.mp4. Use sample.mp4 as the editing reference.
Adapt its typography, graphics, transitions and sound treatment to my content.
Keep all my dialogue. Use my Video Project folder as the workspace.
```

**Without a reference:**

```text
Edit my-video.mp4 using your best judgment. No reference.
Choose a treatment that suits the content and keep my meaning and dialogue.
Use my Video Project folder as the workspace.
```

“Best” means clear, relevant, readable, and faithful to your material. It does not promise one winning style for every genre or guaranteed virality. Actual video quality still needs audiovisual review; see [validation and limits](#validation-and-limits).

In v3.1.2, vertical/Reels presenter scenes put the real speaking video or extracted person **below**, captions in a **clear middle channel**, and the primary animation **above**, across Split, Cutout, Overlay and Adaptive. Caption headroom is measured over the speaker's movement and scales with output resolution. Added foreground graphics stay clear of the real presenter, while Cutout backgrounds can use safe transparent gaps. Meaningful graphics develop throughout the edit, with readable settled text and suitable transitions. Every source receives its own content, motion and palette decisions from actual footage; blue/navy and cloned animation templates are not automatic defaults. Explicit placement, stillness and palette instructions take priority without waiving obstruction checks.

## Modes and choices

| Mode | When it applies | What the agent does |
| --- | --- | --- |
| **Reference** | You designate a sample as an editing reference | Inspect it separately, record timecoded observations, adapt the treatment to your source, and compare a preview with relevant reference passages |
| **Auto** | No editing reference is designated and Manual is not requested | Inspect the source, choose a suitable treatment by scene, and explain the selected direction briefly |
| **Manual** | You explicitly request manual selection | Follow supplied choices; ask only for genuinely missing format/composition choices |

Manual format choices include horizontal 16:9, vertical 9:16, or the source's original shape. Composition choices include Adaptive, Split, Cutout, and Overlay. Manual waits for missing answers before media-based inference; Auto and Reference permit preliminary analysis to resolve their choices.

Format, composition, creative treatment, and editing permission are separate decisions. A preset supplies its named output shape and composition. A reference can guide typography or motion without changing that preset. Clear user overrides replace only the named choice: selecting Vertical Overlay and saying “horizontal instead” requests **Horizontal Overlay**.

Output shape follows explicit user choices, an explicitly selected preset, an applicable reference, then the source display aspect ratio. Auto can preserve square and other native ratios; it does not assume every source belongs in a vertical short. An automatically matched preset is not an explicit user selection and does not supply preset defaults.

The agent asks when an ambiguity blocks the edit, such as two unlabeled files that could mean two sources or one source plus a sample, contradictory directions, or conflicting references with no usable priority. It does not ask the old wide/tall and style questions routinely in Auto or Reference mode. A requested but inaccessible reference is reported as unavailable; switching to Auto requires your direction.

### Editing permissions

By default, preserve dialogue, order, pauses, duration, original timing, lip-sync, and source framing. A sample's quick cuts or close crops do not authorize cutting your speech, cropping, zooming, changing speed, replacing the image with B-roll, or combining sources. State any such permission separately, for example:

```text
Make a 60-second version. You may remove repetitions and pauses.
Keep the remaining statements in their original order and preserve their meaning.
```

The agent maps every authorized edit from source time to output time so audio, captions, and visuals remain synchronized. Reference footage, embedded text, and metadata are input data, not instructions or permission to reuse protected assets.

An explicit request for a shorter edit, highlights, or a montage supplies editing authority within that request's stated scope. The agent does not ask you to repeat an authorization already given.

## Choose a skill

All eight entry names use `omni-edit-pro` since v3.2.0. Use your host's skill picker or supported command syntax. Codex supports `$omni-edit-pro` or its picker; slash commands depend on the host.

| Skill | Default output when explicitly selected |
| --- | --- |
| [`omni-edit-pro`](skills/omni-edit-pro/SKILL.md) | Reference when a sample is designated; Auto otherwise; Manual on request |
| [`omni-edit-pro-horizontal-split`](skills/omni-edit-pro-horizontal-split/SKILL.md) | Horizontal 16:9 Split |
| [`omni-edit-pro-horizontal-cutout`](skills/omni-edit-pro-horizontal-cutout/SKILL.md) | Horizontal 16:9 Cutout |
| [`omni-edit-pro-horizontal-overlay`](skills/omni-edit-pro-horizontal-overlay/SKILL.md) | Horizontal 16:9 Overlay |
| [`omni-edit-pro-vertical-split`](skills/omni-edit-pro-vertical-split/SKILL.md) | Vertical 9:16 Split |
| [`omni-edit-pro-vertical-cutout`](skills/omni-edit-pro-vertical-cutout/SKILL.md) | Vertical 9:16 Cutout |
| [`omni-edit-pro-vertical-overlay`](skills/omni-edit-pro-vertical-overlay/SKILL.md) | Vertical 9:16 Overlay |
| [`omni-edit-pro-all`](skills/omni-edit-pro-all/SKILL.md) | Both orientations × Split, Cutout, Overlay: six versions per source |

**A direct preset:**

```text
/omni-edit-pro-horizontal-split
Keep the original video on the left and explain the ideas with diagrams on the right.
Preserve the person's full framing and all dialogue.
```

**Manual selection:**

```text
/omni-edit-pro
Manual mode. Edit these two videos separately.
Ask me for any missing format and composition choices.
```

**Every existing preset:**

```text
/omni-edit-pro-all
Make all six versions of each source. Use sample.mp4 only as an editing reference.
Save checked exports in Final Output Videos.
```

Two sources plus one reference request **12**, not 18, exports in unrestricted All mode. “All, horizontal only” requests three per source, so six total for two sources. All never adds Adaptive automatically and does not combine your sources. Clear narrowing or overrides change the requested set; jobs record that set before work begins.

## Composition and automatic direction

| Composition | Contract |
| --- | --- |
| **Split** | Fit the complete original source and its background into a dedicated region. For vertical presenter scenes, source below and primary animation above; horizontal uses a suitable left/right arrangement. |
| **Cutout** | Isolate the real moving presenter with actual alpha. For vertical scenes, place the unboxed silhouette below the main animation over a full-canvas dynamic background. Protect face, hair, hands, movement and temporal edges. |
| **Overlay** | Keep the complete original footage and background together. For vertical presenter scenes, fit this intact source below and put primary animation above, even when the source is already 9:16. |
| **Adaptive** | In the main workflow, choose layouts from actual scenes and permissions. Vertical presenter scenes use intact source/background below and primary animation above by default; non-presenter scenes use suitable source-native or scene-specific layouts. |

The portrait ordering applies only when a real presenter is present and does not invent one for other footage. It does not force horizontal speakers below. An explicit placement instruction wins; an incompatible reference is adapted and the deviation recorded. Region sizes follow framing, gestures and readability, without a compulsory 50/50 split. A format change may require padding or a smaller fitted image; simplify graphics and enlarge the source region to protect detail. Report any remaining incompatible constraints.

Cutout protects the actual moving silhouette with a justified small margin, rather than reserving its entire rectangular bounding box. The full-canvas background can animate behind the person and through transparent gaps between an arm and torso or beside the head. Essential text stays readable across the whole gesture. Do not add a visible backing panel or reserve an invisible rectangular exclusion zone. Adaptive is not a seventh All preset. See [styles and framing](skills/omni-edit-pro/references/editing-styles.md).

Without a reference, the agent examines actual frames and audio before choosing:

| Observed content | Starting treatment |
| --- | --- |
| Lesson or explanation | Diagrams and phrase emphasis tied to ideas; preserve explanation time |
| Interview or documentary | Restrained identifiers and context; protect answers, reactions, and meaning |
| Screen or product demonstration | Protect interface text, cursor, and important actions; use readable callouts |
| Travel, action, sport, gaming, or music-led footage | Follow shot relationships, movement, and sound; montage requires cutting/combining permission |
| Fiction, performance, or an already polished edit | Preserve dramatic timing and intentional quiet; make selective improvements |
| Mixed or uncertain material | Plan by segment, record uncertainty, and choose a conservative treatment |

Silent footage does not receive an invented transcript or a compulsory presenter cutout. A genre label is a planning aid, not proof that an effect is appropriate. See [automatic direction](skills/omni-edit-pro/references/auto-direction.md).

Across all compositions and output shapes, explanations evolve from opening through ending through meaningful diagram development, active highlights, mechanisms or other source-grounded graphics and transitions. Labels settle for reading while useful visual elements progress. Quiet material can use restrained motion and justified short reading holds; long frozen cards with only entrance/exit fades, constant text jitter and decorative pulsing do not meet the default. This motion requirement grants no authority to cut, crop, zoom or retime the source. An explicit stillness instruction is honored and recorded.

Every batch source is inspected and directed independently for topic, scenes, subject/clothing, lighting, changing backgrounds and contrast. Its visual metaphors, motion and transitions must explain its own material. Palette choices use that evidence and applicable reference or brand instructions; blue remains valid when supported. Variants of one source may share a coherent treatment, and a batch may retain requested brand consistency, while each source still receives semantic planning and contrast review. See [visual planning](skills/omni-edit-pro/references/visual-planning.md) and [motion design](skills/omni-edit-pro/references/motion-design.md).

## How reference editing works

The agent first separates source, reference, and supporting-asset roles and maps each reference to its target. It inspects source and reference independently. A broad contact sheet is followed by denser inspection and playback of openings, endings, changing layouts, and short events; sparse thumbnails alone cannot establish motion or sound behavior.

The reference profile records timecoded evidence for layout, caption hierarchy, graphic density, shot rhythm, motion, transitions, color, and audible treatment. Findings are labeled **measured**, **inferred**, or **unknown**, with confidence. A finished video does not reveal exact original settings, and a spectrogram alone cannot identify a sound effect with certainty.

The agent turns observations into rules that suit your source. It adapts timing to your words and scenes instead of copying sample event times. A representative test passage includes the densest or hardest relevant effect; the reviewer compares it at delivery size with audio, records similarities and intentional deviations, and repairs concrete defects before the full edit. A successful short preview establishes that passage only.

For multiple references, you can specify “captions from A, pacing from B.” A designated primary resolves unspecified attributes; material conflicts without a priority require clarification. Reference style does not grant rights to its music, logos, footage, or artwork. Use cleared assets or original equivalents. See [reference analysis](skills/omni-edit-pro/references/reference-analysis.md).

## Teams, tools, and quality

Each source receives a unique ID, isolated working paths, one timeline owner, and real specialist assignments for source/speech analysis, creative direction, assets, composition/animation, optional Cutout, audio/export, and independent review. Reference observations may be shared read-only across source jobs. Native host agent tools provide the actual workers; jobs queue within available agent and hardware capacity. A host without subagents must disclose that limitation and resolve the execution choice before a solo fallback. See [per-video teams](skills/omni-edit-pro/references/batch-teams.md).

Every source has a dedicated independent **Production Video Reviewer**, separate from the editor, with authority to reject any known defect, including cosmetic defects and one-frame mistakes. The reviewer checks each requested variant's complete actual export, every text occurrence and animation state, and source preservation, sync, motion, sound and technical integrity. Repairs require inspection of the revised full export; approval of an earlier version or a short preview does not carry over. Missing review evidence and unresolved issues keep a candidate out of Final Output Videos. See the [reviewer contract](skills/omni-edit-pro/references/video-reviewer.md).

Seven production requirements cover the reported defects:

1. **Presenter clearance:** place upper-channel captions at least 200 pixels above the highest forehead position on a 1920-pixel-high output, scaling that distance with resolution and aiming for 250 scaled pixels where feasible. Measure the complete caption/plate footprint; fixed Y coordinates and a universal 60/40 split are not accepted substitutes.
2. **Stable captions:** use complete semantic phrases at a consistent anchor, with no moving word window, sentence bleed, reflow or ghosted phrase transition. Only verified active-word color changes; yellow `#FDE047` is the default when contrast and brand requirements permit.
3. **Padded backgrounds:** measure actual glyph bounds and wrap complete text within safe width, with sufficient scaled padding through every animation state.
4. **Centered headings:** center banner/title/CTA content from measured visible bounds, including bearings and multiline layout, rather than guessed offsets. Preserve intentional body-text and explicit user alignments.
5. **Sharp graphics and export:** render graphics at 2× resolution and downsample carefully, or document an evidenced equivalent. Inspect text in the decoded delivery file for jagged edges, blur, ringing, chroma bleed and compression damage; a codec preset alone cannot pass this check.
6. **Verified wording:** check names, credentials, venues, landmarks and event date/time details against matching evidence. ASR is a draft, and prior projects' glossaries or dates never verify a new event.
7. **Original audio and sync:** preserve speech, pauses and source timing under the recorded edit permissions; select source streams explicitly and verify the final mux. Streamcopy and lossy AAC re-encoding are different operations and must be described accurately.

After each render, the reviewer inspects timecoded verification frames and detailed text crops, full normal-speed playback and applicable listening. It logs every defect, returns repairs to the owning specialist, and checks the revised complete export and fresh evidence before release. Missing capability remains needs-review. See [layout rules](skills/omni-edit-pro/references/layouts-effects.md), [transcription verification](skills/omni-edit-pro/references/transcription-sync.md), [rendering](skills/omni-edit-pro/references/audio-rendering.md) and the [reviewer contract](skills/omni-edit-pro/references/video-reviewer.md).

The default workflow uses free local processing: FFmpeg/FFprobe, an available compositor, and suitable local transcription or matting where needed. Remotion is optional when its actual terms permit the intended use without payment; a capable local alternative is allowed. Tool setup happens for an authorized editing job, not during skill installation. There is no automatic paid or hosted fallback. Your AI host, runtime tools, models, fonts, and media retain their own terms.

Animations must explain the actual material, remain readable, and protect people, essential gestures, interface details, existing text, and captions. Charts need real values; measurement-like waveforms need real audio. Local Cutout tests a difficult passage before full processing. Failed Cutout variants remain incomplete while independent Split/Overlay work continues. See [environment](skills/omni-edit-pro/references/environment.md), [local Cutout](skills/omni-edit-pro/references/local-cutout.md), and [quality assurance](skills/omni-edit-pro/references/quality-assurance.md).

## Final output folders

```text
<editing-workspace>/
├── Final Output Videos/
│   ├── video-001-interview/
│   │   └── ...checked, versioned exports
│   └── video-002-demo/
│       └── ...checked, versioned exports
└── Working Files/
    ├── batch-progress.md
    ├── reference-analysis/
    └── video-001-interview/
        ├── plan.md
        ├── source-analysis/
        ├── assets/
        ├── project/
        ├── previews/
        ├── candidate-exports/
        └── review/
```

Only reviewed candidates are promoted to **Final Output Videos**. Missing audiovisual review means **needs review**, not complete. Preserve earlier finals. Each delivery row identifies the requested variant, status, path if available, dimensions, frame rate, duration, actual checks, reference deviations, and limitations. Working captions, projects, credits, and review evidence are linked separately. Editing does not publish or upload videos. See [delivery](skills/omni-edit-pro/references/delivery.md).

## Install and update

Use the [copy-and-paste global installation prompt](#install-globally-copy-and-paste) above for installation from GitHub. The complete package has eight entries, 20 shared references and 36 Markdown/license files. For updates, preserve local edits and install the core and wrappers together from one reviewed revision. Follow [INSTALL.md](INSTALL.md) for manual copying, migration and verification.

Manual copying needs no Node.js or Python. From a reviewed local checkout, an optional Skills CLI command for a verified Codex target is:

```sh
npx skills add . --global --agent codex --skill omni-edit-pro omni-edit-pro-horizontal-split omni-edit-pro-horizontal-cutout omni-edit-pro-horizontal-overlay omni-edit-pro-vertical-split omni-edit-pro-vertical-cutout omni-edit-pro-vertical-overlay omni-edit-pro-all
```

Verify the selected revision and CLI/runtime requirements. Use `npx.cmd` in PowerShell if script policy blocks `npx.ps1`. A smaller installation must include the shared core plus each chosen wrapper. See [installation and migration](INSTALL.md) and [host compatibility](skills/omni-edit-pro/references/agent-compatibility.md).

**Migrating from before v3.2.0:** every command now uses the `omni-edit-pro` order. The main entry and shared core are one folder, so the suite has eight unique entries rather than nine. Back up existing installations, migrate local edits, replace the former preset folders with the names above, and remove obsolete suite entries from active discovery after verifying the replacement. All editing modes, presets, quality rules and output counts remain available. See [migration instructions](INSTALL.md#migrate-from-earlier-releases).

Earlier behavior changes are retained:

**From v2:** the main entry no longer requires two selection answers before inspecting media. Select Manual to retain question-led selection, or use an explicit preset for stable format/composition defaults. Update core and wrappers together; never mix releases.

**From v3.0:** Reference/Auto/Manual routing and All's six default variants stay available. The v3.1 portrait placement, full-duration motion, Cutout negative-space use and per-source art direction are retained. Explicit placement, stillness and palette overrides remain authoritative. Use the current command names above.

**From v3.1.0:** retain the complete core and wrappers, including `references/video-reviewer.md`. Version 3.1.1 introduced middle-channel captions, every-frame face clearance, padded text containment, evidence-backed spelling and independent zero-known-defect release review. These rules remain mandatory.

**From v3.1.1:** stable phrase captions, scaled headroom, measured heading centering, sharpness/encoding evidence and explicit post-render repair checks introduced in v3.1.2 remain mandatory.

## Sources and validation

The v2 foundation adapted guidance from nine repositories with ten selected source entries, including two Superpowers delegation skills. The v3 research inspected official Remotion guidance and the Melvynx `steal` reference workflow on **2026-10-27**. Remotion remains optional implementation guidance; `steal` informed measurement ideas and is not an installation recommendation. Their reachable dependencies were not fully audited or trialed. Source choices do not prove superior video quality. See [attributions and bounded research](ATTRIBUTIONS.md) and [source notices](skills/omni-edit-pro/references/source-notices.md).

The five discovery/authoring roles—`find-skills`, `agent-skill-stack`, `anthropic-skill-creator`, `reverse-engineer-anything`, and `arena`—helped research, inspect, compare, or author the revision. They are not required for each video edit. [IMPLEMENTATION.md](IMPLEMENTATION.md) explains their roles.

## Validation and limits

Historical v2 checks covered nine entries, same-release links, installation staging, CLI discovery, and instruction dry runs. The v3.0 audit reproduced the old question gate in paper scenarios, and four modification proposals competed through two Arena rounds; proposal a002 won the independently judged final **95.5 to 90.5**. Those scores assess the proposal, not rendered videos.

**Historical v3.0 checks:** nine discovered entries, matching 3.0.0 metadata/licenses, 147 relative file links and a matching staged copy containing only Markdown and licenses. In three paired paper scenarios, independent grading recorded v3.0 **15/15** instruction checks and v2 **10/15**; a separate adversarial review found and closed a narrowed-All counting inconsistency. A small synthetic render/decode check exercised local tools outside this repository. These results do not certify the v3.1 changes.

**Historical v3.1.0 checks:** nine discovered entries at 3.1.0, 37 Markdown/license files, 174 resolved file links, two heading links, matching licenses and a byte-identical staged copy. Seven paired paper scenarios initially recorded 26/28 checks for that draft versus 16/28 for 3.0; two planning omissions were repaired and both affected cases passed focused retests (8/8). The original failures remain recorded separately. Independent source review found no standing substantive contradictions in that version. These counts and results do not certify v3.1.1.

Historical v3.1.1 and v3.1.2 package, scenario and installed-copy checks are recorded separately in [VALIDATION.md](VALIDATION.md). Current v3.2.1 adds small speech/action-anchored graphic reveals, explicit eased handoffs and content-sized panels selected from measured clear space. Detailed explanations use a fitting primary region; narrow regions use useful keywords/symbols or remain clear. These shared rules apply to all presets and Adaptive. See the current evidence section in [VALIDATION.md](VALIDATION.md) for checks and limitations. **No actual user-supplied video has been edited or fully reviewed during authoring.** Strict written rules and zero known defects at release do not guarantee that an unobserved defect cannot exist. Caption stability, geometry, spelling, badge fit, text sharpness, reference fidelity, matte quality, useful motion and audio fidelity require actual output review for each later video.

## Project guide

| Document | Purpose |
| --- | --- |
| [INSTALL.md](INSTALL.md) | Same-release installation, updates, migration, and host discovery |
| [IMPLEMENTATION.md](IMPLEMENTATION.md) | v3.2.1 design, execution contract, and authoring roles |
| [ATTRIBUTIONS.md](ATTRIBUTIONS.md) | Pinned sources, rights findings, and research boundaries |
| [VALIDATION.md](VALIDATION.md) | Historical evidence, current checks, and unrun media tests |
| [Shared SKILL.md](skills/omni-edit-pro/SKILL.md) | Production instructions used by every entry |
| [Selection](skills/omni-edit-pro/references/selection.md) | Modes, input roles, permissions, presets, and overrides |
| [Production Video Reviewer](skills/omni-edit-pro/references/video-reviewer.md) | Independent full-export review, defect repair and release decisions |

The complete installable package lives under `skills/`. All required instructions travel with the selected same-release entries. The project is [MIT licensed](LICENSE) and is not affiliated with upstream maintainers.
