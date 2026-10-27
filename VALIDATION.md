# Validation evidence — OmniEdit Pro 3.1.0

This document separates historical package checks, v3 instruction tests, a bounded synthetic media check, and future media benchmarks. **No actual user-supplied source video has been edited or rendered during this authoring task.** Instruction tests and proposal scores cannot establish audiovisual quality or reference fidelity.

## Current 3.1 changes — 2026-10-27

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
