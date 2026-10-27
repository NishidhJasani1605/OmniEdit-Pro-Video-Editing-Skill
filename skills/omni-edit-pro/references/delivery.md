# Final outputs and safe delivery

Resolve the user's chosen editing workspace during intake under [Selection](selection.md). If no workspace can be inferred safely, ask for it. Never use an installed skill folder as the editing workspace. Use the exact folder name **Final Output Videos** unless the user explicitly requests another delivery folder. Keep originals unchanged and references read-only.

## Locations

Inside the editing workspace:

```text
Working Files/
    batch-progress.md
    video-001-topic/
        plan.md
        source-analysis/
        assets/
        project/
        previews/
        candidate-exports/
        review/
Final Output Videos/
    video-001-topic/
        video-001-topic-horizontal-split-v001.mp4
        video-001-topic-horizontal-cutout-v001.mp4
        video-001-topic-horizontal-overlay-v001.mp4
        video-001-topic-vertical-split-v001.mp4
        video-001-topic-vertical-cutout-v001.mp4
        video-001-topic-vertical-overlay-v001.mp4
```

This is an output convention, not a scaffold shipped with the skill. Create only folders and variants needed for the actual task. The six illustrated files apply to unnarrowed All; Adaptive is not added to that default set. A reference or supporting asset does not create a source delivery folder. Adapt the extension to an explicitly requested format. Keep captions, editable project, credits, reference observations/comparisons and review notes in working/project folders and link them separately.

Adaptive can use the named shape for 16:9/9:16 outputs, for example `video-001-topic-horizontal-adaptive-v001.mp4`. For other resolved shapes use a portable explicit ratio token, for example `video-001-topic-aspect-1x1-adaptive-v001.mp4` or `video-001-topic-aspect-4x3-adaptive-v001.mp4`. Record exact pixel dimensions, display aspect and any sample-aspect metadata in the plan/report; a filename token does not replace those facts. Use the final resolved shape, whether source-native or explicitly overridden, and avoid colons or ambiguous orientation labels for custom ratios.

## Identity and versions

Create safe stable video IDs with a batch-unique prefix and sanitized topic/basename. Identical basenames from different directories get distinct IDs tied to their source identities. Do not merge them accidentally. Keep filename components portable across operating systems; never interpret user filenames as commands. Record the original source path mapping privately in the batch record.

Record mode, reference mapping/coverage, selected treatment, composition, resolved variant set/settings and decision provenance before creating variant/render jobs. Reserve paths from that set before export. If a name exists, preserve it and increment the version or choose a unique batch directory; never silently overwrite. The lead owns final-file promotion. Workers render to their own candidate paths and report them. Do not let multiple tasks promote the same output.

## Final promotion gate

Render the full candidate in `Working Files`, then inspect it according to [Quality assurance](quality-assurance.md), including actual source/variant comparison, normal-speed motion, listening where audio exists and required treatment/reference assessment. Only after required checks pass, place the verified file in `Final Output Videos/<video-id>/`. Reconfirm the copied/moved file identity and readability. A tool exiting successfully, a thumbnail or a short test alone is insufficient.

Missing required audiovisual or reference-comparison review means `needs-review`, not completed: keep the export in the working area and provide the exact file/intervals for review. Unavailable required references cannot become a claimed match or a silent Auto fallback. Failed, placeholder, unrendered and partially checked outputs stay outside the final folder. Keep earlier verified finals if a later revision fails.

## User report

Report each source/requested variant with status and an exact clickable output path when it exists. State mode/treatment/composition; dimensions/aspect, FPS, duration and format; preservation or authorized edits; and actual full-output viewing, motion, listening and technical checks. Include portrait ordering or explicit override, per-source graphic/motion/transition rationale, topic/subject contrast palette and Cutout silhouette/negative-space review where relevant. In Reference include mappings, coverage, matched/adapted/unassessed attributes, shared-default adaptations and gaps. In Auto give the source-grounded direction reason. Keep measured facts separate from design judgments.

Link requested captions, editable project, credits and review evidence separately. Do not count a preview as a final or missing Cutout as another style. Reconcile the actual resolved set: unnarrowed All has six entries per source; All, horizontal only has three. References/assets do not enter those counts. Continue valid independent outputs when another is blocked, but label the batch partial until every requested variant has passed its required checks. No source, routing or instruction-only test establishes rendered-video quality.

Creating a final file does not authorize uploading or publishing it.
