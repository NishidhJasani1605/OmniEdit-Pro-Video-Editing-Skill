# Strict production video reviewer

Read this assignment with [Quality assurance](quality-assurance.md). It applies to every source, requested variant and revised export, in every genre and format. The dedicated **Production Video Reviewer** is a real native subagent distinct from the editor and repairing specialists, assigned under [Batch and teams](batch-teams.md). This is an instruction-defined role, not application code or a claim of special perception capabilities.

## Authority and handoff

The reviewer owns the release verdict; the video lead owns integration and promotion. Every specialist receives and follows the shared face-protection, text-containment, verified-wording and review requirements. A producer's deadline, render cost, attractive overall result or description of a defect as cosmetic does not turn a failed check into a pass. A stated budget is a quality expectation, not permission to buy tools or services.

Give the reviewer this concrete handoff before review:

| Required item | Contents |
| --- | --- |
| Identity | Source ID, variant, candidate absolute path, version and file fingerprint; source-to-output mapping |
| Brief | User constraints, actual requested output, composition, approved treatment and any explicit overrides |
| Text evidence | Raw/reviewed transcript where speech exists, approved terminology ledger with evidence, all caption/title/badge/end-card/sidecar text and outstanding questions |
| Geometry | Per-scene protected presenter/gesture bounds, caption channel and measured minimum clearance, phrase/word positions, actual fonts, glyph bounds, centered heading boxes, badge padding/wrapping and platform safe areas |
| Semantic units and motion | Each unit's exact content/source anchor, first semantic visibility, entry/settled/hold/exit frames, property endpoints/easing, persistent elements and same-slot handoff schedule |
| Available-space decisions | Candidate clear regions over the complete cue, primary versus compact form and reason, readable type floor, measured content-sized boxes, motion/overlap footprints and worst clearance |
| Render and encoding | Graphics render scale, downsampling/compositing path, clean reference frames, actual encoder/rate control/color settings, audio source selection and passthrough/re-encode choice |
| Media evidence | Original source, applicable references/assets, candidate with actual audio or verified silence, diagnostic Cutout composites when applicable |
| Prior review | Check coverage, defect ledger, repair ownership and previous candidate verdicts; do not inherit a pass for changed output |

Missing required inputs or unavailable viewing/listening capability means incomplete review. Never claim to have watched, heard or checked content that the host cannot expose. Follow the existing team-capability fallback rules; a role label is not a spawned reviewer.

## Review passes

1. **Wording and meaning.** Compare every displayed string and supplied caption file with the approved text evidence. Replay speech where relevant. Check names, acronyms, venues, landmarks, technical terms, spelling, punctuation, numbers, units, negations, capitalization, repeated/missing words, language and glyph shaping. Confirm that correct text is actually rendered, not merely present in the project. Independently verify uncertain corrections; plausibility and ASR confidence are not proof. Unresolved words prevent release of affected outputs. Do not alter a speaker's claim to hide a factual error.
2. **Composition and text.** Inspect every cue and layout state at native output resolution and intended delivery size. For vertical presenter scenes require the reserved middle caption channel and resolution-scaled clearance measured from the complete caption footprint to the highest forehead during the cue, unless the user explicitly changes placement. Keep foreground text/cards off the actual person, including face, chin and neck, throughout motion. Check every badge's rendered glyphs plus padding through all states; measure each banner/title/CTA against its intended content-box center, accounting for bearings and output-pixel rounding. Check every caption's fixed word/box positions across highlights, genuine sentence boundaries and actual active-word timing. Reject moving windows, bold/scale-induced reflow, text jumps and sentence bleed. Verify line breaks, contrast, clipping, font fallback, controls, existing captions and competing layers under [Layouts](layouts-effects.md) and [Transcription](transcription-sync.md).
3. **Complete audiovisual playback.** Watch the entire final candidate at normal speed, including opening, all scenes, transitions and final tail; listen to its actual audio where present. Check source preservation, sync, caption timing/reading time, purposeful motion, readability, cuts, glitches, color, audio continuity and final frames under the full QA checklist. Cutout also needs playback on actual animated, light diagnostic and dark diagnostic backgrounds. A montage of samples or a successful full decode cannot replace this pass.
4. **Small-defect sweep.** Inspect every text cue, each layout/transition boundary and difficult movement interval in detail. Check cue start, start+1, end-1 and end frames where valid; step through any suspect passage and any motion/scale/occlusion extremes between endpoints. Look for a one-frame face collision, partially uncovered character, punctuation outside a plate, cut descender/diacritic, clipped word tail, orphaned line, typo, jitter, matte flicker, audio click and inconsistent repeated spelling. Automatic collision/text checks help locate faults but require verification in the actual render. Sampling never proves that every frame is perfect.

Run the representative preview review before full production and repeat the applicable checks on **every complete candidate**. A safe horizontal version does not certify a vertical version; one source's approved spellings do not approve another source's names.

