# Sources and integration decisions — v3.0.0

The v2 foundation used nine unique repositories inspected on 24 October 2026. The two requested Superpowers skills share one repository, giving ten historical source-list entries. A bounded v3 source inspection followed on **2026-10-27**, described separately below. These are relevance-based selections, not a highest-stars ranking or an endorsement by upstream authors.

The source checkouts were kept outside the distributed project. No upstream scripts were executed and no source repository is a runtime dependency. The package contains original, adapted Markdown guidance, not upstream applications, code templates, models or media.

## Historical foundation: inspected revisions

| Repository and pinned revision | Material reviewed | Contribution to this suite | Rights found |
| --- | --- | --- | --- |
| [Official Remotion Skills](https://github.com/remotion-dev/skills/tree/6c67adcd9cdbe6eb84d76342da89b225f9161cb2) | Composition, captions, media and render guidance | Technical principles; independently written instructions, no upstream prose/code copied | No explicit repository license grant found |
| [iArt Motion Design Skills](https://github.com/iart-ai/motion-design-skills/tree/3c129f769d90a1328c209c386492333c9ac62312) | Art direction, animation principles, composition and color | Consistent design, smooth entrances/holds/exits and readable hierarchy | MIT; 2026 iart.ai |
| [iArt Talking-Head B-roll](https://github.com/iart-ai/b-roll-skills/tree/a51e34b0a8def533759373733bde1869c21075fb) | talking-head-b-roll | Meaning-based cues, continuous original narration and face-safe visuals | MIT; 2026 iart.ai |
| [AI Self-Media Video Packaging](https://github.com/zhouyuechuan2025-ui/ai-self-media-video-packaging-skill/tree/cfbb87843c746ceee18e8ae7c855ba536a6f32f2) | Root skill and public-lite, director, motion and quality references | Presenter/explanation layouts, cards, flows and illustrations | MIT; 2026 Nana AI; separate third-party NOTICE |
| [iArt TikTok Video Skills](https://github.com/iart-ai/tiktok-video-skills/tree/2a775336b5a638cbf8a61dbd785f9a1b649be016) | Caption animation, lower thirds and short-form presentation | Vertical reflow, readable captions and relevant early visual context | MIT; 2026 iart.ai |
| [iArt Kinetic Typography Skills](https://github.com/iart-ai/kinetic-typography-skills/tree/fccc94bd325d824235ee9e715e65abde57b6513a) | Kinetic typography and reveal recipes | Speech-matched keyword emphasis and phrase animation | MIT; 2026 iart.ai |
| [iArt Explainer Video Skills](https://github.com/iart-ai/explainer-video-skills/tree/3e2d411b725d9a72939cf8e5eb81579e751373e7) | Explainer, diagram and whiteboard skills/references | Storyboard from the actual narration; reveal entities, actions and results at meaningful cues | MIT; 2026 iart.ai |
| [HyperFrames Media-Use](https://github.com/heygen-com/hyperframes/tree/234b87a4bbbde51100005c7be013f0f052339dde) | skills/media-use/SKILL.md and audio/references/remove-background.md | Local cutout concepts, alpha/RGB quality, synchronization and edge checks | Apache-2.0; reference only, no upstream code/prose copied |
| [Superpowers: both requested skills](https://github.com/obra/superpowers/tree/2ce8aa15d05bd57213e6f746f953aafb7ded7a8b) | dispatching-parallel-agents and subagent-driven-development | Independent scoped assignments, ownership, integration and separate review/repair | MIT; 2025 Jesse Vincent |

The two delegation sources are [Dispatching Parallel Agents](https://github.com/obra/superpowers/blob/2ce8aa15d05bd57213e6f746f953aafb7ded7a8b/skills/dispatching-parallel-agents/SKILL.md) and [Subagent-Driven Development](https://github.com/obra/superpowers/blob/2ce8aa15d05bd57213e6f746f953aafb7ded7a8b/skills/subagent-driven-development/SKILL.md). Their principles are adapted in [Per-video teams](skills/omni-edit-pro/references/batch-teams.md). No additional orchestrator, software-development helper script or mandatory sibling skill is required.

## Adaptations and exclusions

- **Remotion:** independently describe composition/timing invariants and link official API documentation. Do not copy unlicensed skill prose/code. Prefer Remotion only when free for the intended use; allow a capable free local alternative.
- **Motion and B-roll:** use readable animation and reviewed spoken meaning. Do not force effects every few seconds, use arbitrary lead offsets, crop the presenter, or disrupt original narration.
- **Self-media:** its public-lite 16:9 title/card/flow layouts are references, not the same as OmniEdit's Split/Cutout/Overlay modes. Portrait reflow and the three modes are original suite instructions. Reject its crop/zoom assumptions and unrelated approval gates.
- **Social and typography:** use real transcript timing, readable phrase hierarchy and clean lower thirds. Exclude compulsory jump cuts, pause removal, punch-ins, regenerated speech, artificial loops and paid transcription. Do not copy sample code with timing-coordinate mistakes or browser-time animation.
- **Explainers:** build diagrams from the existing words, revealing relationships when spoken. Do not invent numerical claims or rewrite narration to fit a template.
- **HyperFrames:** its local background-removal reference distinguishes segmentation quality from encoding quality and supports alpha intermediates. Use those principles without requiring its compositor or paid media providers. Free local matting is a runtime option, never a guarantee of perfect edges.
- **Superpowers:** keep scoped assignments, independent parallel work, review and repair. Replace software implementation/test/Git instructions with video-specific evidence and QA. Use actual host-native agents, queue within capacity, and do not fabricate a team when the host lacks support.

The v3 Auto/Reference/Manual routing, role/reference maps, explicit permission records, Adaptive composition, preset matrix, unique source identities, six-variant accounting, source-framing protection, and checked-only Final Output Videos promotion rule are maintained directly in this suite. The v2 compulsory-question gate is replaced; Manual retains questions for missing choices. No separate third-party skill is needed for these behaviors.

## Bounded v3 source inspection — 2026-10-27

This inspection compared possible helpers with the requested reference-conditioned and no-reference workflow. It read the current top-level candidate instructions and selected supporting files. It did not execute candidate code, install the candidates, upload media, run a local trial, or complete a dependency audit. Search/registry adoption signals informed discovery only and do not establish safety, compatibility, or editing quality. Public documentation does not require the private research workspace to remain in this repository.

| Candidate and inspected source | Assessment and integration decision |
| --- | --- |
| [Official Remotion guidance at 30d4553](https://github.com/remotion-dev/skills/blob/30d4553ecd46fbc5212fd0ff006ae43af522158b/skills/remotion-best-practices/SKILL.md) | The inspected `remotion-best-practices` 4.0.539 routes to specialized composition/media guides. Optional implementation guidance, not a verified creative director or reference analyzer. Its preview-first default must be scoped so OmniEdit's requested final exports are still delivered. Reachable assets/dependencies were not exhaustively inspected; no local trial was run and current rights need checking before any incorporation. No upstream prose/code is copied. |
| [Melvynx `steal` at 4774fa4](https://github.com/Melvynx/video-agent-skills/blob/4774fa4f2601baa822fd513387202c26e4587902/skills/steal/SKILL.md) | Research inspiration for contact sheets, cut rhythm, sound/framing observations, a human-readable profile, and a comparison edit. Its engine-specific data and portrait assumptions are not OmniEdit contracts. Online download, dynamic-service, paid audio, and sibling-skill branches require separate review. Dependencies were not fully audited and no local trial was run. No installation recommendation or mandatory dependency; no upstream implementation is imported. |

The current Melvynx skill is `steal`; the older `video-steal` registry entry describes a different historical workflow. The inspected [supporting lessons](https://github.com/Melvynx/video-agent-skills/blob/4774fa4f2601baa822fd513387202c26e4587902/skills/steal/references/learnings.md) contain creator-specific preferences that can conflict with matching a reference's audible treatment. OmniEdit uses evidence and the user's constraints instead of adopting those preferences as universal rules. Registry badges alone were not treated as a safety verdict.

The measurement limitations are our assessment: sparse contact sheets can miss brief events; scene thresholds need visual confirmation; spectrogram appearance does not establish exact sound identity; and a finished reference does not expose its original settings. OmniEdit therefore separates measured observations, inferences, unknowns, confidence, and intentional adaptations.

Optional underlying tools may help execution without adding more skill coordinators: [PySceneDetect's official documentation](https://www.scenedetect.com/docs/latest/) covers scene detection and scene/frame outputs; [faster-whisper's official repository](https://github.com/SYSTRAN/faster-whisper) describes local speech transcription, word timestamps, and optional voice-activity filtering. Scene candidates and transcript timing still need review. Existing equivalents can be reused. Neither tool was installed or trialed in this bounded inspection.

## Research and authoring helpers

`find-skills` supported discovery; `agent-skill-stack` assessed fit, overlap, and conflicts; `anthropic-skill-creator` supplied the baseline/comparison/revision method; `reverse-engineer-anything` routed readable source instructions to ordinary inspection rather than video-style extraction; `arena` compared four alternative proposals through two judged rounds. They are improvement-time roles, not runtime dependencies or evidence of real-video performance. See [IMPLEMENTATION.md](IMPLEMENTATION.md) and [VALIDATION.md](VALIDATION.md).

## Attribution and separate rights

MIT source notices are retained in [source notices](skills/omni-edit-pro/references/source-notices.md). The project's [MIT license](LICENSE) covers its original material; a copy travels in each installable entry. Upstream model/tool/media terms are separate.

Historical v1 research also consulted [gitethanwoo/video-editing at 166eed9b1f391af5201a37057924593bf8f413d4](https://github.com/gitethanwoo/video-editing/tree/166eed9b1f391af5201a37057924593bf8f413d4), MIT, copyright 2026 Ethan Woo, for asset provenance and quality checks. Its NOTICE credits Louise De Sadeleer's B-Roll Finder. This historical acknowledgment does not add a tenth downloaded repository to the v2 list.

No repository license licenses third-party stock, music, fonts, model weights or supplied footage. Inspect the actual selected runtime/asset terms at use time. This project is not affiliated with the upstream maintainers.
