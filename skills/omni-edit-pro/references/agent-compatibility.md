# Agent compatibility and global installation

The host conventions below were checked for the earlier release against official documentation and Skills CLI 1.7.2 on 18 October 2026. They are historical compatibility notes, not a claim that this nine-entry suite has been runtime-tested in every host. Directory support is host-specific; an installed file and a successful CLI listing do not prove that a particular app has loaded it. `~` below means the current user's home, not a project folder.

## Install without changing a project

This skill needs only Markdown files and its license at installation time. CLI installation requires Git, network access and a Node/npm version supported by the selected Skills CLI; version 1.7.2 declares Node.js >=22.20.0. Manual copying does not require Node. No FFmpeg, Remotion, model, browser binary, or video project belongs in this step.

Before installing, identify the exact host and inspect both its native skill directory and any shared directory it reads for existing core and preset names. Also run a global skills listing when available. Compare existing files and back up local changes; do not replace a conflicting installation without the user's update authorization. The CLI can overwrite a same-name skill and can skip prompts when it detects an agent environment. Omitting `--yes` alone is not a conflict guarantee.

For the complete same-release suite or selected presets, follow the repository INSTALL.md. Every preset depends on the sibling `omni-edit-pro` core. This local-checkout command installs the core and main entry at user scope:

```sh
npx skills add . --skill omni-edit-pro omni-pro-edit --global
```

Select the intended host when prompted, or add `--agent` with a verified ID below. Prefer an explicit agent: CLI 1.7.2's automatic selection installed shared/Claude copies in our isolated test but also printed a PromptScript global-install failure while exiting zero. Read the installation summary rather than relying only on the exit code. Do not use `--all`. Use `--copy` if filesystem links are unsuitable. In PowerShell, `npx.cmd` can avoid a blocked `npx.ps1` without changing execution policy. Pin `skills@1.7.2` in place of `skills` when reproducing this release's tests.

Discover before installation and inspect the user scope afterward:

```sh
npx skills add . --list
npx skills list --global
```

The installed core must contain `SKILL.md`, `LICENSE`, and its complete `references/` subtree. Each installed preset must contain its own `SKILL.md` and `LICENSE`; its relative link to the sibling core must resolve. Install all nine skill folders for the complete suite, or the core plus selected wrappers. Compare the complete subtree with the downloaded revision, not just the entrypoint. Reload/restart the host if necessary, inspect its skill picker/list, and invoke the skill with a harmless planning-only prompt from an unrelated directory. Check for duplicate names in project-level folders if discovery is ambiguous.

## Hosts and invocation

The table retains the original `omni-edit-pro` invocation for compatibility. Substitute an installed main or preset name using the same supported host syntax. Verify current host conventions at installation time.