During these passes, verify the [semantic reveal contract](motion-design.md) and [space allocation](layouts-effects.md#allocate-space-before-sizing-panels) explicitly. Listen/observe each source anchor against the first visible meaning: future descriptions must remain hidden, and qualifications stay with their claims. Check that one small idea settles long enough to read before the next focal change. Step through intra-card and scene handoffs for easing resets, pops, flashes, truncated exits, moving shared headings and old/new prose overprint. Check the whole travel/resize/overlap footprint, not only the settled panel. Reject a detailed panel in a region that only supports a keyword/symbol, oversized empty backing, tiny text and a panel that crowds the moving presenter even without touching. A concise companion cue is optional; do not demand symmetrical boxes. Require the recorded worst clearance and actual rendered evidence, not a claim that the layout is responsive.

## Verification frames and post-render repair evidence

After each complete candidate is encoded, extract **lossless native-resolution PNGs from that actual file** into its working review folder. Derive timestamps from the timeline: every scene transition before/after, every card's readable hold, every subtitle cue midpoint, caption entry/exit boundaries, active-word changes that could expose layout shifts, movement/overshoot extremes, opening and final tail. Do not reuse the example timestamps from another video or certify a long cue from its midpoint alone. JPEG quality 98 may serve a contact sheet, but use lossless crops for typography/codec diagnosis.

Include each explanatory unit immediately before/at/after first semantic visibility, its settled readable frame, the old/new handoff boundary, and the worst space/gesture interval. Use those frames to verify hidden future content, eased continuity and measured clearance; keep normal-speed viewing/listening as the temporal check. Respect any explicit no-save constraints using permitted in-memory review and notes rather than persisting forbidden media; if that prevents required verification, report the specific evidence gap.

Keep a compact evidence manifest with candidate fingerprint, source/variant, output time and frame, cue/scene ID, image path and checks/results. Extract both context frames for layout and native-scale crops for glyph edges. Compare actual decoded text with clean pre-encode reference frames to separate raster/scaling problems from compression. Check diagonals and curves, smallest text, diacritics, dark gradients, colored active words, halos, shimmer and chroma bleed using [Audio and rendering](audio-rendering.md). Two-times rendering or CRF 14 alone is not a PASS. Record caption word positions across multiple highlight states; a stable midpoint cannot prove temporal stability. Review full playback/listening in addition to stills.

The acceptance rubric is: **presenter clearance; stationary grammatical phrases and accurate word highlighting; full padded badge containment; measured heading centering; clean final decoded typography; verified entities/credentials/date/time; preserved source sound/timing/lip-sync; small source-anchored reveals with smooth handoffs; and content-sized panels in measured clear regions**. Check other quality requirements above as well. Mark each passed, failed, not run or source-grounded inapplicable; do not average failed items into a high overall score.

For any failure, identify the responsible cue/layer, layout/font/scale/encode setting or project source location; send a concrete repair to its specialist. Within existing authority, the lead applies the repair without asking for routine approval, re-renders the affected test and integrated candidate, then the reviewer re-extracts evidence and repeats the checks on the new export. Earlier verification images and verdicts stay linked to their old candidate. The editor cannot declare its own repair accepted. If actual media inspection is unavailable, retain needs-review rather than generating a fictional pass report.

## Defects and repair loop

Record every observed defect, including minor cosmetic defects. Use a compact ledger with: defect ID; candidate fingerprint; source/variant; timecode and frame range; exact offending text/layer; observed versus required behavior; evidence; responsible specialist; repair; replacement candidate; retest result; and open/closed state. Severity sets repair order, never permission to ignore a known defect. Distinguish an observable error or brief violation from an optional aesthetic preference; review is not permission to redesign an approved treatment.

Send each defect to its owner. Reflow geometry for collisions; measure text again after wording/font/wrapping changes; propagate verified terminology corrections to all dependent text and variants. Preserve source meaning, timing, framing and explicit choices. Re-render the affected preview and integrated candidate. Close a defect only after the reviewer inspects the repaired export and adjacent boundaries, not after an editor says it was fixed.

A changed full export needs full-duration normal-speed viewing and applicable listening again, plus targeted checks of repairs and dependent states. Reuse unchanged source/rights evidence; do not repeat unrelated research. Scope of a correction guides targeted inspection, but an old export's approval cannot certify new bytes. After two targeted failures from the same cause, diagnose a different permitted local approach or report the specific blocker. Do not lower the standard, loop without diagnosis or silently deliver a defective fallback; independent passing jobs may continue.

## Release decision

| Verdict | Condition and action |
| --- | --- |
| **PASS** | All applicable checks performed and passed on the identified complete candidate; zero open observed defects and zero unresolved text; record reviewer task identity, coverage, evidence and file fingerprint. The lead may promote that same file under [Delivery](delivery.md). |
| **NEEDS REPAIR** | Any observed defect remains, even tiny, brief or cosmetic. Keep the candidate in Working Files and return the ledger to its owners. There is no "pass with minor issues". |
| **NEEDS REVIEW / INPUT** | Required review, evidence, wording confirmation or media access is missing. Identify exactly what is missing; do not treat a not-run check as a pass. |

Record each check as passed, failed, not run or inapplicable with a source-grounded reason. If both defects and review gaps exist, retain both; neither cancels the other. A source-embedded defect that cannot be repaired within existing authority remains unresolved pending a clean source or authorized treatment. Do not hide it through cropping, masking, rewriting or an inapplicable label.

The release report states what was inspected and that no known defects remain within that review. It never promises infallibility or certifies unobserved frames. Instruction-only evaluations test this decision process; only actual media review can approve a video.
