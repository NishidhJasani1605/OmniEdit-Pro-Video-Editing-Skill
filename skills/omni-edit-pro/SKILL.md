---
name: omni-edit-pro
description: Edit one or many supplied videos with per-video specialist teams, horizontal or vertical output, and split, speaker-cutout or original-overlay styles. Shared workflow and compatible original entry for the OmniEdit Pro presets; asks for missing format and style before processing.
license: MIT
metadata:
  author: NishidhJasani1605
  version: "2.0.0"
---

# OmniEdit Pro

Turn supplied footage into coherent, verified edits. This is the shared implementation for `omni-pro-edit`, the six orientation/style presets, `omni-pro-edit-all`, and this original `omni-edit-pro` entry. Preserve preset selections when a wrapper loads this file. This package contains instructions only; generate any project code, masks, dependencies and media in the user's editing workspace, never in an installed skill. No upstream skill or script is required.

## Resolve the two choices first

For an editing request, read [Selection](references/selection.md) before media inspection, transcription, team dispatch, project creation, runtime installation or rendering. Read only the prompt, explicitly user-selected preset and supplied path labels to resolve choices. Automatic skill matching must not invent either choice or bypass the questions. Do not infer orientation from the source video, or a style from the topic.

If orientation is missing, ask only: **"Do you want a wide video for YouTube (horizontal 16:9) or a tall video for Reels/Shorts (vertical 9:16)?"** Wait for the answer. If style is still missing, then ask: **"Which style do you want: 1. Split — speaker beside or above/below explanations; 2. Cutout — speaker with the background removed over graphics; or 3. Overlay — original video with animations on top?"** Wait for the answer. Ask only the missing question when the other choice is supplied. Never treat an unanswered question or elapsed time as a selection.

An explicitly user-selected `all` preset selects both orientations and all three styles: six outputs for each video. Explanation, installation, skill-development and planning-only requests do not trigger the editing questions or processing.

## Start and protect the edit

After selection, identify source files, requested deliverables, audience and constraints. Inspect available evidence before asking additional questions. A normal editing request includes producing checked final video files; a requested plan or preview limits that deliverable. Do not invent footage, transcripts, native subagent capabilities or completed renders.

For talking-head and narrated work, default to preserving **all original dialogue, its order, original timeline, and lip-sync**. Keep the original footage continuous underneath supporting visuals when applicable. Do not trim pauses, create jump cuts, change speed, regenerate speech, or shorten the narrative without explicit editing instructions. Clarify a shorter requested runtime that conflicts with full dialogue preservation. Other genres follow the user's creative brief; record approved cuts and their source mappings.

Preserve full source framing in Split and Overlay: no unwanted crop, punch-in, stretch, face enlargement or quality-reducing zoom. In Cutout remove the background, not body parts; retain original subject detail and movement. Read [Styles and framing](references/editing-styles.md) and, for Cutout, [Local cutouts](references/local-cutout.md). Reflow graphics for a different aspect ratio; fit the source with padding when necessary. Never promise unchanged pixel size, full-frame coverage and an uncropped source when geometry makes that impossible.

Use free/local processing and assets. Prefer a compatible Remotion setup where the intended use requires no paid license, with FFmpeg/FFprobe for preparation and verification. Follow [Environment](references/environment.md) for a free local alternative when needed. One engine owns composition and time. Exclude paid APIs, credit-based services, paid stock and hosted processing from this workflow. Ask only for genuinely missing installation authorization; existing authorization persists. No publishing is implied by editing.

## Coordinate each video

Read [Batch and teams](references/batch-teams.md). Create a separate job and native specialist team for every source video, queueing tasks within available agent and hardware limits. Assign speech, art direction, layout/animation, audio/export, cutout when relevant, and independent review tasks. Keep different videos' writable files isolated. Use actual host subagent tools; do not merely label one agent as a team. If unsupported, explain the limitation and obtain a changed execution choice before replacing requested teams with solo work. Completed independent jobs may continue while another job needs attention.

For All mode, share verified source analysis and transcript within each video, but plan and review each of its six compositions. A failed cutout does not block valid Split/Overlay jobs, and four completed outputs are not a completed six-output request.

## Route the work

Read only the references needed for the current stage. Begin with workflow and environment; load creative and technical detail when it affects a decision.

| Stage | Read when needed | Produce or verify |
| --- | --- | --- |
| 1. Select and dispatch | [Selection](references/selection.md), [Batch and teams](references/batch-teams.md) | Answered choices, jobs, real team assignments |
| 2. Detect environment | [Environment](references/environment.md) | Tool/version inventory, workspace, dependency gaps |
| 3. Inspect sources | [Workflow](references/workflow.md) | Media facts, sample observations, narrative continuity mode |
| 4. Understand speech | [Transcription and sync](references/transcription-sync.md) | Reviewed words/segments, timestamps and uncertainty |
| 5. Direct the edit | [Visual planning](references/visual-planning.md) | Style, pacing, shot plan and semantic cues |
| 6. Select assets | [B-roll and assets](references/broll-assets.md) | Relevant, cleared assets with provenance |
| 7. Build the timeline | [Transcription and sync](references/transcription-sync.md) | Integer frame intervals, source mappings, cue ledger |
| 8. Composite and animate | [Motion design](references/motion-design.md), [Layouts](references/layouts-effects.md) | Deterministic composition, readable face-safe graphics |
| 9. Preview | [Audio and rendering](references/audio-rendering.md) | Representative renders with real audio |
| 10. Review and repair | [Quality assurance](references/quality-assurance.md) | Measured checks plus visual and listening review |
| Finish and deliver | [Delivery](references/delivery.md), [Audio and rendering](references/audio-rendering.md) | Checked exports in `Final Output Videos`, project, credits and status |

For installation, discovery, or host differences, read [Agent compatibility](references/agent-compatibility.md). Source attribution is in [Source notices](references/source-notices.md). Do not load all references or fetch upstream instruction sets on every invocation.

## Completion standard

Keep a compact evidence record in the editing workspace: media facts, edit decisions, transcript confidence, frame timeline, asset rights, and QA results. For a small edit these can be sections in one plan rather than many files. Reuse verified work after a failure.

Align contextual visuals to reviewed spoken concepts at output frame boundaries. Choose smooth, readable animation, diagrams, cards, relevant B-roll and original graphics to suit each video. Animation should explain or emphasize meaning; no compulsory effect count, cut frequency or fake retention score. Never promise virality or millisecond accuracy beyond the frame rate and alignment evidence. Avoid covering faces, gestures, essential screen content or captions.

Render into the working area first. Only checked completed video exports go in `<editing-workspace>/Final Output Videos/<video-id>/`, following [Delivery](references/delivery.md). Keep previews, code, captions, credits and diagnostics in their appropriate working/project folders. Preserve earlier finals with versioned names. Report every requested variant as completed, needs review, failed or blocked, with exact paths and any review gaps. A successful command, source check or routing test alone is not proof of professional editing quality.
