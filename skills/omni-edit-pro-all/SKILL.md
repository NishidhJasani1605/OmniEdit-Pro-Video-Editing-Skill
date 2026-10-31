---
name: omni-edit-pro-all
description: "Use when all six OmniEdit Pro preset variants are requested for each source video: horizontal and vertical, each in Split, Cutout and Overlay."
license: MIT
metadata:
  author: NishidhJasani1605
  version: "3.3.0"
---

# omni-edit-pro-all

Preset selection when explicitly chosen by the user: **both orientations and all three styles**, producing six variants per source video. Both selection questions are already answered for that explicit selection. Preserve any clear user narrowing; never count missing Cutout variants as a complete six-output request.

Classify references and supporting assets before counting sources. They receive no exports unless separately identified as edit targets. Adaptive is not added to this set automatically. Direction can still be Reference or Auto within these fixed compositions. "Horizontal only" narrows All to three variants per source; "Overlay only" narrows it to two, changing only the named dimension.

Vertical presenter variants inherit the shared speaking-footage/silhouette-below and primary-animation-above default, including intact lower footage for Overlay and true unboxed alpha for Cutout. All variants use meaningful evolving graphics and suitable source-specific transitions/palettes. Shared source variants may keep one coherent treatment and reflow; different source jobs require individual direction rather than cloned card/blue-background edits.

Apply these preset values only when the user explicitly invokes or selects this skill. If the host/model matched it automatically, loading this file alone does not select this preset: use the actual prompt and resolve missing choices through Reference/Auto, or Manual if explicitly requested.

For an editing request, load the [shared OmniEdit Pro workflow](../omni-edit-pro/SKILL.md) and follow its selected-style, framing, speech, free/local processing, per-video team and delivery rules. Carry the preset above into that workflow; loading the shared skill does not reset choices. Resolve clear user overrides through its selection rules.

This preset requires the sibling `omni-edit-pro` folder from the same release. If the shared workflow cannot be read, report the incomplete installation and stop before processing; do not invent a reduced workflow or fetch an unrelated skill. Install the core and this preset together, or the complete suite.

The package contains instructions only. Generate all editing code/media in the chosen workspace. Checked exports belong under `Final Output Videos/<video-id>/`; previews and unfinished outputs stay under `Working Files`. An explanation or installation request does not start video processing.
