# ⚙ Claude Code Managed-Settings Builder

**The most advanced Claude Code `managed-settings.json` policy builder on the web.**

Generate enterprise security policies with a visual interface — permissions, sandbox, MCP controls, hooks, plugins, environment variables, and every other setting. Complete documentation included.

[![Live](https://img.shields.io/badge/🔗_Live-managed--settings.net-7c3aed?style=for-the-badge)](https://managed-settings.net)

---

## 🔗 [managed-settings.net](https://managed-settings.net)

---

## The Problem

Claude Code's `managed-settings.json` controls everything — what developers can run, what files they can read, which MCP servers are allowed, how hooks behave, and more. Writing it by hand means:

- Memorizing dozens of JSON keys and nested structures
- Guessing pattern syntax for Bash, Read, Edit, WebFetch rules
- Missing managed-only keys that silently get ignored in the wrong file
- No validation until you deploy and something breaks

## The Solution

A single-page visual builder that covers **every key** in the Claude Code settings schema. Toggle switches, quick-add buttons, tag inputs, and a live JSON preview — then download or copy the result.

---

## What's Inside

### Builder

| Section | What You Can Configure |
|---|---|
| **Authentication** | `forceLoginMethod`, `forceLoginOrgUUID`, `apiKeyHelper`, AWS credential helpers |
| **Permissions** | Deny / Allow / Ask rules with pattern syntax, `defaultMode`, `disableBypassPermissionsMode`, `allowManagedPermissionRulesOnly` |
| **Sandbox** | Network domain allowlists, Unix sockets, filesystem read/write restrictions, unsandboxed commands |
| **Hooks** | `disableAllHooks`, `allowManagedHooksOnly`, HTTP hook URL + env var allowlists |
| **MCP Servers** | Enable/disable specific servers, `enableAllProjectMcpServers` |
| **Plugins** | `strictKnownMarketplaces`, marketplace restrictions |
| **Environment Vars** | 25+ presets — telemetry, Bedrock, Vertex, OTEL, proxy, timeouts |
| **Model & Output** | Model override, extended thinking, `skipWebFetchPreflight`, OTEL headers |
| **General** | Transcript retention, auto-updates, co-authored-by, git instructions |
| **Announcements** | Company-wide startup messages |

### Documentation

Below the builder is a **complete 15-section reference** covering every option, accepted values, scope (managed-only vs any level), merge behavior, file paths by OS, and three ready-to-use policy presets.

### Export

- **Live JSON preview** with syntax highlighting — updates as you toggle
- **Copy** to clipboard
- **Download** as `managed-settings.json` or `settings.json`
- **Import** existing JSON to edit visually

---

## Managed-Only Keys

These only work in `managed-settings.json` — they're silently ignored in regular settings:

| Key | What It Does |
|---|---|
| `forceLoginMethod` | Lock auth to `claudeai` or `console` |
| `forceLoginOrgUUID` | Lock users to a specific org |
| `allowManagedPermissionRulesOnly` | Ignore all user/project permission rules |
| `allowManagedHooksOnly` | Block all non-managed hooks |
| `strictKnownMarketplaces` | Restrict plugin sources (empty `[]` = block all) |

---

## Deployment Paths

After generating your JSON, deploy to the system path for your OS:

| OS | Path |
|---|---|
| macOS | `/Library/Application Support/ClaudeCode/managed-settings.json` |
| Linux / WSL | `/etc/claude-code/managed-settings.json` |
| Windows | `C:\Program Files\ClaudeCode\managed-settings.json` |

Or via MDM: macOS plist (`com.anthropic.claudecode`), Windows registry (`HKLM\SOFTWARE\Policies\ClaudeCode`).

Verify with `/status` inside Claude Code.

---

## References

- [Claude Code Settings Docs](https://code.claude.com/docs/en/settings)
- [Settings JSON Schema](https://json.schemastore.org/claude-code-settings.json)
- [Official Settings Examples](https://github.com/anthropics/claude-code/tree/main/examples/settings)
- [Claude Code Enterprise](https://claude.com/product/claude-code/enterprise)
- [Enterprise Configuration](https://support.claude.com/en/articles/12622667-enterprise-configuration)

---

## Author

**Omri Yaakov**

---

## License

MIT
