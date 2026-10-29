---
name: omni-pro-edit-horizontal-overlay
description: Edit supplied videos in horizontal 16:9 Overlay layout retaining original footage with animations. Direct OmniEdit Pro preset with per-video teams.
license: MIT
metadata:
  author: NishidhJasani1605
  version: "3.1.2"
---

# omni-pro-edit-horizontal-overlay

Preset selection when explicitly chosen by the user: orientation = **horizontal**; style = **overlay**. These choices are already answered. Do not ask the two selection questions unless the user explicitly clears a choice or gives an unresolved conflicting instruction.

Apply these preset values only when the user explicitly invokes or selects this skill. If the host/model matched it automatically, loading this file alone does not select this preset: use the actual prompt and resolve missing choices through Reference/Auto, or Manual if explicitly requested.

For an editing request, load the [shared OmniEdit Pro workflow](../omni-edit-pro/SKILL.md) and follow its selected-style, framing, speech, free/local processing, per-video team and delivery rules. Carry the preset above into that workflow; loading the shared skill does not reset choices. Resolve clear user overrides through its selection rules.

This preset requires the sibling `omni-edit-pro` folder from the same release. If the shared workflow cannot be read, report the incomplete installation and stop before processing; do not invent a reduced workflow or fetch an unrelated skill. Install the core and this preset together, or the complete suite.

The package contains instructions only. Generate all editing code/media in the chosen workspace. Checked exports belong under `Final Output Videos/<video-id>/`; previews and unfinished outputs stay under `Working Files`. An explanation or installation request does not start video processing.
