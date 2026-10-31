# Intent, input roles and selection

Read this before an actual edit. Resolve intent from the prompt, explicit preset and input labels. Explanation, installation, authoring and planning-only requests do not start processing. Version 3 replaces the unconditional v2 two-question gate with Reference/Auto direction; Manual retains deliberate user selection.

## Identify inputs

Record each input's role: **source target**, **style reference**, **supporting asset**, or **unavailable**. A source is edited; a reference is observed; an asset is considered for use with rights evidence. A file has two roles only when explicitly requested. Explicit labels and corrections win. For unlabeled inputs use the automatic classification below without stopping to ask which file is the source or reference. A lone designated reference does not supply a source.

Preserve source identities even when basenames match. References do not contribute to source-job or output counts. A batch means independent sources unless a combined edit is requested. Clear montage/combination instructions establish grouping; do not repeat authorization questions they already answer.

### Zero-Configuration Automatic Role Classification

When video files arrive without explicit source/reference tags, inspect them before dispatch and proceed autonomously. Use FFprobe for decoded dimensions, display aspect ratio (including rotation and sample aspect), frame rate, video duration, audio stream duration/start and stream presence. Use FFmpeg to decode 2–3 representative frames per file, spread across opening, middle and ending rather than adjacent opening frames. Respect view-only retention constraints with in-memory decoding. These frames support initial classification, not complete reference or motion review; inspect more intervals when the evidence conflicts.

| Detected role | Evidence to inspect |
| --- | --- |
| **Source Target (Raw Footage)** | Continuous single-take presenter footage with natural room/camera background and absence of pre-rendered motion graphics, title bars and burned-in captions. A raw camera/hash filename supports this classification but never overrides decoded content. Non-presenter raw/action/interface footage remains a valid source; do not invent a presenter. |
| **Vertical Reference (9:16)** | Display aspect ratio 9:16, such as 1080×1920, together with pre-rendered motion graphics, split screens, topic banners or burned-in captions. Aspect ratio alone cannot turn a raw vertical recording into a reference. |
| **Horizontal Reference (16:9)** | Display aspect ratio 16:9, such as 1920×1080, together with motion graphics, overlay cards, side scrims or lower-third captions. A widescreen raw recording remains a source. |

Log file ID, metadata, sampled timecodes, visible evidence, assignment, confidence, reference-to-source mapping and reason in the job plan. Compare subject/topic and audiovisual correspondence to map references to matching source targets. Never use input order or filenames alone. With multiple same-format references, prefer the best content match, then the most inspectable relevant treatment; log that priority. Different formats guide their own outputs and are not conflicting references to be averaged.

If 2–3 frames leave roles uncertain, extend inspection and record the best supported assignment without a role-confirmation prompt. Retain an unresolved file as a provisional source target rather than silently discarding it or treating it as a proven reference; keep that uncertainty in the plan. A lone unlabeled finished-looking video is a source unless there is evidence of another target it exemplifies. User labels, explicit destinations, selected presets and editing permissions remain authoritative. Auto classification does not authorize trimming, cropping, asset copying or source replacement. A corrupt/inaccessible file remains unavailable, not falsely classified; continue accessible independent inputs and report the access gap.

When no explicit output set/preset overrides detection, derive deliverables per source from its applicable references:

| Applicable reference formats | Automatically resolved deliverables |
| --- | --- |
| Vertical only | One **Vertical 9:16 Reel** |
| Horizontal only | One **Horizontal 16:9 Master** |
| Both vertical and horizontal | **BOTH**: one Vertical 9:16 Reel and one Horizontal 16:9 Master |
| No applicable reference | Auto direction, preserving source display aspect unless another instruction applies |

Select composition within each format from the applicable reference and source fit; this does not multiply outputs into all compositions. An explicit preset retains its selected composition/shape; explicit All still requests six pairs or its narrowed set, with references guiding the corresponding formats. References never add source jobs. Finalize and log the exact source/variant matrix and proceed without routine format or role questions.

## Direction, composition and treatment

| Direction | Predicate | Behavior |
| --- | --- | --- |
| Reference | An explicitly designated or automatically classified reference applies to this source | Inspect source and sample; use [reference-analysis.md](reference-analysis.md) |
| Auto | No applicable designated or automatically classified reference and no request for Manual | Inspect source; use [auto-direction.md](auto-direction.md) |
| Manual | User explicitly wants to choose missing settings | Honor supplied details; ask missing creative choices below |

An explicit direction wins. Explicit Auto governs its scope; log a supplied sample as unused treatment evidence or an explicitly requested asset within that scope. Otherwise automatically classified references select Reference without a role prompt. Manual can use a reference for unspecified aesthetics after its settings are answered. An inaccessible required reference remains a Reference gap; no silent switch to Auto. Use an already authorized fallback and record when it applies.

Composition describes geometry: `adaptive`, `split`, `cutout`, `overlay`. Treatment describes typography, pacing, graphics, motion, color and sound. A sample's "style" may describe either; do not interpret every style adjective as a fixed composition. Editing permission separately describes allowed changes to the source.

