# Final outputs and safe delivery

Resolve the user's chosen editing workspace after selection. If no workspace can be inferred safely, ask for it. Never use an installed skill folder as the editing workspace. Use the exact folder name **Final Output Videos** unless the user explicitly requests another delivery folder.

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

This is an output convention, not a scaffold shipped with the skill. Create only folders and variants needed for the actual task. The six illustrated files apply to All mode. Adapt the extension to an explicitly requested delivery format. Keep captions, editable project, credits and review notes in the job's working/project folders and link them separately.

## Identity and versions

Create safe stable video IDs with a batch-unique prefix and sanitized topic/basename. Identical basenames from different directories get distinct IDs tied to their source identities. Do not merge them accidentally. Keep filename components portable across operating systems; never interpret user filenames as commands. Record the original source path mapping privately in the batch record.

Reserve output paths before export. If a name exists, preserve it and increment the version or choose a unique batch directory; never silently overwrite. The lead owns final-file promotion. Workers render to their own candidate paths and report them. Do not let multiple tasks promote the same output.

## Final promotion gate

Render the full candidate in `Working Files`, then inspect it according to [Quality assurance](quality-assurance.md). Only after required checks pass, place the verified file in `Final Output Videos/<video-id>/`. Reconfirm the copied/moved file identity and readability. A tool exiting successfully, a thumbnail or a preview alone is insufficient.

Missing audiovisual review means `needs-review`, not completed: keep the export in the working area and provide the exact file/intervals for review. Failed, placeholder, unrendered and partially checked outputs stay outside the final folder. Keep earlier verified finals if a later revision fails.

## User report

Report each requested video/variant with status and an exact clickable output path when it exists. State dimensions, frame rate, duration, format, preserved-dialogue status, checks performed and any remaining limitations. Link requested captions, editable project and credits separately. Do not count a preview as a final or a missing Cutout as another style. For All mode, reconcile six requested entries per video against actual files and evidence. Continue valid independent outputs even when another is blocked, but label the batch partial until every requested variant is complete.

Creating a final file does not authorize uploading or publishing it.
