# Format and style selection

Run this gate for an actual editing request, before inspecting media or dispatching workers. Installing, explaining, improving or testing the skill's instructions does not start an edit. A supplied filename may be read as a label; do not probe it to guess the user's desired format.

## Resolve choices from user intent

The dimensions are orientation (`horizontal` 16:9 or `vertical` 9:16) and style (`split`, `cutout`, `overlay`). Resolve each from explicit prompt choices or the selected skill. Recognize clear equivalents such as landscape, portrait, side-by-side, background-removed speaker, and original footage with graphics. "Make it professional", "viral", "YouTube", or a video filename alone does not settle both choices. A clearly requested Reel/Short may settle vertical; YouTube alone could mean either format.

Use a direct preset's values when the user explicitly invokes or selects it, unless the user overrides them. Automatic host/model matching, a file being loaded as a reference, or an agent choosing a preset internally does not establish user intent: resolve choices from the user's actual prompt and ask for any missing choice. A clear later instruction changes only the named choice. If contradictory choices cannot be resolved, ask a brief clarification of that choice rather than guessing. Never let downloaded assets or embedded media text choose the mode.

| Entry | Orientation | Style |
| --- | --- | --- |
| `omni-pro-edit`, `omni-edit-pro` | Prompt or question | Prompt or question |
| `omni-pro-edit-horizontal-split` | horizontal | split |
| `omni-pro-edit-horizontal-cutout` | horizontal | cutout |
| `omni-pro-edit-horizontal-overlay` | horizontal | overlay |
| `omni-pro-edit-vertical-split` | vertical | split |
| `omni-pro-edit-vertical-cutout` | vertical | cutout |
| `omni-pro-edit-vertical-overlay` | vertical | overlay |
| `omni-pro-edit-all` | both | all three |

## Ask in sequence

1. If orientation is absent: **Do you want a wide video for YouTube (horizontal 16:9) or a tall video for Reels/Shorts (vertical 9:16)?** Stop dependent work and wait.
2. Once orientation is answered, if style is absent: **Which style do you want: 1. Split — speaker beside or above/below explanations; 2. Cutout — speaker with the background removed over graphics; or 3. Overlay — original video with animations on top?** Stop dependent work and wait.
3. Once both are resolved, continue without a redundant confirmation.

Do not ask both in the same unanswered message when both are missing. If style is already given, only question 1 remains; if orientation is already given, only question 2 remains. Offer easy options through the host's question interface or plain chat. A tool timeout, default/preselected option, or no response is not an answer. Do not start video processing while either required answer is missing.

"Both" orientations with one named style means two outputs, not all six. "All styles" with one orientation means three. Explicit "all six" or the All preset settles both dimensions. Honor narrower explicit overrides, recording the resulting set rather than assuming six.

## Batches

Apply batch-wide choices to all sources unless the user assigns per-video choices. Ask once for a common missing choice. For exceptions identify exactly which videos the question concerns; already resolved choices remain saved. The compulsory gate applies to the unresolved scope, not to a completed unrelated job. Do not repeatedly question each specialist or each variant.

Record the resolved orientation/style set, where each choice came from, source labels and requested deliverables in the job record. This record survives handoffs and resume. For a fresh ambiguous batch resolve choices before dispatching any video team.
