---
name: omni-edit-pro
description: Plan, edit, composite, caption, and finish videos with a coordinated Remotion and FFmpeg workflow. Use for talking-head, podcast, educational, social, product, documentary, and narrated video editing, including synchronized B-roll and motion graphics.
license: MIT
metadata:
  author: NishidhJasani1605
  version: "1.0.0"
---

# OmniEdit Pro

Turn the user's footage and brief into a coherent, verified edit. This is one coordinated editing skill, not a rendering engine. Write project code and generated artifacts only in the user's chosen editing workspace, never inside this installed skill. No upstream skill installation is required.

## Start and protect the edit

Identify source files, requested deliverables, audience, and constraints from the conversation. Inspect what is available before asking questions. If footage or a consequential creative choice is missing, ask narrowly and continue independent planning. Do not invent footage, transcript, tool availability, or completed renders.

For talking-head and narrated work, default to preserving **all original dialogue, its order, original timeline, and lip-sync**. Keep the original footage continuous underneath supporting visuals when applicable. Do not trim pauses, create jump cuts, change speed, regenerate speech, or shorten the narrative without explicit editing instructions. Clarify a shorter requested runtime that conflicts with full dialogue preservation. Other genres follow the user's creative brief; record approved cuts and their source mappings.

Use Remotion as the principal composition engine and FFmpeg/FFprobe for inspection, preparation, audio finishing, and verification, all driven by one timeline. If the required engine is missing, follow the environment fallback instead of creating a competing editor. Ask before installing heavyweight dependencies or models; honor existing authorization. Asset downloads, hosted processing, purchases, and publication need authorization appropriate to the actual task.

## Route the work

Read only the references needed for the current stage. Begin with workflow and environment; load creative and technical detail when it affects a decision.

| Stage | Read when needed | Produce or verify |
| --- | --- | --- |
| 1. Detect environment | [Environment](references/environment.md) | Tool/version inventory, workspace, dependency gaps |
| 2. Inspect sources | [Workflow](references/workflow.md) | Media facts, sample observations, narrative continuity mode |
| 3. Understand speech | [Transcription and sync](references/transcription-sync.md) | Reviewed words/segments, timestamps and uncertainty |
| 4. Direct the edit | [Visual planning](references/visual-planning.md) | Style, pacing, shot plan and semantic cues |
| 5. Select assets | [B-roll and assets](references/broll-assets.md) | Relevant, cleared assets with provenance |
| 6. Build the timeline | [Transcription and sync](references/transcription-sync.md) | Integer frame intervals, source mappings, cue ledger |
| 7. Composite and animate | [Motion design](references/motion-design.md), [Layouts](references/layouts-effects.md) | Deterministic composition, readable face-safe graphics |
| 8. Preview | [Audio and rendering](references/audio-rendering.md) | Representative renders with real audio |
| 9. Review and repair | [Quality assurance](references/quality-assurance.md) | Measured checks plus visual and listening review |
| 10. Finish and deliver | [Audio and rendering](references/audio-rendering.md) | Verified final files, project, credits and known limitations |

For installation, discovery, or host differences, read [Agent compatibility](references/agent-compatibility.md). Do not load all references or fetch upstream instruction sets on every invocation.

## Completion standard

Keep a compact evidence record in the editing workspace: media facts, edit decisions, transcript confidence, frame timeline, asset rights, and QA results. For a small edit these can be sections in one plan rather than many files. Reuse verified work after a failure.

Align contextual visuals to reviewed spoken concepts at output frame boundaries. Never claim millisecond accuracy beyond the frame rate or alignment evidence. Avoid covering faces, essential screen content, or captions, and avoid cuts made solely to increase activity.

Deliver only what was actually produced. Distinguish a plan, preview, and final render. State what was inspected, unresolved quality issues, exact output specifications, and any remaining dependency or source requirement. A successful command or routing test alone is not proof of professional editing quality.
