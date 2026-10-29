# Intent, input roles and selection

Read this before an actual edit. Resolve intent from the prompt, explicit preset and input labels. Explanation, installation, authoring and planning-only requests do not start processing. Version 3 replaces the unconditional v2 two-question gate with Reference/Auto direction; Manual retains deliberate user selection.

## Identify inputs

Record each input's role: **source target**, **style reference**, **supporting asset**, or **unknown**. A source is edited; a reference is observed; an asset is considered for use with rights evidence. A file has two roles only when explicitly requested. Map references to sources, including shared references and per-source overrides. Resolve ambiguous unlabeled files before dispatch: "Which file should I edit, and which is the example?" Do not infer roles from filename order alone. A lone designated reference does not supply a source.

Preserve source identities even when basenames match. References do not contribute to source-job or output counts. A batch means independent sources unless a combined edit is requested. Clear montage/combination instructions establish grouping; do not repeat authorization questions they already answer.

## Direction, composition and treatment

| Direction | Predicate | Behavior |
| --- | --- | --- |
| Reference | An explicitly designated sample guides this source | Inspect source and sample; use [reference-analysis.md](reference-analysis.md) |
| Auto | No applicable designated reference and no request for Manual | Inspect source; use [auto-direction.md](auto-direction.md) |
| Manual | User explicitly wants to choose missing settings | Honor supplied details; ask missing creative choices below |

An explicit direction wins. Auto plus a sample may mean the sample is an asset or unused input; resolve a material ambiguity rather than assuming a match request. Manual can use a reference for unspecified aesthetics after its settings are answered. An inaccessible required reference remains a Reference gap; no silent switch to Auto. Use an already authorized fallback and record when it applies.

Composition describes geometry: `adaptive`, `split`, `cutout`, `overlay`. Treatment describes typography, pacing, graphics, motion, color and sound. A sample's "style" may describe either; do not interpret every style adjective as a fixed composition. Editing permission separately describes allowed changes to the source.

## Resolve dimensions with evidence

For each dimension apply: latest clear user instruction > explicitly user-selected preset default > applicable reference within constraints > Auto decision from source. Explicit settings remain fixed in every direction. Automatic host matching does not establish a selected preset; retain actual prompt settings and resolve missing choices through Reference/Auto, or Manual when requested.

Resolve shape from a clear user destination/ratio, then preset, then suitable reference, then source display aspect. Preserve square or other native shapes when no stronger choice exists. "Professional" or "YouTube" alone does not imply a Reel. Where a reference conflicts with no-crop/readability requirements, fit the full source and adapt graphics; if that is unusable, resolve the concrete tradeoff. Record the reference deviation. Presets retain their named 16:9/9:16 shape unless overridden.

| Explicit entry | Default output set |
| --- | --- |
| `omni-edit-pro` | One chosen output per source; Reference/Auto with Adaptive available |
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

Reference/Auto do not ask these routine questions. They may ask for a missing source/location/workspace, ambiguous roles, contradictory instructions or a material low-confidence choice that evidence cannot settle. Announce reasonable assumptions and proceed with reversible previews when no blocker exists. Do not turn every creative choice or preview into a new approval gate.

## Handoff

Before production dispatch record source/reference/asset IDs, mappings, direction/treatment/composition, output dimensions and variant set, portrait ordering or override, authority, per-source palette/contrast rationale, graphic/motion/transition coverage and decision provenance. Narrow analysis may precede creative selection in Reference/Auto; final composition/render dispatch waits for it. Reuse verified analysis, ask common batch questions once, and preserve choices across handoffs/resume.
