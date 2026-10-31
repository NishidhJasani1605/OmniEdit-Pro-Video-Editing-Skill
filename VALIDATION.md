# Validation evidence — OmniEdit Pro 3.3.0

This document separates historical package checks, v3 instruction tests, a bounded synthetic media check, and future media benchmarks. **No actual user-supplied source video has been edited or rendered during this authoring task.** Instruction tests and proposal scores cannot establish audiovisual quality or reference fidelity.

## Current 3.3.0 automatic discovery and still-first revision

This revision adds automatic video role/format classification, reference-matched separate stacked cards, measured progressive scrim falloff with protected presenter illumination, horizontal full-canvas captions, scaled portrait stack spacing and the mandatory pre-render still-frame audit. All eight entries use 3.3.0 and load the shared rules. Existing source preservation, small semantic reveals, stable captions, moving-subject safety, MIT notices and full-export review remain applicable.

### Baseline and checks

- **Untouched baseline:** commit `b1cff16edc98f6d2e859a34614fd731cd3381200` (3.2.1). A fresh-context read-only evaluator applied five hypothetical planning scenarios before edits. It found that unlabeled media could require role clarification or become three targets; separate concept containers were not mandatory; scrim falloff and horizontal full-canvas centering lacked explicit contracts; and full-candidate verification PNGs were post-encode rather than a still-first gate. Existing presenter-shadow protection and the scaled 200px portrait minimum already rejected those defects, and are retained controls rather than claimed new gains.
- **Package checks:** all eight entries passed the skill validator at 3.3.0. The suite retains 36 Markdown/license files and 20 shared references. Frontmatter names/versions, MIT license bytes, relative file/heading links, Markdown fences and whitespace passed. No processing code, dependency trees or media were added.
- **Independent revised instruction test:** a separate fresh-context evaluator read the revised core and relevant references without this validation report or the objective attachment. In the same five scenario families it selected one source/two reference-format outputs without role questions, rejected the merged card, required smooth scrim falloff with no coat shadow, centered horizontal captions at the full-canvas midpoints, and required still audit/repair before full rendering. It correctly scaled portrait gaps, marked an absent event scene inapplicable, invalidated still approval after font changes, preserved explicit source/preset/narrowed-All choices and kept an uninspectable gate needs-review. This was one planning response per version, not repeated-run reliability or media QA. A subsequent author audit separated pre-render composition/still identity from post-render encoded-file identity to avoid requiring an unavailable full candidate before the still gate. The independent evaluator then re-read the revised handoff, gate, workflow and render instructions; its focused follow-up found no remaining circular dependency, stale/uninspected-gate bypass or loss of post-render review requirements.
- **Numerical/synthetic compositing checks:** the documented multi-stop ramp was evaluated for 1920px and 3840px canvases, including a shoulder moved from X900 to X700 on a 1920px canvas. Terminal zero moved from X806.4 to X673; opacity stayed bounded/monotone with a smooth endpoint, and in-memory RGB comparisons found no scrim-induced change in the protected synthetic presenter region. A hard-cutoff ramp and a scrim crossing the earlier shoulder failed the corresponding properties. These are synthetic formula/compositing checks, not a real-video illumination pass.
- **Caption and portrait calculations:** full-canvas caption midpoints checked at X640/X960/X1920 for widths1280/1920/3840. A three-card stack and its card/caption/forehead gaps were checked at heights1280/1920/3840. The 12px card-gap, exactly100px card/caption-gap and 180px forehead-gap controls were rejected against the scaled contract. These calculations validate examples, not actual fonts, gesture tracking or exported frames.

