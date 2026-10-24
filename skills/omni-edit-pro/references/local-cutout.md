# Free local speaker cutouts

Cutout means separating a person's silhouette from the background, not a rectangular crop of their face. This file provides a workflow the executing agent implements in the editing workspace; it ships no processing code or model. Do not claim that arbitrary footage can be isolated accurately by a simple crop command.

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

Use one original narration owner. Mute cutout/background copies so there is no echo. Verify mask, foreground and speech synchronization at the start, middle, end and scene boundaries. Never freeze, loop or regenerate a speaking presenter to conceal a processing failure.

## Quality decision

Review real-time playback plus difficult frames at delivery resolution. Reject missing fingers/body regions, clipped hair, holes in clothing, crawling edges, flicker, halos, color mismatch, soft faces, and motion/sound offset. Avoid heavy erosion, feathering or beauty filters that hide defects by damaging the person.

Try targeted repair or another available free local method. If the result still fails, save a clearly labeled preview and report the exact limitation and options (better source, user-supplied matte, further local work). Do not fall back to a paid service, change to Split/Overlay without permission, or present a failed matte as final. In All mode, continue the four independent Split/Overlay variants and report the two Cutout variants incomplete.

This guidance draws on the inspected HyperFrames local cutout workflow; it does not require HyperFrames as the composition engine. Model repositories such as [RVM](https://github.com/PeterL1n/RobustVideoMatting) are optional runtime research references, not bundled instruction skills or guaranteed solutions.
