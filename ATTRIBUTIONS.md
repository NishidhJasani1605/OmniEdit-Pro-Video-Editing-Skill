# Research and acknowledgments

OmniEdit Pro contains original instructions informed by an inspection of the following projects on **18 October 2026**. It combines general editing capabilities into one workflow. No upstream skill prose, application code, scripts, templates, images, or media are redistributed, and none of these skills must be installed to use OmniEdit Pro. This project is not affiliated with or endorsed by the upstream maintainers.

## Inspected sources

| Project and pinned revision | Actual relevant material | Rights found in that revision |
| --- | --- | --- |
| [remotion-dev/skills](https://github.com/remotion-dev/skills/tree/1441a11e95db35443bd76bb318386c0d3ca00053) | Twelve skills, including `remotion-best-practices`, `remotion-captions`, `remotion-render`, `remotion-create`, and `remotion-multimedia`; composition, captions, motion and rendering guidance | No explicit LICENSE/COPYING/NOTICE or package license grant found. Its instruction text and code are not copied. Technical guidance is independently written and linked to official API documentation. |
| [iart-ai/b-roll-skills](https://github.com/iart-ai/b-roll-skills/tree/a51e34b0a8def533759373733bde1869c21075fb) | `skills/talking-head-b-roll/SKILL.md`; narration-aware overlays, continuous speech, face regions and timing checks | [MIT, copyright 2026 iart.ai](https://github.com/iart-ai/b-roll-skills/blob/a51e34b0a8def533759373733bde1869c21075fb/LICENSE) |
| [iart-ai/motion-design-skills](https://github.com/iart-ai/motion-design-skills/tree/3c129f769d90a1328c209c386492333c9ac62312) | Nine skills including `motion-art-direction`, `animation-principles`, `shot-composition`, `color-motion`, and `remotion-video`; direction, hierarchy, composition and motion principles | [MIT, copyright 2026 iart.ai](https://github.com/iart-ai/motion-design-skills/blob/3c129f769d90a1328c209c386492333c9ac62312/LICENSE) |
| [gitethanwoo/video-editing](https://github.com/gitethanwoo/video-editing/tree/166eed9b1f391af5201a37057924593bf8f413d4) | `find-broll`, `analyze-video-editing`, `video-editing`; asset provenance, editorial evidence and quality checks | [MIT, copyright 2026 Ethan Woo](https://github.com/gitethanwoo/video-editing/blob/166eed9b1f391af5201a37057924593bf8f413d4/LICENSE). Its [NOTICE.md](https://github.com/gitethanwoo/video-editing/blob/166eed9b1f391af5201a37057924593bf8f413d4/NOTICE.md) also credits Louise De Sadeleer's MIT B-Roll Finder. |
| [ai-self-media-video-packaging-skill](https://github.com/zhouyuechuan2025-ui/ai-self-media-video-packaging-skill/tree/cfbb87843c746ceee18e8ae7c855ba536a6f32f2) | Root skill is `package-talking-head-video`; presenter framing, information layouts, line drawings and review gates. Current public-lite supports 16:9, three layouts (`title`, `card`, `flow`) and a single presenter window; OmniEdit's broader layout guidance is original. | [MIT, copyright 2026 Nana AI](https://github.com/zhouyuechuan2025-ui/ai-self-media-video-packaging-skill/blob/cfbb87843c746ceee18e8ae7c855ba536a6f32f2/LICENSE), with separate third-party terms in [NOTICE](https://github.com/zhouyuechuan2025-ui/ai-self-media-video-packaging-skill/blob/cfbb87843c746ceee18e8ae7c855ba536a6f32f2/NOTICE) |

## Integration decisions

Upstream tools differ: Canvas/Playwright/FFmpeg, Remotion, After Effects, and legacy HyperFrames appear in the inspected projects. OmniEdit uses one Remotion composition timeline with FFmpeg preparation/finishing instead of inheriting competing engines, scripts, model downloads or sibling-skill calls.

Fixed B-roll lead/lag offsets and maximum presenter-only durations are replaced with reviewed semantic cues and frame quantization. Beat cuts and retiming apply only when the user authorizes that kind of edit. Layout changes preserve the continuous presenter clock. Aspect ratios, caption styles and languages come from the actual brief. Upstream approval gates are not imported as mandatory pauses.

## Separate licenses

The [MIT license](LICENSE) applies to OmniEdit Pro's original material. A copy is included inside the installable skill so the notice travels with it. Upstream license findings document the inspected revisions, not a legal guarantee for future revisions or third-party media.

Remotion's engine has [its own license](https://www.remotion.dev/license), distinct from these skill repositories. FFmpeg, speech engines, model weights, fonts, stock assets, music and generated media have their own applicable terms. OmniEdit does not bundle or grant rights to any of them.

The structure follows the [Agent Skills specification](https://agentskills.io/specification). Global installation uses the separately maintained [Vercel Skills CLI](https://github.com/vercel-labs/skills). Agent-specific official sources and limitations are linked in the [compatibility guide](skills/omni-edit-pro/references/agent-compatibility.md).
