# Free local speaker cutouts

Cutout means separating a person's silhouette from the background, not a rectangular crop of their face. This file provides a workflow the executing agent implements in the editing workspace; it ships no processing code or model. Do not claim that arbitrary footage can be isolated accurately by a simple crop command.

The visible foreground is **only the actual person**. Do not place a square/rectangular image, backing card, frame, filled mask background or reserved rectangular empty area around the extracted subject. A rectangular alpha intermediate is normal storage; every non-subject pixel must remain transparent when composited. The full-canvas graphic background continues behind the person and through all real transparent negative space, including gaps inside the person's bounding box.

## Choose from the actual footage and installed tools

1. Reuse a trustworthy user-supplied alpha video or mask sequence, verifying exact source/timestamp correspondence and edges.
2. For a genuinely controlled green/blue screen, use a local chroma-key workflow with careful spill handling. Inspect matching clothing, reflections, motion blur and hair; keying an arbitrary room by color is not a valid substitute.
3. For ordinary backgrounds, use an available free local video-matting/segmentation engine suitable for the hardware and allowed use. Examples to investigate at execution time include temporally aware human matting, or the local background-removal path documented in [HyperFrames](https://github.com/heygen-com/hyperframes/blob/main/skills/media-use/audio/references/remove-background.md). Do not install its paid media resolver or call HeyGen APIs. Check the installed command/version, local provider, model source and license before using it; do not assume one CLI or model exists on every host.
4. The agent may write its own local processing code to apply a suitable model, track masks or perform manual/keyframed rotoscoping for manageable footage. All generated code and dependencies belong to the video workspace. Hand-drawn masks must follow real motion and be reviewed through occlusion; a static outline, generic oval or generated replacement person is not an acceptable cutout.

Start with a difficult representative interval: moving hands, loose hair, motion blur, similar foreground/background colors and occlusion. Compare free local options on this interval before processing the full video. Ask only for missing authorization for large local dependencies/model downloads; honor authorization already given. Keep a valid Split/Overlay pipeline independent of cutout tool availability.

## Preserve original detail and time

Use the original RGB frames as the appearance reference. Where possible, infer a matte and composite against original-resolution RGB, instead of repeatedly re-encoding or upscaling a small foreground. Preserve frame presentation timestamps, dimensions, rotation, color and source-to-output mapping. A model's working resolution is not a reason to reduce the final person's RGB resolution. Inspect the matte's effective edge resolution honestly.

Maintain temporal state across contiguous video chunks when the engine needs it; handle scene cuts deliberately. For image-only segmentation, explicitly inspect temporal instability and use justified temporal refinement; independently clean-looking frames can still flicker. Never promise zero jitter or perfect hair merely because a model is popular.

Keep a mask/foreground intermediate with real alpha, using a locally supported format such as PNG sequence, appropriate VP9 alpha WebM or ProRes 4444. Verify alpha through the actual decoder/compositor, including on bright and dark backgrounds. H.264 MP4 is not the transparent intermediate; it can be the final opaque composite. Account for straight versus premultiplied alpha, edge color spill and dark/bright halos. Export quality settings improve encoding, not a defective segmentation boundary.

For a portrait/Reel place the silhouette lower with primary explanation above, as in [Compositions](editing-styles.md). Size from real body/gesture detail, not a fixed square or 50/50 divider. Let hands/hair extend naturally and reflow graphics around them. Do not hide body parts to keep the foreground below a hard boundary. In horizontal work choose placement from that scene while keeping the same unboxed alpha treatment.

Plan occupied space from the actual time-varying alpha, not just a face detector or bounding rectangle. A modest feather/safety margin may protect hair and gestures; it must not expand into an opaque panel or exclude the whole lower canvas. Animate the full background behind the silhouette. Put labels in safe transparent gaps only when their complete display interval remains readable; otherwise reflow or time them, while nonessential background graphics may pass behind the person. Check alpha/RGB/time correspondence and changing background contrast together.

Choose background palette and contrast from the topic, actual source lighting, skin/hair/clothing and other protected content using [Visual planning](visual-planning.md). No automatic blue/navy background. Avoid losing green clothing against green graphics, light hair against bright surfaces or dark clothing against deep backgrounds merely to match a generic palette. Recheck separation throughout moving graphics; do not repair contrast by altering the real person's appearance.

Use one original narration owner. Mute cutout/background copies so there is no echo. Verify mask, foreground and speech synchronization at the start, middle, end and scene boundaries. Never freeze, loop or regenerate a speaking presenter to conceal a processing failure.

## Quality decision

The job plan's Cutout review list includes three named playback backgrounds before a full render: the actual animated scene, a diagnostic light background and a diagnostic dark background. Review alpha/gesture/edge behavior on all three at delivery size and normal speed; record them separately as planned, passed, failed or not run with interval/file evidence. A general promise to "check contrast" is not that complete diagnostic plan.

Review real-time playback and difficult frames at delivery resolution on the actual moving background plus contrasting diagnostic backgrounds. Inspect a frame with hands/arms spread: correctly transparent gaps inside its bounding box must show the background, not a rectangle, and safe background graphics must continue behind/around it. Inspect the full silhouette and any safe text across motion. Reject visible rectangular backing/borders, a box-shaped matte or unnecessarily reserved box, missing fingers/body regions, clipped hair, clothing holes, crawling edges, flicker, halos, color mismatch, soft faces and sync errors. Avoid erosion, feathering or beauty filters that conceal defects by damaging the person.

Try targeted repair or another available free local method. If the result still fails, save a clearly labeled preview and report the exact limitation and options (better source, user-supplied matte, further local work). Do not fall back to a paid service, change to Split/Overlay without permission, or present a failed matte as final. Continue passing independent variants from the actual requested set: unnarrowed All can complete four Split/Overlay variants with two Cutouts incomplete; horizontal-only All can complete two with one Cutout incomplete. Retain every requested row and its actual status.

This guidance draws on the inspected HyperFrames local cutout workflow; it does not require HyperFrames as the composition engine. Model repositories such as [RVM](https://github.com/PeterL1n/RobustVideoMatting) are optional runtime research references, not bundled instruction skills or guaranteed solutions.
