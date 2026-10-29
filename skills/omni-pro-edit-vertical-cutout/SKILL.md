---
name: omni-pro-edit-vertical-cutout
description: Edit supplied videos in vertical 9:16 Cutout layout with a locally isolated speaker over graphics. Direct OmniEdit Pro preset with per-video teams.
license: MIT
metadata:
  author: NishidhJasani1605
  version: "3.1.2"
---

# omni-pro-edit-vertical-cutout

Preset selection when explicitly chosen by the user: orientation = **vertical**; style = **cutout**. These choices are already answered. Do not ask the two selection questions unless the user explicitly clears a choice or gives an unresolved conflicting instruction.

Portrait presenter default: speaking footage or true Cutout silhouette below, primary dynamic animation above. Keep intact source/background in Split and Overlay; Cutout uses only real alpha over the full animated canvas without a visible or reserved rectangular box. Honor an explicit placement override. Choose motion, transitions and palette from this source rather than a repeated blue/card template.

Apply these preset values only when the user explicitly invokes or selects this skill. If the host/model matched it automatically, loading this file alone does not select this preset: use the actual prompt and resolve missing choices through Reference/Auto, or Manual if explicitly requested.

For an editing request, load the [shared OmniEdit Pro workflow](../omni-edit-pro/SKILL.md) and follow its selected-style, framing, speech, free/local processing, per-video team and delivery rules. Carry the preset above into that workflow; loading the shared skill does not reset choices. Resolve clear user overrides through its selection rules.

This preset requires the sibling `omni-edit-pro` folder from the same release. If the shared workflow cannot be read, report the incomplete installation and stop before processing; do not invent a reduced workflow or fetch an unrelated skill. Install the core and this preset together, or the complete suite.

The package contains instructions only. Generate all editing code/media in the chosen workspace. Checked exports belong under `Final Output Videos/<video-id>/`; previews and unfinished outputs stay under `Working Files`. An explanation or installation request does not start video processing.
