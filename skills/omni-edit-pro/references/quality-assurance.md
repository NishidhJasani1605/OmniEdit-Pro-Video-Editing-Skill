# Quality assurance and delivery evidence

Use both automated inspection and human-style viewing/listening. Passing a build, parsing JSON, or following the skill's route does not establish editorial quality.

The independent reviewer verifies both compliance with the selected format/style and the viewing/listening result. Review each output variant; a horizontal pass does not certify its vertical reflow. Use [Editing styles](editing-styles.md), [Local cutouts](local-cutout.md) and [Delivery](delivery.md) as acceptance contracts.

## Before rendering

Check the intended source streams and timeline mode. In continuity mode, ensure every original dialogue interval maps once, in order, at unchanged speed and with original pauses. Confirm that the original base footage is continuous where applicable, including beneath supporting visual layers allowed by the selected style. Check audio ownership so narration is neither duplicated nor accidentally muted.

Validate integer frame bounds, positive event durations, exact composition duration, source-time mappings, existing asset IDs, captions and layer ordering. Check cumulative duration and transition overlap if the user authorized an edited montage; transitions can change runtime. Ensure external assets have resolved rights and required credits. Remove placeholders before declaring a final output.

## Inspect preview and final

| Area | Evidence to collect | Failures to fix |
| --- | --- | --- |
| Narrative | Compare source and output at beginning, middle, end and every changed region; review full output | Missing/repeated/reordered words, unintended pauses removed, clipped tail |
| Sync | Listen and watch lip movements and cue boundaries; compare difficult words to waveform/source | Constant offset, drift, concept arriving too early/late |
| Captions | Read at delivery size and playback speed; inspect every cue and line-break change | Wrong names/numbers/negations, missing glyphs, poor reading time, face overlap |
| Layout | View all layout states and boundary frames at intended aspect ratios | Cropped faces/demo content, clipped text, obstructed labels, unsafe UI zones |
| Motion | Watch entries, holds, exits and transitions at normal speed | Single-frame flashes, jitter, arbitrary cuts, overshoot, incomplete animation |
| Assets/color | Inspect downloaded media and rendered composites | Incorrect context, stretched clips, watermarks, mixed color transforms, misleading graphics |
| Audio | Listen on useful monitoring equipment and measure against selected targets | Echo, clipping, clicks, pumping, music masking, channel loss |
| Technical | FFprobe plus an end-to-end decode of the final file | Wrong codec/FPS/dimensions, corruption, unexpected stream start or duration |
| Framing/person size | Compare matching source/output times at delivery size, including gesture extremes | Cover-fit crop, punch-in, stretched source, tiny presenter or enlarged soft face |
| Cutout | Watch edge motion and alpha composites on contrasting backgrounds | Missing hands/hair, flicker, holes, halos, color spill or mask/RGB offset |
| Selection/delivery | Reconcile requested pairs, actual jobs and verified export paths | Wrong style, omitted variant, duplicate output or candidate labeled final |

Audit cue start, start+1, end-1 and end frames where valid, especially for nested sequences and caption replacement. Sparse frame sampling complements playback; it cannot guarantee absence of every flash or dropped word. A transcript comparison helps locate omissions but cannot prove exact speech preservation because recognition itself can be wrong. For unchanged narration, compare source/output waveform timing at multiple points and investigate deviations beyond expected encode or gain differences.

An example full decode check with installed FFmpeg is:

```text
ffmpeg -v error -i "out/final.mp4" -map 0:v:0 -map 0:a? -f null -
```

Adapt stream selection for audio-only outputs. Successful decoding does not certify lip-sync, rights, or design. Listen through the final tail and inspect actual final frames; container duration alone can hide clipped speech or an unintended frozen ending.

## Release decision

Fix material failures and rerender the affected preview, then the candidate final if needed. Recheck adjacent intervals and dependent layouts; avoid repeating every expensive test when a local correction cannot affect them. If visual or audio review is unavailable, mark the candidate needs-review, keep it in `Working Files`, and provide clips/intervals for user assessment. Do not promote an uninspected export to `Final Output Videos` or call it verified. User review can supply the missing evidence; lack of review cannot silently count as a pass.

Record each check as passed, failed or not run, with the file/version and concrete evidence. Report unresolved problems plainly, along with the smallest next action. An incomplete preview can still be useful, but label it accurately.

Source: [FFmpeg documentation](https://ffmpeg.org/ffmpeg.html).
