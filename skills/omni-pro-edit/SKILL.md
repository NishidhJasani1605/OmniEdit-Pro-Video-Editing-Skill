---
name: omni-pro-edit
description: Edit supplied videos with OmniEdit Pro; choose horizontal or vertical and Split, Cutout or Overlay through two simple questions when missing.
license: MIT
metadata:
  author: NishidhJasani1605
  version: "2.0.0"
---

# omni-pro-edit

No preset choices are fixed. Resolve orientation and style from the user prompt; ask only for missing choices.

For an editing request, load the [shared OmniEdit Pro workflow](../omni-edit-pro/SKILL.md) and follow its selected-style, framing, speech, free/local processing, per-video team and delivery rules. Carry the preset above into that workflow; loading the shared skill does not reset choices. Resolve clear user overrides through its selection rules.

This preset requires the sibling `omni-edit-pro` folder from the same release. If the shared workflow cannot be read, report the incomplete installation and stop before processing; do not invent a reduced workflow or fetch an unrelated skill. Install the core and this preset together, or the complete suite.

The package contains instructions only. Generate all editing code/media in the chosen workspace. Checked exports belong under `Final Output Videos/<video-id>/`; previews and unfinished outputs stay under `Working Files`. An explanation or installation request does not start video processing.