The new scenarios and required decisions are maintained in [Evaluation](skills/omni-edit-pro/references/evaluation.md#v33-automatic-discovery-multi-box-scrim-and-still-first-regressions). Instruction evaluation and synthetic arithmetic do not certify perceived motion, audio, exact source classification on all footage or future video quality. Every later job must perform the new still audit and all existing preview/full-export reviews on its actual artifacts. No new edit of user footage or full rendered-media benchmark was run for this revision. The changes are repository authoring work; no global installation, commit or GitHub publication is part of this revision request.

## Historical 3.2.1 motion and space revision — 2026-10-30

This revision changes the shared production instructions, not the package's eight-entry structure. It requires small speech/action-anchored explanatory units, explicit eased property endpoints and handoffs, and content-sized panels selected from measured clear regions. Caption phrase stability, portrait ordering, Cutout alpha-space rules, source preservation and per-variant production review remain in force. The new requirements are carried into planning, specialist handoffs, review and release gates.

### Evidence and scope

- **Baseline inspection:** commit `c0f201aada99a2e174f4eac80f6dfdb953095d22` already required meaningful progression, safe moving-person placement and measured text containment. It permitted active highlights as graphic development and lacked an explicit per-unit visibility ledger, same-slot handoff recipe and primary-description/compact-cue allocation procedure. Existing clipping/collision prohibitions are retained safeguards, not claimed new discoveries. An attempted independent baseline scenario agent ended with a host usage-limit error; no result or score is attributed to it.
- **Read-only reference inspection:** two supplied images were viewed in place. Video metadata, duration-wide sampled frames and adjacent frames around an entrance were inspected through in-memory decoding. They support the staged-card and asymmetric-space design interpretation. No reference media, thumbnails, extracted audio, transcript, identities or attachment paths were added to this package or saved as authoring fixtures. Full normal-speed playback/listening and exact recovered easing were not established; the ramp in the skill is an implementation choice.
- **Package checks:** all eight entry points passed the skill validator at version 3.2.1. The suite retains 36 Markdown/license files and 20 shared references. Names, same-release wrapper dependencies, license bytes, local links/anchors, closed fences and whitespace were checked. These checks validate packaging, not aesthetic quality.
- **Numerical checks:** the documented ramp was evaluated at 24, 25, 30 and 60 fps for four durations (16 combinations); endpoints, clamping, monotonicity and bounded opacity passed. The 30fps example was checked for no early second-unit visibility or same-slot prose overlap, and a zero-opacity outgoing endpoint. These calculations validate the example's timing arithmetic, not an executed editor or perceived smoothness.
- **Geometry checks:** synthetic 734×520 and 274×520 regions were checked with detailed 600×420 and compact 180×80 content plus travel. Detailed content fits only the wide region; compact content can fit the narrow region. A narrow-only description and a hold that fits but whose entrance leaves the region were rejected. The clearance calculation was checked for landscape, portrait and square dimensions. Actual font metrics and moving-subject footage must still be measured on each production job.
- **Contract review:** the [regression cases](skills/omni-edit-pro/references/evaluation.md#progressive-reveals-smooth-handoffs-and-available-space-regressions) were traced manually through the new timing, fit and review procedures, including mirrored space, changing gestures, portrait/alpha constraints, long text, fast speech, silent interfaces and view-only references. This is an author review, not independent agent compliance, repeated fresh-context trials or a rendered-media benchmark.
- **Installed copy:** all eight installed 3.2.0 entries were compared with the baseline before replacement; no content customizations or extra files were found. All 36 instruction/license files were backed up outside discovery, updated to 3.2.1, and verified byte-for-byte against the repository suite. No media was part of that backup or installation. Host UI reload/runtime discovery was not tested.

No new edited video or production export was requested or produced. Independent revised-agent tests and full audiovisual comparisons remain **not run**. Written release checks and the tested numerical examples do not establish universal defect-free output; each later candidate still needs the actual full-output review and repair loop. This revision does not publish the repository or certify a live host reload.

## Historical 3.2.0 naming revision — 2026-10-29

The main command and every preset now use the `omni-edit-pro` word order. The existing shared core is the main entry, and the former duplicate generic wrapper is merged into it. The current suite has eight unique entries: main/core, six orientation/composition presets and All. There are twenty shared references and thirty-six Markdown/license files. This changes naming and installation structure, not editing behavior or the number of video outputs.

The pre-change 3.1.2 package at commit `602c751` had mixed naming: the shared core used the intended word order, while the separate generic wrapper and seven presets used the reversed order. The generic wrapper delegated to that same core without a unique fixed composition or output set. Manual inspection confirmed that the core already implements Reference, Auto, Manual, Adaptive, source preservation, the seven production requirements and independent review. Consolidating the duplicate therefore retains those behaviors. An attempted delegated baseline audit failed because of a host usage limit; no independent-agent result is claimed for this rename.

Naming and migration checks for this revision:

- The expected entry set is exactly `omni-edit-pro`, `omni-edit-pro-all` and the six `omni-edit-pro-<orientation>-<composition>` presets. Frontmatter names match their folders, every entry uses 3.2.0, each license matches the repository license, and all seven presets resolve the shared core.
- The renamed preset instruction bodies match the prior committed bodies exactly after substituting the command prefix and release version. Selection routes retain the same generic, direct-preset and narrowed-All output sets. The main/core consolidation changes its introduction, not its production rules.
- The suite contains thirty-six instruction/license files and twenty shared references. Repository Markdown links/anchors/fences, install-command uniqueness and whitespace checks pass. No reversed-order command remains in current repository Markdown or active suite folder names. Historical counts below remain attached to their actual older releases.
- The installed 3.1.2 suite was compared with commit `602c751` before replacement; no content customization or inventory difference was found. Its thirty-eight files were backed up to `C:/Users/nishi/.codex/skill-backups/omni-edit-pro-20261029-v3.1.2-before-v3.2.0`. The eight obsolete active folders were verified against that backup, then moved into its `retired-active-folders` subfolder outside discovery. The new eight-entry installation matches all thirty-six repository files byte-for-byte and exposes only the intended namespace on disk.

No actual video processing is part of this naming update. Host UI refresh and runtime invocation were not tested; filesystem and frontmatter checks cannot prove that an already-open host has refreshed its discovery list. Publication is verified separately through Git remote state when pushed.

## Historical 3.1.2 changes — 2026-10-29

This update adds the new reported failure cases to the shared production contract: moving-window caption jitter and sentence bleed, highlight-induced text reflow, off-center headings, jagged/compressed typography, measured portrait headroom, and ambiguous audio-preservation claims. The seven requirements and autonomous post-render evidence/repair loop are instructions for later edits. They cannot guarantee that no future video will contain an undiscovered defect. No source video was processed or rendered for this authoring task; the supplied incident summary is reported history, not a newly inspected media result.

### Baseline and technical verification

A read-only evaluator inspected the installed 3.1.1 suite before replacement. It found existing generic protections for readable captions, safe moving-face placement, font measurement, original timing and independent zero-open-defect review. It did not find explicit requirements for no sliding windows, fixed color-only highlight geometry, measured heading centering, 2x graphics or decoded-encode edge comparison. Its proposed fixes were partly professional judgment rather than instructions already present. This distinguishes retained safeguards from actual guidance gaps.

Primary-source research corrected several proposed implementation claims before they entered the skill. Pillow's Lanczos implementation uses support 3, not a 36-lobe filter; font advance length does not include every visible overhang and therefore cannot alone establish badge containment or visible centering. See [Pillow resampling implementation](https://github.com/python-pillow/Pillow/blob/main/src/libImaging/Resample.c) and [font measurement documentation](https://pillow.readthedocs.io/en/stable/reference/ImageFont.html). FFmpeg streamcopy avoids re-encoding; AAC 256 kb/s is an encode and is not bit-identical preservation. In normal single-pass libx264, explicit CRF selects quality mode, so an added bitrate is not an 8 Mb/s floor; destination-specific limits still need review. See [FFmpeg streamcopy](https://ffmpeg.org/ffmpeg.html#Streamcopy), [libx264 implementation](https://github.com/FFmpeg/FFmpeg/blob/master/libavcodec/libx264.c) and [scaler options](https://ffmpeg.org/ffmpeg-scaler.html). No particular filter, AQ setting or bitrate was treated as proof of sharpness.

### Revised instruction tests and repair

A fresh-context evaluator read the revised core and relevant references without the validation report or other agents' answers. It resolved a hypothetical 30-second clip with sliding captions, split abbreviations, font-weight reflow, copied coordinates, italic headings, entrance-only badge fit, jagged text, copied encode/audio settings, stale event details and a proposed still-only release. Its observed decisions were:

- Replace rolling captions with complete grammatical stationary phrases, preserve abbreviations, use verified color-only highlighting and reject fixed phrase-count quotas.
- Measure the complete caption bottom against worst forehead motion. For 720x1280 and 2160x3840 outputs it correctly derived minimum gaps of 133 1/3 and 400 final pixels. A stated 200-pixel initial gap reduced by 60 pixels becomes 140: conditionally above the first minimum and below the second. It did not equate a caption anchor or arithmetic alone with verified face safety.
- Measure visible bearings and the icon/text group for centering; scale badge padding and check every animation state, not just the hold.
- Reject enlarging a jagged 1x raster as supersampling, reject guaranteed UHD claims from CRF/bitrate settings, and require decoded native-resolution comparisons with the clean render.
- Reject copied credentials/dates without matching evidence and reject unverified stream mapping or AAC re-encoding described as identical audio.
- Require actual candidate identities, timecoded lossless evidence, full normal-speed playback/listening and a distinct reviewer; keep every known defect and unperformed check unresolved until repaired/reviewed.

A separate read-only adversarial audit traced 4K HDR/non-H.264 delivery, silent footage, left-aligned code, moving Cutout hands/hair, explicit reversed portrait placement, overlapping speakers, uncertain word timing, constrained rendering resources, replacement exports and All-mode output accounting. It found two concrete wording issues: an unqualified word-by-word reveal rule could include subtitles, and anti-overlap/active-word/boundary rules were not clearly scoped to individual speaker lanes. The first was limited to explanatory graphics. The second needed an additional focused revision after the first retest still found global wording; the final text explicitly scopes those rules per lane while preserving genuine concurrent speech. The independent final retest confirmed both findings resolved in the affected sections. These failures and repair stages are retained rather than reporting an unqualified initial pass.

These are one baseline response, one revised behavioral response and an independent source audit with focused retests. They establish instruction decisions and identified-conflict closure, not repeat-run reliability or audiovisual quality. The full responses are in the authoring chat. No actual frame extraction, rendering, listening, encoding-quality comparison or video repair was performed.

### Package and installed-copy checks

The instruction suite remains nine entries, twenty core references and thirty-eight Markdown/license files; no coding, model, media or dependency files were added. The bundled Skill Creator validation, metadata/name/license checks, wrapper-to-core resolution, Markdown links/anchors/fences and whitespace checks passed for the final suite. All nine entries use version 3.1.2. File checks do not prove that future agents will perform the required media reviews.

Before installation, the nine active entries were confirmed as 3.1.1 with the matching 38-file inventory. That exact installed copy was backed up to `C:/Users/nishi/.codex/skill-backups/omni-edit-pro-20261029-v3.1.1-before-v3.1.2`, and files were rechecked for concurrent changes before replacement. Twenty files changed; all thirty-eight installed files matched the repository suite byte-for-byte afterward. No remote publication or host UI reload test was performed. The previous 3.1.1 results below remain historical; none is relabeled as a 3.1.2 media pass.

## Historical 3.1.1 changes — 2026-10-29

This instruction-only update makes the vertical middle caption channel, moving-face protection, measured padded text backgrounds, evidence-backed spelling and dedicated Production Video Reviewer mandatory across the suite. The reviewer records every observed defect, including brief or cosmetic defects, and requires repairs and review of the actual replacement export before release. User-confirmed Rajiv/Amore wording is scoped to the matching source; it is not a global substitution dictionary. No supplied video was processed during this update, so these results do not certify rendered-video quality or perfect error detection.

### Baseline and independent instruction checks

A read-only evaluator used the unchanged committed baseline `66ecac3` before edits. In a hypothetical 42-second vertical Split/Cutout/Overlay delivery with a two-frame chin collision, a lower-body caption, an entrance-only badge overflow and uncertain ASR names, it already rejected face overlap, guessed wording and release without full playback. Those are retained safeguards, not invented baseline failures. It explicitly found no required middle caption channel and no explicit all-state badge-background containment rule: it permitted the clear lower-body caption and treated measured badge repair as its own design judgment.

Two fresh-context evaluators then read the revised production instructions without the validation report or each other's answers. These were decision tests with hypothetical facts, not media executions:

| Scenario | Observed revised decision |
| --- | --- |
| Same 42-second vertical case under urgent delivery pressure | Rejected both chin contact and default lower-body caption placement; required a motion-aware middle channel, padded containment through badge entrance, a distinct reviewer, all three full-candidate playback/listening checks and zero-open-defect release. |
| Partial identity evidence and phonetically matching names | Approved only the supplied title-card identity. Kept specialist title, venue and landmark wording unresolved pending relevant evidence; did not copy the example venue from the skill as proof. |
| Punctuation-corrected replacement export | Required full playback/listening of the new complete export plus targeted text-fit checks and a new fingerprint-specific verdict; retained reusable source/rights evidence. |
| Two sources, All vertical only, different doctors/venues | Counted six outputs; restricted approved glossary entries to the matching source; kept affected uncertain variants incomplete while independent work continued. |
| Crowded Cutout with moving hands/hair and Hindi/English diacritics | Reflowed upper graphics and measured padded text, preserved readable source/wording/timing and usable alpha gaps, and retained an unresolved geometry conflict if fit remained impossible. |
| Silent horizontal screen video and supplied typo | Avoided invented presenter, ASR and portrait channel; retained supplied-text proofreading, content protection, actual silence/stream inspection and full visual review. |
| Explicit reversed portrait layout and safe caption band, with source-embedded mouth overlap | Honored the explicit geometry but retained the burned-in defect pending a clean source or authorized repair; no crop/mask shortcut or final claim. |
| Stills and decode available, playback unavailable | Refused sign-off; recorded missing checks as not run and kept the candidate needs-review in Working Files. |

Both evaluators distinguished planned review from performed review. The five-case evaluator reported no instruction contradiction in its scope. This is one baseline response and two revised responses covering the listed decisions, not repeated-run reliability statistics or a visual-quality benchmark. The full responses are retained in the authoring chat; this table summarizes their actual decisions rather than assigning an audiovisual score.

### Package and installed-copy checks

All nine entries passed the bundled Skill Creator validator with matching 3.1.1 metadata, required names and wrapper-to-core links. The installable suite contains 38 files: nine SKILL.md files, twenty shared Markdown references and nine matching LICENSE files. File/heading-link, Markdown-fence and whitespace checks were performed; no application code, processing scripts, media, models or dependency files were added.

The active nine folders under `C:/Users/nishi/.agents/skills` were inspected against the historical `820d341` installation. Their 34 files had no content customizations or added/missing files; CRLF line endings were the only baseline differences. They were rechecked immediately before replacement and backed up to `C:/Users/nishi/.codex/skill-backups/omni-edit-pro-20261029-v2-before-v3.1.1`. All 38 installed files were then verified byte-for-byte against the revised repository suite. No duplicate OmniEdit installation was found under the native `.codex/skills` root. Host UI reload/discovery and real video execution were not tested, and no remote publication was performed.

## Historical 3.1.0 changes — 2026-10-27

The 3.1 instruction revision adds a shared lower-presenter/upper-animation default for portrait scenes in all four compositions, sustained meaningful graphic development, per-source art direction and contrast palettes, and alpha-aware Cutout negative space without a visible or reserved rectangle. Explicit placement, stillness and palette overrides remain authoritative; horizontal placement and non-presenter scenes retain their appropriate geometry. These are skill instructions, not claims about a newly rendered user video.

The pre-change 3.0 snapshot and four read-only baseline scenarios established that its vertical ordering was not common across compositions, matching-shape Overlay occupied the canvas, long still holds were permitted, and alpha-gap/palette/continuous-motion checks were incomplete. Existing silhouette extraction, source-specific planning and contrast guidance were retained; there was no actual written blue-background requirement to remove.

Current structural checks pass: all nine entries parse at 3.1.0 with matching license notices and shared-core dependencies; 174 relative file links and two local heading links resolve; Markdown fences and whitespace checks pass. The suite remains 37 files (9 SKILL.md, 19 reference Markdown files, 9 LICENSE). A final staged copy matches every installable file byte for byte. List-only Skills CLI discovery found the expected nine entries. No coding, media, model or dependency files were added to the repository; no live global skill update or remote publication was performed.

### Paired instruction tests and repair

Fresh evaluators independently simulated the same seven actual-edit requests against a preserved 3.0.0 snapshot and the new draft. Executors read their assigned production instructions and hypothetical source facts, without reading expected criteria or each other's responses. A separate grader used 28 frozen expectations per version with response-specific evidence. These are paper plans, not executed edits or actual audiovisual results.

| Case | Initial 3.1 draft | 3.0 snapshot | Focused repaired retest |
| --- | --- | --- | --- |
| Four portrait compositions | 4/4 | 2/4 | Not repeated; geometry unchanged |
| Raised-arm Cutout and alpha gaps | 3/4 | 1/4 | 4/4 |
| Sixty-second static-card proposal | 3/4 | 0/4 | 4/4 |
| Three different topic/clothing sources | 4/4 | 4/4 | Not repeated; treatment unchanged |
| Explicit brand, position and stillness overrides | 4/4 | 4/4 | Not repeated; authority unchanged |
| Silent horizontal landscape | 4/4 | 3/4 | Not repeated; behavior unchanged |
| Reference, vertical-only All and failure branches | 4/4 | 2/4 | Not repeated; counts and defaults unchanged |
| Initial total | **26/28** | **16/28** | **8/8 across the two repaired cases**, not a new seven-case aggregate |

The initial Cutout plan omitted separate light/dark diagnostic backgrounds despite mentioning alpha and changing-background review. The initial long-card revision did not explicitly commit to full-duration normal-speed motion viewing. The first omission also lost a check the old plan had included. Both original failures are retained. The core and relevant references now require a named release-check list before rendering: source preservation; whole-output normal-speed graphic/hold/transition viewing plus applicable listening; and Cutout playback on the actual animated, diagnostic light and diagnostic dark backgrounds. Fresh unhinted executions of the two affected prompts each passed 4/4 against the unchanged criteria. The targeted retest does not replace the other initial responses or constitute a second full paired run.

The tests show the planned portrait defaults, alpha-space handling and dynamic development within their stated scope. Several baseline checks already passed, especially independent source direction, color considerations and explicit overrides; the revision strengthens those requirements rather than introducing them from nothing. One response per version/case, correlated expectations and hypothetical facts do not estimate arbitrary-video reliability or subjective quality. No timing/token telemetry or completed playback was invented. The standard Skill Creator review viewer contains all 14 initial responses/grades plus the two focused retests, with initial aggregate and repair results separated. No human preference review is claimed.

An independent production-source review covered all four compositions, matching-ratio portrait Overlay, wide-source fitting, gestures across the nominal divide, true alpha versus bounding-box exclusion, reference/static-blue adaptations, moving-background contrast, separate sources versus versions, explicit overrides, silent horizontal footage, source preservation and All counts. It found no standing substantive contradiction within that scope. A focused follow-up verified that the new named review gates remain planned until evidence exists, respect scoped overrides/inapplicable checks and retain needs-review status. These reviews do not prove actual matte quality or model compliance on future runs.

Raw snapshots, prompts, strict grades, original failures, targeted repairs and the generated viewer are retained outside the repository under the authoring record `omni-edit-pro-portrait-motion-20261027`. The project contains only skill-related instructions/licenses and documentation. No new real-user-video render, Cutout extraction, full motion/listening test or media-quality benchmark was run for 3.1.

## Historical 3.0 status — 2026-10-27

| Evidence | Status and scope |
| --- | --- |
| Read-only v2 audit | Completed. Found the pre-inspection question gate, no formal source/reference roles, limited reference procedure, and presenter-focused routing. Existing media inspection, local execution, timelines, and QA were retained as useful foundations. |
| Clean v2 baseline | Completed as a paper simulation in an untouched 2.0.0 snapshot. Delegated edit cases 1 and 2 stopped at the old selection gate; this establishes the routing limitation, not a failed rendered edit. |
| Baseline structural check | Nine entry points and 110 repository-relative file links passed in the v2 baseline. These counts do not describe the revised v3 package. |
| Proposal comparison | Four proposals, two Arena rounds. The independently judged final selected a002 at 95.5 versus a004 at 90.5. The scores assess modification proposals, not edits of supplied videos. |
| v3 instruction implementation | The chosen Reference/Auto/Manual design is written into the shared workflow, wrappers, and public documentation. Implementation is distinct from validation. |
| v3 package checks | Passed: nine parsed entries at 3.0.0, all license bytes match, eight wrapper/core dependencies, 147 relative file links and one local heading link, closed Markdown fences, and clean whitespace. The installable suite has 37 files: 9 SKILL.md, 19 shared references and 9 LICENSE; no processing code, media, models or dependency files. An external staged copy matches every source file byte for byte; list-only Skills CLI discovery found the expected nine entries. |
| v3 comparative scenario evaluation | Completed: fresh old/new evaluators simulated the same three actual-edit requests with hypothetical fixtures, without reading expected criteria. Independent evidence-based grading: v3 5/5 + 5/5 + 5/5 = **15/15**; v2 3/5 + 2/5 + 5/5 = **10/15**. This demonstrates automatic/reference routing and planning on these cases; no media-quality score. |
| Independent adversarial review | Completed: ten scenario families traced generic Auto, Manual waits, host matching, preset overrides, narrowed All counts, ambiguous inputs, conflicting references, edit authority, silent/custom-ratio sources and capability failures. Found fixed six-output wording in narrowed-All recovery; corrected the core and local-cutout guide, then independently rechecked. No standing substantive findings in that review scope. |
| Synthetic toolchain smoke check | Bounded pass: locally generated silent source (640×360, 24 fps, 12 seconds) and portrait reference were inspected for stream/still attributes. A manually directed palette/callout candidate retained 288 frames and source geometry/duration, decoded fully, and its inspected frame retained all source borders/text. Initial Fontconfig failure was repaired with a verified installed font. All test scripts/media are outside this repository. Normal-speed/full-output review was not performed; candidate was not promoted to final. |
| Real-video quality comparison | **Not run**. No user-footage edit, real reference fidelity test, speech alignment, Cutout inference, checked final export, held-out preference study or audiovisual-quality benchmark has run. |
| Live global update / every-host discovery | **Not run** in this revision. Local package checks do not establish a live host reload or runtime capability. |

The proposal record is identified by authoring run `run-20261027-132533-s255224`, with four initial proposals and two elimination rounds. Raw research, baseline snapshots, six scenario responses, six evidence-cited grading records, an aggregate comparison, the independent review and a generated Skill Creator review viewer are authoring artifacts kept separately from the distributed instruction package. The summarized methods and results here do not depend on a repository-local scratch directory.

The paired cases were (1) a bilingual lesson with a rapid portrait reference and explicit full-speech/full-frame preservation, (2) an eight-minute screen tutorial with system sounds, no dialogue or presenter and delegated choices, and (3) two same-basename interview sources plus a reference in All mode with hypothetical reference/Cutout/listening failures. v2 stopped at the orientation gate in the first two; v3 selected constrained Reference/Auto plans. Both preserved the third case's two sources, twelve requested variants and incomplete-output safeguards.

There was one response per version per case. Several checks are regression controls, and gate-related gains are correlated; 15/15 is not an estimate of reliability across genres or model runs. Runtime/token telemetry was unavailable and was not reported as zero. The standard aggregation's unsupported telemetry defaults were removed; any case-to-case score spread is not repeat-run variability. No human feedback or blinded visual preference is claimed. The generated viewer presents the actual responses and grades for further review.

## Historical v2 evidence — 2026-10-24

The following completed checks apply to **version 2.0.0**. They are preserved as history, not carried forward as v3 passes.

| Check | Historical observed result |
| --- | --- |
| YAML and names | All nine SKILL.md frontmatters parsed with PyYAML; required names/descriptions and version 2.0.0 verified |
| CLI discovery | Skills CLI 1.7.2 list-only discovery found exactly the expected nine entries |
| License distribution | Every entry LICENSE matched the root license byte for byte |
| Instruction inventory | 34 files under skills/: 9 SKILL.md, 9 LICENSE, 16 shared Markdown references; no processing code, runtime packages, models, or media |
| Shared links | Eight wrappers read the sibling core; all 56 installable-instruction relative links resolved |
| Staged manual copy | Fresh temporary staging copy matched source package SHA-256 values; wrapper shared-core paths resolved |
| Isolated CLI copy | All nine explicitly selected skills installed into a temporary Codex project scope; all 34 files matched and 56 installed relative links resolved |
| Source identity | Nine historical source origins/revisions matched the attribution record |
| Repository publication check | 110 repository-relative file links and 14 former README contents anchors resolved; metadata, license, Markdown fence, and whitespace checks passed |

Neither installation check changed the user's live global skills. Host app discovery, native teams, media tools, and rendered quality remained separate checks.

A v2 instruction dry run traced missing choices, explicit presets, All with same-basename sources and limited workers, failed Cutouts, explanation-only requests, unavailable playback, absent native teams, and clear preset overrides. It confirmed the then-required question gate and found wording issues that were repaired in v2. These were instruction traces, not executed media operations. The v3 change intentionally replaces that generic-question behavior while retaining explicit preset and preservation contracts.

## v3 scenario acceptance plan

Use identical prompts and the untouched baseline snapshot for old/new routing comparisons. Record each response, route, unresolved blocker, job/variant count, evidence claim, and deviations. A paper scenario must stay labeled as such: no actual frames, sound, task handles, or output paths may be invented. Run independent review against the expected behaviors below.

| Scenario | Required v3 result |
| --- | --- |
| Two sources plus a designated reference; All | Exactly two source jobs, explicit reference mapping, twelve requested variants; reference never becomes a source |
| Same inputs; All horizontal only | Six requested variants total, three per source; Adaptive is not added |
| Two unlabeled videos with ambiguous roles | Ask the role question before creating the production jobs |
| Rapid-cut reference plus dense explanation; keep every word | Preserve original speech/timing; adapt visual treatment; disclose incompatible cut rhythm |
| Silent screen recording, no reference | Auto source inspection; protect interface/action detail; no invented transcript or compulsory presenter Cutout |
| Mixed travel/interview footage, no reference | Scene-level planning, confidence notes, source-aspect/Adaptive path when appropriate; no unauthorized montage |
| Vertical sample plus explicit horizontal output and no crop | Explicit shape wins; fit source and adapt treatment; report reference deviation |
| Explicit Vertical Overlay plus “horizontal instead” | Horizontal Overlay, changing only the named dimension |
| Generic edit automatically matched to a preset by the host | Main Auto/Reference routing applies; automatic matching does not supply explicit preset defaults |
| Explicit Manual with missing choices | Ask only missing format/composition choices and wait; no media-based inference before those answers |
| User explicitly asks for shorter/highlights/montage | Treat that request as authorization within its stated scope; do not demand repeated permission for the same edit |
| Several references with material conflicts | Use attribute assignments or designated primary; resolve remaining material conflict before implementation |
| Requested reference cannot be opened | Report unavailable evidence; do not claim a match or silently switch to Auto |
| Low-confidence Cutout, absent playback, or absent native teams | Name the actual capability gap; preserve partial/needs-review states and truthful execution choice |
| Explicit six presets and All regressions | Preserve their contracts, overrides, unique source IDs, exact variant accounting, isolated paths, and checked-only delivery |
| Explanation/install/authoring request | Complete that task without launching an edit or production teams |

A passing routing comparison can support a narrow claim that v3 removes the compulsory gate for appropriate Auto/Reference requests. It cannot support a claim of better video quality. A written rule's presence is separate from observed agent compliance.

## Future rendered-media benchmark

No such benchmark has run. Before executing one, freeze held-out sources, reference mappings, permissions, rubric, host/model, tool versions, resource limits, and acceptance rules. Include several independent sources per mode and material not used to tune the instructions. For routing, compare the same prompt. For visual quality, also provide v2 equivalent explicit choices so its old gate does not become an unfair quality penalty.

Every candidate must pass hard checks: correct variants, source meaning, authorized edits only, dialogue/caption accuracy, readable protected content, sync, clean audio, permitted framing, end-to-end decode, and actual viewing/listening. Inspect difficult passages and full exports. Mark unavailable dimensions unassessed rather than filling in a score.

Score Reference on observable typography, hierarchy/layout, motion, transitions, pacing, and sound resemblance, including appropriate adaptations. Score Auto on content suitability, clarity, pacing, relevance, and restraint. Separate technical pass/fail, creative ratings, blinded paired preferences, elapsed processing time, and hands-on repair time.

A proposed pilot gate is: every hard check passes; median relevant reference-fit/content-suitability ratings improve on an anchored 1–5 scale; at least two-thirds of blinded pairs prefer v3 in each mode with ties counted as no win; median hands-on repair time does not increase; and no serious defect repeatedly affects a tested content type. Freeze the actual gate before testing and report counts, scores, ties, losses, repair times, and repeat variability. This proposed gate is not a demonstrated result or a reliability guarantee across genres.

Negative, tied, inconsistent, or undersized results require revision, further evidence, or claims limited to the demonstrated benefit and tested material. No universal quality, arbitrary-reference reproduction, virality, or “best editor” claim follows from a working instruction path.

## Production evidence required for each later edit

The runtime workflow requires actual source/reference inspection records, an explicit permission/output plan, representative preview review, full-candidate technical and audiovisual checks, defect repair, and an accurate delivery status for every requested variant. Passing a short test does not verify the whole video. Failed or unreviewed candidates remain in Working Files; only checked exports enter Final Output Videos.

Authoring checks verify an instruction package. Actual capability and output acceptance remain the responsibility of each later execution in its real host and editing workspace.