| Host | Official user-level roots | Invocation | Installation route |
| --- | --- | --- | --- |
| [Codex](https://learn.chatgpt.com/docs/build-skills) | `~/.agents/skills/` | `$omni-edit-pro`, or `/skills` then choose it in CLI/IDE | Skills CLI `--agent codex` |
| [Claude Code](https://code.claude.com/docs/en/skills) | `~/.claude/skills/` | `/omni-edit-pro` or automatic selection | `--agent claude-code` |
| [Cursor](https://cursor.com/docs/skills) | `~/.cursor/skills/`, `~/.agents/skills/` | `/omni-edit-pro` or automatic selection | `--agent cursor`; personal Cloud sync requires the native Cursor root |
| [Kimi Code CLI](https://www.kimi.com/code/docs/en/kimi-code-cli/customization/skills.html) | `~/.kimi-code/skills/` (or configured `KIMI_CODE_HOME`), `~/.agents/skills/` | `/skill:omni-edit-pro` | `--agent kimi-code-cli` |
| [GitHub Copilot / VS Code](https://code.visualstudio.com/docs/agent-customization/agent-skills) | `~/.copilot/skills/`, `~/.agents/skills/`; VS Code also reads `~/.claude/skills/` | `/omni-edit-pro` or automatic selection in supporting clients | `--agent github-copilot` |
| [Antigravity App / IDE](https://antigravity.google/docs/skills) | `~/.gemini/config/skills/`; IDE also documents legacy `~/.gemini/antigravity/skills/` | App: `/omni-edit-pro`; IDE: Customizations > Skills or relevance-based selection | Manual copy to the documented root; see caveat below |
| [Antigravity CLI](https://antigravity.google/docs/skills) | `~/.gemini/antigravity-cli/skills/` | `/omni-edit-pro` | Manual copy to this root; see caveat below |
| [Devin CLI](https://docs.devin.ai/cli/extensibility/skills/overview) | `~/.config/devin/skills/` or `~/.agents/skills/`; Windows native: `%APPDATA%/devin/skills/` | `/omni-edit-pro` or automatic selection | Manual native/shared copy; CLI `--agent devin` needs the Windows caveat below |
| [Devin Desktop / Cascade](https://docs.devin.ai/desktop/cascade/skills) | `~/.config/devin/skills/` or `~/.codeium/windsurf/skills/` | `@omni-edit-pro` or automatic selection | Manual copy; no claim of generic Devin cloud availability |
| [DeepSeek Harness filesystem provider](https://github.com/deepseek-ai/deepseek-harness/blob/master/packages/skill/skill-filesystem/README.md) | `~/.dsh/skills/` or `~/.agents/skills/`, configurable through the harness | `/omni-edit-pro` when the [tool-skill component](https://github.com/deepseek-ai/deepseek-harness/blob/master/packages/skill/tool-skill/README.md) is enabled | Manual copy; documented, not runtime-tested here |

DeepSeek is also a model provider. A [DeepSeek-backed Claude Code environment](https://api-docs.deepseek.com/quick_start/agent_integrations/claude_code/) uses Claude Code's skill mechanism. No local-skill support is claimed for the consumer DeepSeek chat website, and no `--agent deepseek` flag is documented by the inspected CLI.

Standalone local installation applies to the selected machine/account. Remote containers, cloud agents and another device need their own supported distribution method. Do not promise one slash command or automatic synchronization across every surface. ChatGPT's skill picker uses `@`; that is distinct from Codex CLI's `$` syntax.

## CLI mapping caveats and manual fallback

The CLI's agent names do not guarantee agreement with every host version. The previously inspected [agent definitions](https://github.com/vercel-labs/skills/blob/main/src/agents.ts) and [installer](https://github.com/vercel-labs/skills/blob/main/src/installer.ts) classify Antigravity IDs as universal, leading to the shared global directory, which Google's cited docs do not list as a global root. Prefer Google's native paths and verify in the app. On Windows, the CLI's Devin mapping can use `~/.config/devin/skills/` instead of the documented `%APPDATA%` location; use a documented native or shared root.

For any manual installation:

1. Download or clone the named repository in a temporary directory outside the current project. Review the chosen revision.
2. Resolve the host's user-level root above and check for conflicts, including an existing symlink. Create the parent directory if absent.
3. Copy the **entire** `skills/omni-edit-pro/` core and each selected wrapper folder as siblings into that root, resulting in `<user-skill-root>/omni-edit-pro/SKILL.md` and `<user-skill-root>/<preset>/SKILL.md`. Do not copy only `SKILL.md` or add an extra nesting level. Include the bundled license.
4. Compare every file, reload the host and verify discovery/invocation. Remove temporary downloads when no longer needed; leave the installed copy intact.

If the host cannot read local files or execute commands, it can use these instructions for planning only. Rendering requires a capable local or connected execution environment. For other Agent Skills hosts, consult their official user-scope convention instead of inventing a directory.

CLI reference: [Vercel Skills](https://github.com/vercel-labs/skills). Standard: [Agent Skills specification](https://agentskills.io/specification).