## Resolve dimensions with evidence

For each dimension apply: latest clear user instruction > explicitly user-selected preset default > applicable reference within constraints > Auto decision from source. Explicit settings remain fixed in every direction. Automatic host matching does not establish a selected preset; retain actual prompt settings and resolve missing choices through Reference/Auto, or Manual when requested.

Resolve shape from a clear user destination/ratio, then preset, then suitable reference, then source display aspect. Preserve square or other native shapes when no stronger choice exists. "Professional" or "YouTube" alone does not imply a Reel. Where a reference conflicts with no-crop/readability requirements, fit the full source and adapt graphics; if that is unusable, resolve the concrete tradeoff. Record the reference deviation. Presets retain their named 16:9/9:16 shape unless overridden.

| Explicit entry | Default output set |
| --- | --- |
| `omni-edit-pro` | One per applicable reference format (vertical, horizontal or both); without references one Auto output per source; Adaptive available |
| `omni-edit-pro-horizontal-split` | horizontal 16:9, split |
| `omni-edit-pro-horizontal-cutout` | horizontal 16:9, cutout |
| `omni-edit-pro-horizontal-overlay` | horizontal 16:9, overlay |
| `omni-edit-pro-vertical-split` | vertical 9:16, split |
| `omni-edit-pro-vertical-cutout` | vertical 9:16, cutout |
| `omni-edit-pro-vertical-overlay` | vertical 9:16, overlay |
| `omni-edit-pro-all` | both orientations × split/cutout/overlay: six per source |

Clear later overrides change only their named dimensions. Vertical Overlay + "horizontal instead" means horizontal Overlay. All + "horizontal only" means three per source. All + "Overlay only" means two per source; both orientations with one composition means two, not six. Adaptive is not added to All automatically. Explicit additional deliverables are counted separately; a replacement request replaces only its stated scope. Resolve contradictory choices with one brief clarification.

## Shared art-direction defaults

Apply the 3.1 defaults within the resolved output set in Auto, Reference, Manual and all presets: in vertical presenter scenes, speaking footage or true silhouette below and primary animation above; in every format, meaningful evolving graphics/animation and suitable transitions throughout; and a palette/background/motion treatment derived separately from each source. Reference observations and automatically matched presets do not silently reverse these defaults. An explicit request for a different position, exact reference placement, brand palette or deliberately still treatment replaces only the named default; do not ask again for that clear override.

Use [Compositions](editing-styles.md) for lower intact footage versus unboxed alpha, [Visual planning](visual-planning.md) for topic/subject/clothing contrast and per-source direction, and [Motion design](motion-design.md) for dynamic coverage. No routine blue/navy template or cloned batch animation. A shared brand/reference can retain recognizable elements, with source-specific timing, imagery, transitions and contrast review. Non-presenter scenes do not receive a fabricated speaking panel. These choices do not authorize source cuts/crops/speed changes.

## Editing authority

Record authority for trimming/deleting words or pauses, reordering, combining sources, cropping/zooming, speed changes, replacing full-frame footage, speech regeneration and translation. Preserve dialogue, pauses, order and timing by default; preserve the full action/walkthrough for non-speech content unless instructed otherwise. A concrete shorter/highlights/montage request authorizes necessary selection and composition within its stated limits. Record source mappings and do not ask again for those authorized actions. "Keep everything" plus an incompatible shorter runtime needs clarification.

"Like this sample" authorizes transferring observable treatment; it does not by itself authorize losing source meaning, changing a preset, deleting words, cropping protected content or copying assets. A specific request for reference-like cuts or camera moves supplies that named authority where compatible with other constraints. Never hide a conflicting preservation instruction inside the inferred look.

## Manual questions and true blockers

For explicit Manual, use supplied settings first. If orientation is missing, ask: **"Do you want a wide video (horizontal 16:9), a tall video (vertical 9:16), or the source's original shape?"** Wait. Then if composition is missing ask: **"Which composition do you want: Adaptive, Split, Cutout, or Overlay?"** Wait. Ask only the missing question; do not inspect media to infer a Manual answer. No response, timeout or preselected option is an answer. Pause only the unresolved scope.

Reference/Auto do not ask routine role or format questions. Resolve unlabeled inputs and reference-format deliverables with the zero-configuration procedure above. They may ask for a genuinely missing source/location/workspace or contradictory explicit instructions. Log evidence-based creative assumptions and proceed with reversible, reviewer-audited previews. Do not turn every creative choice or preview into a new user approval gate.

## Handoff

Before production dispatch record source/reference/asset IDs, mappings, direction/treatment/composition, output dimensions and variant set, portrait ordering or override, authority, per-source palette/contrast rationale, graphic/motion/transition coverage and decision provenance. Narrow analysis may precede creative selection in Reference/Auto; final composition/render dispatch waits for it. Reuse verified analysis, ask common batch questions once, and preserve choices across handoffs/resume.
