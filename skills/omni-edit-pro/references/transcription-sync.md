# Transcription, semantic cues, and frame synchronization

## Establish the clock

Choose the source timeline origin and selected audio stream before extraction. Preserve the mapping between audio samples, source presentation timestamps, and output time. Let `P0` be the source timestamp at composition time zero and `A0` the source timestamp of the first extracted audio sample. A word reported at `t_asr` seconds maps to `t_output = t_asr + A0 - P0` for an unchanged timeline. Record any additional known delay explicitly. Test the mapping at the beginning, middle and end; do not blindly reset streams with different start times independently.

Extract a speech-friendly audio working copy without cutting silence or changing duration. If extraction already includes leading silence back to the composition origin, do not add the source audio offset again. A recognizer may require mono PCM or resampling; retain the original full-quality narration for the edit. Speech detection used inside recognition is not permission to remove pauses from the video.

## Transcribe and verify

Reuse a reliable supplied transcript where available. Otherwise choose an installed recognizer suited to the source language, hardware, noise and privacy constraints. WhisperX can add language-dependent forced alignment; whisper.cpp offers timestamp options whose accuracy must be evaluated for the selected build. Inspect actual output fields and units rather than assuming seconds or true word boundaries. Optional speaker diarization is useful only when speaker identity affects the edit.

Preserve spoken wording, order and language. Review names, numbers, units, negation and technical terms against audio. Translation is a separate caption track unless requested otherwise. Keep a raw transcript and reviewed version. For each word retain an ID, text, source start/end seconds, speaker if known, alignment method, and uncertainty; absent confidence is unknown, not 100%.

Reject non-finite, negative-after-mapping, reversed, out-of-source or implausibly long intervals. Check chronological ordering within each speaker; genuine overlapping speech can overlap. Do not force unmatched punctuation or unaligned words into invented precise timestamps. Re-align corrected wording where supported; otherwise review the phrase manually. Failed language alignment, music hallucinations, or poor audio can require phrase-level captions with explicit uncertainty. Do not split a sentence evenly into fake word timings.

Map semantic cues to word IDs or reviewed phrase ranges. A cue describes the concept, why a visual helps, the relevant spoken span, its asset, and desired reveal/hold/exit. Timing follows meaning: an illustrative comparison may span a phrase rather than flash on a keyword. Verify all critical numerical, scientific, financial and health claims against the actual narration and reliable sources where verification is needed.

## Quantize once

Keep source timestamps in seconds and the composition rate as a rational `F = p/q`. Use zero-based integer frame intervals `[startFrame, endFrame)` for visual events. Preserve narration offsets at audio-sample/presentation-timestamp precision; do not round audio to the video grid. Where a compositor accepts only frame offsets, prepare or finish the audio through the same timeline with sample-accurate padding/offset handling, then verify the muxed sync. For a cue envelope choose `startFrame = floor(t_start * F)` and `endFrame = ceil(t_end * F)`; clamp to `[0, N]` and require positive duration. This policy starts at most one frame early and ends at most one frame late relative to the supplied timestamps. For a reveal that must never precede a spoken onset, use `ceil(t_onset * F)` instead and record that choice.

Choose `N = ceil(D * F)` for the required preserved timeline duration `D`, including the entire selected narration. Preserve the tail; document any subframe end padding. If source picture ends before narration, choose a deliberate hold or other planned visual, never silently truncate speech. At 30 fps the grid is about 33.3 ms; alignment error exists in addition to that grid. Rational 30000/1001 is about 33.37 ms per frame.

Use one cue ledger with `id`, `sourceId`, `wordIds`, `startFrame`, `endFrame`, `layer`, `assetId`, `layout`, and timing confidence. Validate bounds, missing assets, unintended layer collisions and caption ordering before rendering. A Remotion sequence's duration is `endFrame - startFrame`; local animation time differs from absolute composition time. Share boundary frames between adjacent captions instead of independently rounding them into accidental overlaps. Apply fades within planned intervals.

For explicitly authorized trims or rearrangements, maintain piecewise source-to-output mappings and remap transcript and cues through them. Never reuse original timestamps after a cut without mapping. Such edits override the default continuity mode only for the authorized scope.

Sources: [WhisperX](https://github.com/m-bain/whisperX), [whisper.cpp](https://github.com/ggml-org/whisper.cpp), [Remotion sequences](https://www.remotion.dev/docs/sequence).
