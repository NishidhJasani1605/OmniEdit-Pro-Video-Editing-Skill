# Quality assurance and delivery evidence

Use both automated inspection and human-style viewing/listening. Passing a build, parsing JSON, or following the skill's route does not establish editorial quality.

## Before rendering

Check the intended source streams and timeline mode. In continuity mode, ensure every original dialogue interval maps once, in order, at unchanged speed and with original pauses. Confirm that the original base footage is continuous where applicable, including beneath full-screen B-roll. Check audio ownership so narration is neither duplicated nor accidentally muted.

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

Audit cue start, start+1, end-1 and end frames where valid, especially for nested sequences and caption replacement. Sparse frame sampling complements playback; it cannot guarantee absence of every flash or dropped word. A transcript comparison helps locate omissions but cannot prove exact speech preservation because recognition itself can be wrong. For unchanged narration, compare source/output waveform timing at multiple points and investigate deviations beyond expected encode or gain differences.

An example full decode check with installed FFmpeg is:

```text
ffmpeg -v error -i "out/final.mp4" -map 0:v:0 -map 0:a? -f null -
```

Adapt stream selection for audio-only outputs. Successful decoding does not certify lip-sync, rights, or design. Listen through the final tail and inspect actual final frames; container duration alone can hide clipped speech or an unintended frozen ending.

## Release decision

Fix material failures and rerender the affected preview, then the final if needed. Recheck adjacent intervals and dependent layouts; avoid repeating every expensive test when a local correction cannot affect them. If no visual or audio review tools are available, state that limitation and provide review clips with exact timestamps for user assessment. Do not describe an uninspected export as fully quality-verified.

Record each check as passed, failed or not run, with the file/version and concrete evidence. Report unresolved problems plainly, along with the smallest next action. An incomplete preview can still be useful, but label it accurately.

Source: [FFmpeg documentation](https://ffmpeg.org/ffmpeg.html).
