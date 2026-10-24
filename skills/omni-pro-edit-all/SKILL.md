---
name: omni-pro-edit-all
description: "Edit every supplied video into all six OmniEdit Pro variants: horizontal and vertical, each in Split, Cutout and Overlay, with per-video teams and checked final exports."
license: MIT
metadata:
  author: NishidhJasani1605
  version: "2.0.0"
---

# omni-pro-edit-all

Preset selection when explicitly chosen by the user: **both orientations and all three styles**, producing six variants per source video. Both selection questions are already answered for that explicit selection. Preserve any clear user narrowing; never count missing Cutout variants as a complete six-output request.

Apply these preset values only when the user explicitly invokes or selects this skill. If the host/model matched it automatically, loading this file alone does not answer the two questions: use the actual user prompt and ask for any missing choice through the shared selection rules.

For an editing request, load the [shared OmniEdit Pro workflow](../omni-edit-pro/SKILL.md) and follow its selected-style, framing, speech, free/local processing, per-video team and delivery rules. Carry the preset above into that workflow; loading the shared skill does not reset choices. Resolve clear user overrides through its selection rules.

This preset requires the sibling `omni-edit-pro` folder from the same release. If the shared workflow cannot be read, report the incomplete installation and stop before processing; do not invent a reduced workflow or fetch an unrelated skill. Install the core and this preset together, or the complete suite.

The package contains instructions only. Generate all editing code/media in the chosen workspace. Checked exports belong under `Final Output Videos/<video-id>/`; previews and unfinished outputs stay under `Working Files`. An explanation or installation request does not start video processing.
