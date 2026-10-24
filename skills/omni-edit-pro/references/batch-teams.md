# Per-video teams and batch work

Read after [Selection](selection.md). This is a native-agent coordination workflow, expressed as instructions. No crewAI service, orchestration library, shell helper or external skill is required. Roles are task assignments with relevant context, not a claim of certified expertise or special model capabilities.

## Inventory and ownership

Give every source a stable unique ID, even when two input files have the same basename. Record original absolute source path, identity/fingerprint, selected streams, modes and job status. Before a missing source is located, retain a provisional label with needs-input status; verify its source identity before processing or reusing cached work. Treat each supplied video independently unless the user expressly requests a combined edit. Multiple input clips are not implicit permission for a montage.

Use `<editing-workspace>/Working Files/<video-id>/` for that job's plan, transcript, assets, compositions, previews and candidate exports. Keep source files unchanged. Assign one owner to each writable artifact; a video lead alone integrates the authoritative timeline. Shared resources are read-only once verified. Do not make different teams edit one shared composition or progress file concurrently; report updates to the batch coordinator.

Maintain a compact batch record containing job/variant IDs, team or task handles, owner, dependencies, output paths, state, last evidence and next action. States include waiting-selection, queued, running, needs-input, preview-ready, reviewing, needs-review, needs-repair, completed, failed and blocked. A queue entry or an agent's optimistic message is not completion evidence.

## Native team dispatch

Check the actual host's exposed subagent tools, allowed nesting, concurrency and permissions. Do not infer team support from the model brand or IDE name. With native support, assign a dedicated lead/team context per video and create specialist tasks for its stages:

| Role | Inputs and deliverable |
| --- | --- |
| Video lead | Brief and source facts; owns plan, dependency order, timeline integration and variant status |
| Speech/captions | Selected audio and source origin; reviewed transcript, confidence and timing cues |
| Visual direction/assets | Reviewed ideas and user style; shot plan, design vocabulary, asset rights |
| Layout/animation | Approved plan, timing and assets; composition and readable motion |
| Cutout, only when selected | Original frames and geometry; local matte/foreground plus edge and temporal checks |
| Audio/export | Timeline and original sound; mix, representative previews and candidate final |
| Independent reviewer | Actual source/output, brief and evidence; requirements and audiovisual quality verdicts |

Every substantive stage gets a scoped specialist assignment; a lead does not silently do all work and call that a team. Specialists can run sequentially as slots free up. If nested agents are unavailable, the top-level coordinator dispatches the specialists and links them to their video lead's job. Reserve capacity for coordination/review; do not occupy every slot with leads waiting for children. Launch only as many video teams as the host can sustain and queue the rest. Limit GPU/model/render concurrency independently of agent count.

If no subagent tool exists, explain that genuine teams cannot be created. Ask whether to proceed with one agent applying the same role checklists, or wait for a team-capable environment. Until answered, preserve the job as needs-input; do not fabricate agents or silently reduce the execution mode. A prior user authorization for solo fallback is sufficient.

## Assignments and dependency order

Each worker brief includes video/variant ID, role, exact input paths/versions, relevant instruction references, objective, constraints, owned output paths, dependencies and required evidence. Give only needed context. Prohibit cross-job writes and unauthorized extra workers. Preserve the user's model settings unless they requested a change.

After source inspection, speech analysis, source-matte investigation and media technical checks may proceed independently. Speech-dependent visuals wait for reviewed cues; animation waits for approved geometry/assets; final export waits for integrated timing and audio. Separate videos may run concurrently. Within one video, independent asset research and graphic development can run in parallel when outputs are separate.

Use actual process/task handles to observe running work. A polling timeout does not prove failure. Verify the task or process status before restarting to avoid duplicate renders. On resume, read the batch record and inspect existing artifacts/handles before reassigning anything. Reuse verified analysis and completed outputs when source and settings have not changed.

## Review and repair

Workers report actual paths, changes, checks performed, unverified claims and blockers. The lead checks integration; a distinct reviewer evaluates both (1) requested behavior and (2) audiovisual quality using [Quality assurance](quality-assurance.md). A good-looking preview does not excuse missing speech or the wrong style. A technical pass does not excuse unreadable animation.

Send concrete failed intervals and evidence back to the responsible specialist. Recheck repaired output and affected boundaries. After two targeted failures on the same cause, diagnose a different free/local path or surface the smallest unresolved need; never promote a failed variant just to clear the queue. Continue independent jobs. Report material gaps without inventing success.

## All mode

For each video generate exactly the six orientation/style pairs unless explicitly narrowed. Reuse verified source inspection, transcript, original narration, cleared assets and compatible matte across variants of that same source. A source or transcript change invalidates dependent work. Plan layouts independently: vertical is a reflow, not a crop of the horizontal export. Review all six outputs separately.

If cutout cannot pass, complete and deliver the four valid Split/Overlay variants when possible; keep the two Cutout variants failed or needs-input and the whole All request incomplete. Never quietly substitute another style, omit failed rows, or relabel four outputs as six.
