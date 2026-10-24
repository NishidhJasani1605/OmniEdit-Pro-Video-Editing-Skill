# OmniEdit Pro implementation plan and delivered design

This plan implements the user's instruction-only video skill. The nine requested repositories have been downloaded and inspected; their guidance has been adapted into the local suite. Ten source-list entries come from nine repositories because both delegation skills are in Superpowers.

## Source list: what each contributes

| Source skill/repository | What it teaches | Why it is included |
| --- | --- | --- |
| [Official Remotion Skills](https://github.com/remotion-dev/skills) | Composition, media, captions, frame timing and rendering | Technical editing guidance; independently written, with no copied unlicensed prose/code |
| [iArt Motion Design](https://github.com/iart-ai/motion-design-skills) | Art direction, easing, hierarchy, composition and color | Smooth consistent presentation across all three styles |
| [iArt Talking-Head B-roll](https://github.com/iart-ai/b-roll-skills) | Select supporting visuals from speech while narration continues | Make graphics relevant to the speaker's actual message |
| [AI Self-Media Packaging](https://github.com/zhouyuechuan2025-ui/ai-self-media-video-packaging-skill) | Presenter windows, information cards, flows and illustrations | Inform Split layouts and clear educational explanation |
| [iArt TikTok Video](https://github.com/iart-ai/tiktok-video-skills) | Vertical composition, captions, lower thirds and short-form presentation | Improve tall layouts and readability without forced cuts |
| [iArt Kinetic Typography](https://github.com/iart-ai/kinetic-typography-skills) | Phrase reveals and animated text emphasis | Match keywords and captions to reviewed spoken timing |
| [iArt Explainer Video](https://github.com/iart-ai/explainer-video-skills) | Storyboards, diagrams and whiteboard explanations | Explain relationships instead of adding unrelated effects |
| [HyperFrames Media-Use](https://github.com/heygen-com/hyperframes/blob/main/skills/media-use/SKILL.md) | Relevant local cutout/media guidance | Inform alpha handling, detail preservation and temporal checks; exclude paid providers |
| [Dispatching Parallel Agents](https://github.com/obra/superpowers/blob/main/skills/dispatching-parallel-agents/SKILL.md) | Independent assignments, clear scope and result integration | Coordinate separate videos and independent specialist tasks |
| [Subagent-Driven Development](https://github.com/obra/superpowers/blob/main/skills/subagent-driven-development/SKILL.md) | Specialist assignments, review and corrections | Require evidence before accepting each production stage |

Pinned revisions, rights findings and rejected upstream assumptions are in [ATTRIBUTIONS.md](ATTRIBUTIONS.md). These are selected for fit; no claim is made that every pack ranks first by stars or output quality.

## 1. Package the instructions — implemented

Keep the shared production rules in `skills/omni-edit-pro/`. Add the new main entry, six direct orientation/style entries, and All as thin wrappers. All nine are discoverable skills; each preset reads the same-release sibling core, retaining its selections.

Ship Markdown and license notices only. Do not ship .py/.js processing code, media, models, application templates or dependency trees. A later editing agent may create those things in the chosen editing workspace when required.

Installation copies the complete core and requested wrappers. It does not execute upstream scripts, start an edit, download models or install video tools. Preserve existing local skill edits. Verify complete contents and host discovery separately.

## 2. Add the compulsory selection gate — implemented

For an actual editing request, resolve orientation and style from the prompt or preset. If orientation is missing, ask the simple wide/tall question and wait. Then ask the simple three-style question only if still missing and wait again. No media inspection, transcription, production-team dispatch or rendering proceeds before required choices are answered.

Ask only missing choices. An explicitly user-selected complete direct preset skips questions. Automatic host/model matching never supplies missing user choices. An explicitly selected All preset requests six variants per video. Explicit later instructions override presets. Explanation, installation and skill-authoring requests do not trigger production.

## 3. Dispatch separate video teams — implemented

Create a unique job for each source, including distinct IDs for matching basenames. Use actual host-native agent tools and record real task handles, dependencies, owned paths and status.

Each video gets scoped work for speech/captions, visual direction/assets, layout/animation, optional cutout, audio/export and independent review, coordinated by its lead. Reserve worker capacity for progress/review; if nesting is unsupported, the root coordinator dispatches specialists. Queue any number of supplied videos within available resources rather than promising unlimited simultaneous workers.

Neither a separate orchestration library nor a separate questioning skill is needed. Markdown gives the workflow; native tools supply actual agent capability. If the host cannot create teams, explain the limitation and obtain an execution choice before using a solo fallback.

## 4. Preserve the source and establish timing — implemented

After selection, inspect actual source streams, frames and sound. Keep source identity, timestamps, rotation, display aspect ratio, frame rate and color information. Review transcript uncertainty and use output-frame timing for visual cues.

Default to preserving all original dialogue, order, pauses, original timing and lip-sync. Do not import short-form advice that silently trims silence, speeds speech, regenerates voice or inserts punch-in jump cuts. Use one authoritative timeline and one original narration owner.

## 5. Build the selected style — implemented

| Style | Horizontal | Vertical | Quality contract |
| --- | --- | --- | --- |
| Split | Full source fitted left/right; explanation beside it | Full source fitted above/below; explanation in remaining space | Preserve full frame, visible speaker and gestures; no cover crop or source zoom |
| Cutout | Isolated speaker over a designed graphic scene | Isolated speaker with graphics arranged for tall space | Remove background, preserve real person detail, hair, hands and movement |
| Overlay | Original footage/background with graphics over clear areas | Same treatment reflowed to tall output | Do not move footage into a separate presenter panel or remove its background |

Use uniform contain fitting. When geometry conflicts with full coverage and unchanged apparent person size, show the fit and resolve the actual tradeoff instead of hiding a crop. Reflow diagrams and captions; do not crop the horizontal export to create portrait.

## 6. Make motion explain the speech — implemented

Create a compact treatment from the actual subject: typography, contrast, color, graphic vocabulary and movement. Storyboard important entities, actions, relationships and outcomes from reviewed speech.

Use smooth entrances, readable holds and clear exits. Anchor important values and claims to spoken cues; emphasize phrases without making every word compete. Derive measurement-like waveforms/charts from real data. Protect the speaker, gestures, existing source text and caption space.

No fixed number of effects or artificial retention score is required. Preserve good source moments and simplify crowded graphics. Professional presentation and engagement are goals, with no guarantee of virality.

## 7. Use a free local Cutout path — implemented

Investigate supplied alpha first, genuine chroma key when appropriate, then a suitable free local matting/segmentation engine. The executing agent may write local masking/tracking/model code or practical rotoscoping in the editing workspace. A static face crop is not subject isolation.

Test the hardest passage before processing everything. Preserve original-resolution subject appearance where possible, maintain mask/RGB/time correspondence, and inspect bright/dark composites and moving edges. Encoding settings cannot repair poor segmentation.

If a free local method still fails, report the Cutout limitation and preserve its labeled preview. Continue independent Split/Overlay work. In All mode, four completed variants do not equal six; missing Cutouts remain explicitly incomplete. No automatic paid/cloud fallback is allowed.

## 8. Review and deliver — implemented

Render representative previews and full candidates in `Working Files/<video-id>/`. Independently check selected format/style, full framing, person prominence, caption accuracy/readability, speech preservation, audiovisual sync, animation, cutout edges, color, sound and technical decode.

Repair concrete failing intervals and review their affected boundaries. Missing audiovisual review produces needs-review, not a completed final.

Promote only checked files into `Final Output Videos/<video-id>/`, using orientation/style/version names. Preserve earlier finals. Keep code, projects, assets, captions, credits, previews and evidence in working folders. Report every requested variant and exact paths; reconcile all six per video in All mode.

## 9. Validate the skill package — completed for instruction scope

- Parse every entry's YAML and verify name/version/license.
- Verify all relative instruction links and same-release sibling dependencies.
- Stage a full copy outside the project and compare all package bytes.
- Confirm Skills CLI discovers all nine entries.
- Dry-run selection, batch ownership, preset override, missing capability, Cutout failure and unreviewed-output scenarios against the written instructions.
- Audit all explicit requirements against the implemented files.
- Keep evidence and test limits in [VALIDATION.md](VALIDATION.md).

## Later real-video acceptance

A real editing request supplies footage and a workspace, then executes this workflow with the host's actual capabilities. Start with a short difficult passage in the chosen mode, review the fit and motion at delivery size, and scale to full videos only after it passes. Test all six if All is requested.

This package has not rendered a supplied video during skill authoring. Instruction routing and package checks prove the suite is structurally ready; they do not prove an arbitrary host can render or that a particular matte/animation already passes audiovisual review.
