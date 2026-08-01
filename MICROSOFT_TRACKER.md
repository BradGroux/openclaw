# Microsoft Ecosystem Issues & PRs Tracker

> **Purpose:** Living checklist for maintainers to track all open Microsoft-related issues and PRs (Teams, Windows, WSL, Azure, M365/SharePoint).
>
> **How to use:**
>
> - Mark items resolved by editing this PR body and changing `[ ]` to `[x]`
> - Claim items by adding your GitHub handle to the `Assignee` column
> - Priority guide: **P0** = crash/blocker/security, **P1** = significant bug/regression, **P2** = minor bug/enhancement, **P3** = nice-to-have/stale
> - Items marked _(stale)_ have been flagged by the stale bot due to inactivity
>
> **Last updated:** 2026-08-01 (post-purge audit: refreshed from currently open GitHub issues/PRs and rebuilt from PR #49126 format)

---

## Summary

| Category                  | Issues | PRs    | Total   | Closed | Remaining |
| ------------------------- | ------ | ------ | ------- | ------ | --------- |
| MS Teams (channel plugin) | 13     | 40     | 53      | 0      | 53        |
| Windows platform          | 46     | 20     | 66      | 0      | 66        |
| WSL                       | 1      | 0      | 1       | 0      | 1         |
| Azure                     | 9      | 9      | 18      | 0      | 18        |
| SharePoint / M365         | 0      | 0      | 0       | 0      | 0         |
| **Total**                 | **69** | **69** | **138** | **0**  | **138**   |

---

## 1. MS Teams Channel Plugin — Issues

### Bugs / Crashes

| Resolved? | Priority | #       | Title                                                                                                                                                                                               | Labels                                                                                                                                                                        | Assignee  |
| --------- | -------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------- |
| [ ]       | P0       | #115410 | security audit silently skips DM policy for channels without resolveDmPolicy (msteams, feishu)                                                                                                      | `bug` `security` `maintainer` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` +5                                                                       |           |
| [ ]       | P0       | #115367 | Provider-owned read gate requires `origin: bundled`, but every privileged chat surface (slack/discord/matrix/msteams/feishu) now ships as an external plugin → reads locked to current conversation | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `clawsweeper:source-repro` +2 |           |
| [ ]       | P0       | #105322 | Teams: local multi-user Workspaces sharing with exact tab RBAC                                                                                                                                      | `P3` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `impact:security` `issue-rating: 🌊 off-meta tidepool` +1           |           |
| [ ]       | P1       | #113351 | [Bug]: Duplicate image response in msteams when agent runtime is set to openclaw                                                                                                                    | `bug` `regression` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `impact:message-loss` +1                                                            |           |
| [ ]       | P1       | #112368 | [Bug]: Content created with non-unique file name causes msteams to show wrong file                                                                                                                  | `bug` `regression` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-product-decision` `clawsweeper:linked-pr-open` +5                                                      | @steipete |
| [ ]       | P1       | #106566 | [Bug] False-Positive Channel Health Failure for MS Teams on Expired Delegated Token                                                                                                                 | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:source-repro` `clawsweeper:linked-pr-open` `impact:auth-provider` `issue-rating: 🦞 diamond lobster` +1                         |           |
| [ ]       | P1       | #67177  | [msteams] Inbound file attachments silently fail in DMs — file.download.info downloadUrl not rewritten to Graph shares endpoint                                                                     | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `impact:message-loss` +1           |           |
| [ ]       | P2       | #104521 | Native approval buttons for Feishu, Microsoft Teams, and Mattermost                                                                                                                                 | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:source-repro` `issue-rating: 🦞 diamond lobster` `impact:ux-friction`                     |           |
| [ ]       | P2       | #102376 | [Bug]: MS Teams inbound mentions, quoted replies, and forwards are not normalized for agent text                                                                                                    | `bug` `maintainer` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-live-repro` +2                                                            |           |
| [ ]       | P2       | #94939  | [Bug]: 6.x state migration leaves channel conversation-store SQLite empty (0 bytes) — orphans references, breaks proactive (Bot Framework) sends (MS Teams)                                         | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-live-repro` `impact:data-loss` `impact:message-loss` +1                                      |           |

### Feature Requests

| Resolved? | Priority | #      | Title                                                                                         | Labels                                                                                                                                               | Assignee |
| --------- | -------- | ------ | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [ ]       | P2       | #99939 | [Feature]: MSTeams - Support raw Adaptive Card JSON in message tool for richer approval cards | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `issue-rating: 🌊 off-meta tidepool`     |          |
| [ ]       | P2       | #93288 | feat(msteams): per-call topLevel override on send action for proactive new channel threads    | `P2` `clawsweeper:needs-live-repro` `impact:message-loss` `issue-rating: 🐚 platinum hermit`                                                         |          |
| [ ]       | P2       | #81084 | [Feature]: MSTeams channel-bound agents need opt-out from per-thread sessions                 | `stale` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:fix-shape-clear` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` +2 |          |

---

## 2. MS Teams Channel Plugin — PRs

| Resolved? | Priority | #       | Title                                                                                      | Size | Assignee        |
| --------- | -------- | ------- | ------------------------------------------------------------------------------------------ | ---- | --------------- |
| [ ]       | P0       | #115432 | fix(security): audit open Feishu and Teams DMs                                             | S    |                 |
| [ ]       | P0       | #115301 | fix(msteams): resolve approvals before agent queue                                         | M    |                 |
| [ ]       | P0       | #114492 | fix: repair full-stack QA, gateway, and channel regressions                                | XL   |                 |
| [ ]       | P0       | #112791 | docs: fix agents.list -> agents.entries in 29 config examples across …                     | XS   |                 |
| [ ]       | P0       | #107164 | fix: Teams Graph and media work with RFC2544 proxy DNS                                     | S    |                 |
| [ ]       | P0       | #103780 | EXPERIMENTAL: authorization policy prototype — DO NOT LAND                                 | XL   | @steipete       |
| [ ]       | P0       | #98972  | fix: block channel reads outside allowlists [AI]                                           | XL   | @joshavant      |
| [ ]       | P0       | #77784  | Add Teams delegated auth for plugin tools                                                  | XL   |                 |
| [ ]       | P0       | #55828  | feat(msteams): add native plugin interactivity parity                                      | XL   |                 |
| [ ]       | P1       | #117114 | fix: fence pnpm link out of source-checkout updates and warn on self-link damage           | M    | @vincentkoc     |
| [ ]       | P1       | #112811 | feat(msteams): support multiple bot accounts                                               | XL   |                 |
| [ ]       | P1       | #112078 | feat: add NVIDIA Nemotron Speech ASR and TTS                                               | XL   | @jacobtomlinson |
| [ ]       | P1       | #111823 | fix(msteams): prevent toPluginJsonValue from crashing on unserializable values             | XS   |                 |
| [ ]       | P1       | #111638 | fix(msteams): reject malformed OAuth token envelopes [AI-assisted]                         | S    |                 |
| [ ]       | P1       | #106923 | fix(msteams): keep delegated auth healthy when an expired token can auto-refresh           | XS   |                 |
| [ ]       | P1       | #79185  | fix(tts/xiaomi): support Token Plan TTS endpoint                                           | S    |                 |
| [ ]       | P1       | #77921  | feat(inworld): default to inworld-tts-2 (Realtime TTS-2)                                   | XS   |                 |
| [ ]       | P1       | #59986  | refactor(plugins): add lane-oriented channel interface                                     | XL   |                 |
| [ ]       | P2       | #117345 | fix(tts): reject non-audio speech synthesis responses                                      | S    |                 |
| [ ]       | P2       | #116982 | Skillfy install scan hardening                                                             |      |                 |
| [ ]       | P2       | #116647 | fix(channels): preserve bundled plugin delivery and provider contracts                     | M    |                 |
| [ ]       | P2       | #116543 | fix(msteams): page channel thread replies                                                  | S    |                 |
| [ ]       | P2       | #115772 | fix(memory): force shared memory index and redirect to shared sqlite                       |      |                 |
| [ ]       | P2       | #115771 | fix(state): skip shared memory database ownership assertion for cross-agent access         |      |                 |
| [ ]       | P2       | #113560 | fix(msteams): stop SharePoint uploads overwriting same-named generated files in Teams      | S    |                 |
| [ ]       | P2       | #112322 | fix(channels): preserve durable ingress under queue backpressure                           | XL   |                 |
| [ ]       | P2       | #111317 | fix(msteams): token refresh hangs past deadline when DNS preflight stalls                  | S    |                 |
| [ ]       | P2       | #109864 | fix(msteams): bound federated certificate file reads                                       | S    |                 |
| [ ]       | P2       | #109030 | fix(msteams): bound remote media saves with header and idle timeouts                       | S    |                 |
| [ ]       | P2       | #107171 | fix: prevent duplicate Teams broker retry turns                                            | L    |                 |
| [ ]       | P2       | #106461 | fix(msteams): remove unused attachment helper                                              | XS   |                 |
| [ ]       | P2       | #104691 | fix(msteams): proactive sends fail after conversation migration                            | S    |                 |
| [ ]       | P2       | #104690 | fix(msteams): reset sessions on app removal lifecycle                                      | XL   | @steipete       |
| [ ]       | P2       | #102379 | fix(msteams): normalize inbound mentions and forwards                                      | XL   | @galiniliev     |
| [ ]       | P2       | #100906 | feat(signal): add setup wizard                                                             | XL   | @jesse-merhi    |
| [ ]       | P2       | #100350 | fix(msteams): handle bot removal and uninstallation to mark sessions stale                 | M    |                 |
| [ ]       | P2       | #95867  | fix(msteams): sanitize internal tool-trace lines from outbound text (#90684)               | XS   |                 |
| [ ]       | P2       | #93292  | feat(msteams): per-call topLevel override on send action for proactive new channel threads | S    |                 |
| [ ]       | P2       | #83988  | fix(tts): defer text settlement for final-mode TTS to eliminate churn (#83511)             | XL   |                 |
| [ ]       | P2       | #78839  | [codex] Add Teams member-info action gate                                                  | S    |                 |

---

## 3. Windows Platform — Issues

### Bugs / Crashes

| Resolved? | Priority | #       | Title                                                                                                                                                                                   | Labels                                                                                                                                                                                  | Assignee    |
| --------- | -------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| [ ]       | P0       | #116240 | [Bug]: Unix process-tree kill leaves orphan grandchildren when detached:false (Windows taskkill /T has no Unix equivalent)                                                              | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `clawsweeper:source-repro` `impact:security` +1                               |             |
| [ ]       | P0       | #114208 | [Bug]: Windows sandbox diagnostics emit a malformed container path hint                                                                                                                 | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `issue-rating: 🦪 silver shellfish` `impact:ux-friction` `clawsweeper:bulk-filed`                                         |             |
| [ ]       | P0       | #114207 | [Bug]: Windows misclassifies same-path sandbox binds as aliases                                                                                                                         | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-info` `issue-rating: 🦐 gold shrimp` `impact:other` +1                                                 |             |
| [ ]       | P0       | #105667 | [Bug] Incorrect Sandbox Bind Mount Parsing for Windows Relative Drive-Letter Paths                                                                                                      | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `clawsweeper:source-repro` +2           |             |
| [ ]       | P0       | #98470  | [Bug]: openclaw doctor misses Windows cloud-synced state dirs                                                                                                                           | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-security-review` `clawsweeper:needs-live-repro` `impact:session-state` +3                     |             |
| [ ]       | P0       | #89527  | 建议：为国内 Windows 用户提供一键安装器方案                                                                                                                                             | `P3` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `issue-rating: 🌊 off-meta tidepool` +2 |             |
| [ ]       | P0       | #83890  | Windows restart script builds ProcessStartInfo.Arguments via string concatenation without quoting embedded double-quotes                                                                | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `impact:security` `issue-rating: 🦪 silver shellfish`                         |             |
| [ ]       | P1       | #111476 | Windows: Telegram voice-note STT + exec-approvals writer fail silently with EPERM on fsync/rename (no retry, no user feedback)                                                          | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `impact:session-state` `impact:message-loss` +1                             |             |
| [ ]       | P1       | #109436 | Model fallback selection ignores candidate context windows, causing overflow/compaction storms on mid-turn failover                                                                     | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `impact:session-state` +2                    |             |
| [ ]       | P1       | #105528 | exec/read tools silently return empty output on Windows (v2026.6.x regression)                                                                                                          | `bug` `docs` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-info` +3                                                                         |             |
| [ ]       | P1       | #102755 | [Bug]: The project won't start on Windows and WSL.                                                                                                                                      | `bug` `bug:behavior` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` +2                                                     |             |
| [ ]       | P1       | #91675  | fetch failed / UND_ERR_SOCKET on Windows WSL when connecting to Google Gemini                                                                                                           | `bug` `bug:crash` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-live-repro` +3                                                              |             |
| [ ]       | P1       | #91144  | [Bug]: Windows native CLI gateway Scheduled Task does not stay running; foreground window worksWindows native CLI gateway Scheduled Task does not stay running; foreground window works | `bug` `bug:behavior` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-live-repro` +2                                                                    |             |
| [ ]       | P1       | #90548  | macOS: per-port lsof port-health polling can saturate launchservicesd and trigger a WindowServer watchdog reboot                                                                        | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `impact:crash-loop` +2                       | @vincentkoc |
| [ ]       | P1       | #90158  | Gateway self-restart on Windows fails silently when schtasks /Run cannot relaunch the scheduled task                                                                                    | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-live-repro` `impact:session-state` `impact:message-loss` +2                                   |             |
| [ ]       | P1       | #88373  | Windows post-onboarding provider switch path is not discoverable                                                                                                                        | `no-stale` `P2` `clawsweeper:fix-shape-clear` `clawsweeper:queueable-fix` `clawsweeper:source-repro` `impact:auth-provider` +3                                                          |             |
| [ ]       | P1       | #88372  | Windows provider switch leaves stale model/provider config and session cache                                                                                                            | `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `impact:session-state` `impact:auth-provider` +3  |             |
| [ ]       | P1       | #87136  | compaction: absolute token thresholds break when switching models with different context windows                                                                                        | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-info` `impact:session-state` +2                          |             |
| [ ]       | P1       | #74378  | [Bug]: OpenClaw CLI commands remain alive as node.exe processes after execution on Windows                                                                                              | `bug` `regression` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-info` +3                                                                   |             |
| [ ]       | P1       | #63491  | [Bug]: Windows Scheduled Task gateway restart/health becomes inconsistent after ready                                                                                                   | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-live-repro` `impact:session-state` `impact:crash-loop` +2                                     | @vincentkoc |
| [ ]       | P2       | #115989 | [Bug]: Windows Companion node never declares `browser` capability — "Enabled, not active yet", no error anywhere                                                                        | `bug` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `issue-rating: 🦪 silver shellfish` +2                                |             |
| [ ]       | P2       | #115430 | [Bug]: Corepack fails with EPERM creating pnpm shim in C:\Program Files\nodejs on Windows                                                                                               | `bug` `bug:behavior` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` +2                                                     |             |
| [ ]       | P2       | #113308 | SQLite state stores fail on long Windows paths                                                                                                                                          | `bug` `maintainer` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` +3                                                       | @vincentkoc |
| [ ]       | P2       | #113219 | [Bug]: exec / read tools mangle GBK-encoded output on Windows (cp936), corrupting transcript and causing empty-response loop                                                            | `bug` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` +3                                     |             |
| [ ]       | P2       | #112711 | [Bug]: Windows Hub node mode gets stuck in approval/repair loop and falls back to invalid bootstrap token                                                                               | `bug`                                                                                                                                                                                   |             |
| [ ]       | P2       | #112421 | MEDIA: directive fails for paths containing spaces (e.g. Windows profile "C:\Users\First Last")                                                                                         | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-live-repro` `impact:message-loss` `issue-rating: 🐚 platinum hermit`                                   |             |
| [ ]       | P2       | #112173 | ACP workers hang forever on permission prompts when Gateway runs as a hidden-console Windows service (stdin.isTTY=true)                                                                 | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `issue-rating: 🦪 silver shellfish` `impact:other`                          |             |
| [ ]       | P2       | #112051 | Windows installer cannot repair stale Winget Node registrations                                                                                                                         | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-live-repro` `issue-rating: 🐚 platinum hermit` `impact:ux-friction` +1                                 |             |
| [ ]       | P2       | #111900 | Codex CLI resume timeouts can leave descendant processes running on Windows                                                                                                             | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `issue-rating: 🦪 silver shellfish` `impact:other` `clawsweeper:bulk-filed`                                               |             |
| [ ]       | P2       | #111620 | [Bug]: Windows file tools misresolve POSIX drive paths                                                                                                                                  | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `clawsweeper:needs-live-repro` `issue-rating: 🐚 platinum hermit` `impact:other` +2                                       | @vincentkoc |
| [ ]       | P2       | #111595 | [Bug]: Equivalent Windows cwd spellings split catalog project groups                                                                                                                    | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `issue-rating: 🦪 silver shellfish` `impact:ux-friction`                                                                  | @vincentkoc |
| [ ]       | P2       | #111567 | SYSTEM_RUN_DENIED: approval required on Windows node despite correct exec-approvals.json (socket initialized with missing file)                                                         | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `issue-rating: 🐚 platinum hermit` +1        |             |
| [ ]       | P2       | #110757 | [Bug]: Windows Tray chat code blocks have no copy button                                                                                                                                | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-info` `issue-rating: 🦪 silver shellfish` +1             |             |
| [ ]       | P2       | #108802 | exec tool renders PowerShell output as "see in attachment" on Windows when output contains binary BOM                                                                                   | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:linked-pr-open` `issue-rating: 🦪 silver shellfish` `impact:ux-friction`                                                                  |             |
| [ ]       | P2       | #106203 | Remote Windows node is connected and system.which works, but Codex/WebChat exposes no node_exec surface                                                                                 | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `issue-rating: 🦪 silver shellfish` `impact:ux-friction`                                                         |             |
| [ ]       | P2       | #95072  | fix: Windows /restart falls back to in-process restart without changing PID                                                                                                             | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:source-repro` `issue-rating: 🦞 diamond lobster` +1            |             |
| [ ]       | P2       | #93081  | [Bug]: Ctrl+C not working in Windows install on foreground                                                                                                                              | `bug` `P2` `clawsweeper:needs-info` `issue-rating: 🦪 silver shellfish` `impact:other`                                                                                                  |             |
| [ ]       | P2       | #58139  | [Bug]: memory-lancedb plugin fails with Windows Docker bind mount                                                                                                                       | `bug` `bug:behavior` `P2` `clawsweeper:needs-info` `impact:session-state` `issue-rating: 🦪 silver shellfish`                                                                           |             |
| [ ]       | P2       | #44291  | Add native PowerShell smoke coverage for contributor commands                                                                                                                           | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `issue-rating: 🌊 off-meta tidepool` `impact:other`                         |             |
| [ ]       | P2       | #40694  | Browser-opened temporary tabs/windows should close automatically after task completion                                                                                                  | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:source-repro` `impact:session-state` +2                        |             |

### Feature Requests

| Resolved? | Priority | #      | Title                                                                                                                              | Labels                                                                                                                                                            | Assignee |
| --------- | -------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [ ]       | P0       | #89223 | [Bug]: SecretRef file provider broken on Windows 11 26200 — icacls /sid unsupported, preflight validator ignores allowInsecurePath | `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `impact:security` +2   |          |
| [ ]       | P0       | #72595 | [Feature]: Feishu channel needs per-channel proxy bypass for mixed Windows proxy setups                                            | `enhancement` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` +5  |          |
| [ ]       | P2       | #97800 | [Feature]: Console-free windows dashboard autostart (also without duplicate gateway launch)                                        | `enhancement` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `issue-rating: 🌊 off-meta tidepool` +1 |          |
| [ ]       | P2       | #18985 | [Feature]: Supports Windows 11 MSYS environment and Fishshell.                                                                     | `enhancement` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` +2       |          |
| [ ]       | P2       | #7057  | Flaky tests on Windows/WSL: timeouts and ENOENT in pi-tools workspace-paths & safe-bins                                            | `enhancement` `P3` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `issue-rating: 🦪 silver shellfish` `impact:other` +1                        |          |
| [ ]       | P2       | #75    | Linux/Windows Clawdbot Apps                                                                                                        | `enhancement` `help wanted` `P2` `issue-rating: 🌊 off-meta tidepool` `impact:ux-friction`                                                                        |          |

---

## 4. Windows Platform — PRs

| Resolved? | Priority | #       | Title                                                                               | Size | Assignee    |
| --------- | -------- | ------- | ----------------------------------------------------------------------------------- | ---- | ----------- |
| [ ]       | P0       | #112055 | fix(install): repair stale Winget Node registrations                                | XS   |             |
| [ ]       | P0       | #108073 | fix(infra): scope Windows path realpath caches                                      | M    |             |
| [ ]       | P1       | #116797 | fix(agent-exec): cold runs time out on slow hosts and fail on Windows cleanup EBUSY | XS   |             |
| [ ]       | P1       | #116570 | fix(windows): report Startup fallback launch failures                               | S    |             |
| [ ]       | P1       | #111523 | fix(json-parse): exclude code-context tails from Windows-path heuristic (#93139)    | S    |             |
| [ ]       | P1       | #95982  | fix(json-parse): exclude code-context tails from Windows-path heuristic (#93139)    | S    |             |
| [ ]       | P2       | #116780 | test(auto-reply): run dispatch suite on Windows                                     | XS   |             |
| [ ]       | P2       | #115399 | fix(mxc): agent tools fail in Windows workspace subdirectories                      | S    |             |
| [ ]       | P2       | #114925 | fix(ai): remove Windows path heuristic that double-escapes JSON newlines            | S    | @vincentkoc |
| [ ]       | P2       | #114900 | fix: decode Windows bash session output                                             | XS   | @vincentkoc |
| [ ]       | P2       | #111902 | fix(codex): stop timed-out resume process trees on Windows                          | L    |             |
| [ ]       | P2       | #111814 | [AI] fix(update-cli): warn+continue on Windows schtasks access-denied               | S    |             |
| [ ]       | P2       | #111716 | fix(process): resolve Windows commands when env aliases are blank                   | S    |             |
| [ ]       | P2       | #111624 | fix(tools): read POSIX drive paths on Windows                                       | S    | @vincentkoc |
| [ ]       | P2       | #111596 | fix(ui): keep Windows catalog sessions in one project group                         | S    | @vincentkoc |
| [ ]       | P2       | #111257 | fix(diffs): find Windows browsers when install roots are blank                      | S    |             |
| [ ]       | P2       | #110947 | [codex] Add WhatsApp group listen windows                                           | M    |             |
| [ ]       | P2       | #110877 | fix(scripts): use direct-run helper for Windows guards                              | S    |             |
| [ ]       | P2       | #109163 | fix: PowerShell exec output with BOM renders as text                                | M    |             |
| [ ]       | P2       | #69059  | fix: retry sqlite-vec load without .dll suffix on Windows                           | S    |             |

---

## 5. WSL (Windows Subsystem for Linux) — Issues

### Bugs / Crashes

| Resolved? | Priority | #       | Title                                                                                   | Labels                                                                                                                                                                 | Assignee |
| --------- | -------- | ------- | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [ ]       | P1       | #116731 | Cron failureAlert silently swallowed by quiet exits and misses WSL2 drvfs mount failure | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-info` `issue-rating: 🦐 gold shrimp` +1 |          |

### Feature Requests

_No currently open items found._

---

## 6. WSL (Windows Subsystem for Linux) — PRs

_No currently open items found._

---

## 7. Azure (Provider / Infrastructure) — Issues

### Bugs / Crashes

| Resolved? | Priority | #       | Title                                                                                                                        | Labels                                                                                                                                                                            | Assignee |
| --------- | -------- | ------- | ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [ ]       | P0       | #95894  | Plugin installs crash Express 4.x routes: core npm-shrinkwrap pins path-to-regexp@8.x but no central override covers plugins | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `clawsweeper:needs-live-repro` +2 |          |
| [ ]       | P1       | #111386 | Azure OpenAI embedding provider fails — api-version not forwarded as URL query parameter                                     | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:source-repro` `clawsweeper:linked-pr-open` `impact:auth-provider` `issue-rating: 🦞 diamond lobster`                                |          |
| [ ]       | P1       | #80926  | Azure OpenAI Responses stalls before first event when memory tools are exposed                                               | `maintainer` `P1` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `impact:auth-provider` +2                                |          |
| [ ]       | P2       | #103067 | Centralize chat-session naming; define subagent session lifetime & cross-channel persistence                                 | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-info` `impact:session-state` +2                    |          |
| [ ]       | P2       | #48788  | feat: centralized filename encoding utility for multi-encoding Content-Disposition handling                                  | `P3` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `issue-rating: 🐚 platinum hermit`     |          |

### Feature Requests

| Resolved? | Priority | #       | Title                                                                                               | Labels                                                                                                                                                                 | Assignee |
| --------- | -------- | ------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| [ ]       | P0       | #87325  | Support Azure Foundry GPT Realtime Talk via gateway relay                                           | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-security-review` `impact:security` +3   |          |
| [ ]       | P1       | #102907 | Azure OpenAI Responses throws 400 when prompt_cache_key is sent to endpoints that do not support it | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `impact:auth-provider` `issue-rating: 🦪 silver shellfish` |          |
| [ ]       | P1       | #71058  | [Feature]: Support for multiple Azure/Teams bots on a single Openclaw Gateway                       | `enhancement` `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-product-decision` `impact:auth-provider` `issue-rating: 🌊 off-meta tidepool`                        |          |
| [ ]       | P2       | #90842  | [Feature]: Document and/or centralize the per-event cfg re-resolve contract for channel plugins     | `P2` `clawsweeper:no-new-fix-pr` `clawsweeper:needs-maintainer-review` `clawsweeper:needs-product-decision` `clawsweeper:needs-live-repro` `impact:message-loss` +1    |          |

---

## 8. Azure (Provider / Infrastructure) — PRs

| Resolved? | Priority | #       | Title                                                                          | Size | Assignee    |
| --------- | -------- | ------- | ------------------------------------------------------------------------------ | ---- | ----------- |
| [ ]       | P0       | #116793 | refactor(agents): centralize immutable execution attribution                   | M    | @vincentkoc |
| [ ]       | P0       | #70922  | refactor(whatsapp): centralize account policy                                  | L    |             |
| [ ]       | P1       | #108482 | refactor(skills): centralize internal write paths                              | L    |             |
| [ ]       | P1       | #98259  | fix(openai): enable prompt cache keys for Azure                                | L    |             |
| [ ]       | P2       | #117327 | refactor(telegram): centralize text delivery                                   | XL   |             |
| [ ]       | P2       | #116403 | refactor(agents): centralize local turn lifecycle ownership                    | L    | @vincentkoc |
| [ ]       | P2       | #111813 | fix: Azure OpenAI memory indexing fails for custom providers                   | S    |             |
| [ ]       | P2       | #110299 | docs(providers): add Azure OpenAI setup page and directory entry               | XS   |             |
| [ ]       | P2       | #107070 | refactor(whatsapp): centralize inbound turn admission and history finalization | M    |             |

---

## 9. Microsoft 365 / SharePoint — Issues

### Bugs / Crashes

_No currently open items found._

### Feature Requests

_No currently open items found._

---

## 10. Microsoft 365 / SharePoint — PRs

_No currently open items found._

---

## Appendix: P0 Blockers (Start Here)

| Category                  | Type  | Priority | #       | Title                                                                                                                                                                                               |
| ------------------------- | ----- | -------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MS Teams (channel plugin) | issue | P0       | #115410 | security audit silently skips DM policy for channels without resolveDmPolicy (msteams, feishu)                                                                                                      |
| MS Teams (channel plugin) | issue | P0       | #115367 | Provider-owned read gate requires `origin: bundled`, but every privileged chat surface (slack/discord/matrix/msteams/feishu) now ships as an external plugin → reads locked to current conversation |
| MS Teams (channel plugin) | issue | P0       | #105322 | Teams: local multi-user Workspaces sharing with exact tab RBAC                                                                                                                                      |
| MS Teams (channel plugin) | pr    | P0       | #115432 | fix(security): audit open Feishu and Teams DMs                                                                                                                                                      |
| MS Teams (channel plugin) | pr    | P0       | #115301 | fix(msteams): resolve approvals before agent queue                                                                                                                                                  |
| MS Teams (channel plugin) | pr    | P0       | #114492 | fix: repair full-stack QA, gateway, and channel regressions                                                                                                                                         |
| MS Teams (channel plugin) | pr    | P0       | #112791 | docs: fix agents.list -> agents.entries in 29 config examples across …                                                                                                                              |
| MS Teams (channel plugin) | pr    | P0       | #107164 | fix: Teams Graph and media work with RFC2544 proxy DNS                                                                                                                                              |
| MS Teams (channel plugin) | pr    | P0       | #103780 | EXPERIMENTAL: authorization policy prototype — DO NOT LAND                                                                                                                                          |
| MS Teams (channel plugin) | pr    | P0       | #98972  | fix: block channel reads outside allowlists [AI]                                                                                                                                                    |
| MS Teams (channel plugin) | pr    | P0       | #77784  | Add Teams delegated auth for plugin tools                                                                                                                                                           |
| MS Teams (channel plugin) | pr    | P0       | #55828  | feat(msteams): add native plugin interactivity parity                                                                                                                                               |
| Windows platform          | issue | P0       | #116240 | [Bug]: Unix process-tree kill leaves orphan grandchildren when detached:false (Windows taskkill /T has no Unix equivalent)                                                                          |
| Windows platform          | issue | P0       | #114208 | [Bug]: Windows sandbox diagnostics emit a malformed container path hint                                                                                                                             |
| Windows platform          | issue | P0       | #114207 | [Bug]: Windows misclassifies same-path sandbox binds as aliases                                                                                                                                     |
| Windows platform          | issue | P0       | #105667 | [Bug] Incorrect Sandbox Bind Mount Parsing for Windows Relative Drive-Letter Paths                                                                                                                  |
| Windows platform          | issue | P0       | #98470  | [Bug]: openclaw doctor misses Windows cloud-synced state dirs                                                                                                                                       |
| Windows platform          | issue | P0       | #89527  | 建议：为国内 Windows 用户提供一键安装器方案                                                                                                                                                         |
| Windows platform          | issue | P0       | #89223  | [Bug]: SecretRef file provider broken on Windows 11 26200 — icacls /sid unsupported, preflight validator ignores allowInsecurePath                                                                  |
| Windows platform          | issue | P0       | #83890  | Windows restart script builds ProcessStartInfo.Arguments via string concatenation without quoting embedded double-quotes                                                                            |
| Windows platform          | issue | P0       | #72595  | [Feature]: Feishu channel needs per-channel proxy bypass for mixed Windows proxy setups                                                                                                             |
| Windows platform          | pr    | P0       | #112055 | fix(install): repair stale Winget Node registrations                                                                                                                                                |
| Windows platform          | pr    | P0       | #108073 | fix(infra): scope Windows path realpath caches                                                                                                                                                      |
| Azure                     | issue | P0       | #95894  | Plugin installs crash Express 4.x routes: core npm-shrinkwrap pins path-to-regexp@8.x but no central override covers plugins                                                                        |
| Azure                     | issue | P0       | #87325  | Support Azure Foundry GPT Realtime Talk via gateway relay                                                                                                                                           |
| Azure                     | pr    | P0       | #116793 | refactor(agents): centralize immutable execution attribution                                                                                                                                        |
| Azure                     | pr    | P0       | #70922  | refactor(whatsapp): centralize account policy                                                                                                                                                       |

## Appendix: High-Priority Bugs / Regressions

| Category                  | Type  | Priority | #       | Title                                                                                                                                                                                   |
| ------------------------- | ----- | -------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| MS Teams (channel plugin) | issue | P1       | #113351 | [Bug]: Duplicate image response in msteams when agent runtime is set to openclaw                                                                                                        |
| MS Teams (channel plugin) | issue | P1       | #112368 | [Bug]: Content created with non-unique file name causes msteams to show wrong file                                                                                                      |
| MS Teams (channel plugin) | issue | P1       | #106566 | [Bug] False-Positive Channel Health Failure for MS Teams on Expired Delegated Token                                                                                                     |
| MS Teams (channel plugin) | issue | P1       | #67177  | [msteams] Inbound file attachments silently fail in DMs — file.download.info downloadUrl not rewritten to Graph shares endpoint                                                         |
| MS Teams (channel plugin) | pr    | P1       | #117114 | fix: fence pnpm link out of source-checkout updates and warn on self-link damage                                                                                                        |
| MS Teams (channel plugin) | pr    | P1       | #112811 | feat(msteams): support multiple bot accounts                                                                                                                                            |
| MS Teams (channel plugin) | pr    | P1       | #112078 | feat: add NVIDIA Nemotron Speech ASR and TTS                                                                                                                                            |
| MS Teams (channel plugin) | pr    | P1       | #111823 | fix(msteams): prevent toPluginJsonValue from crashing on unserializable values                                                                                                          |
| MS Teams (channel plugin) | pr    | P1       | #111638 | fix(msteams): reject malformed OAuth token envelopes [AI-assisted]                                                                                                                      |
| MS Teams (channel plugin) | pr    | P1       | #106923 | fix(msteams): keep delegated auth healthy when an expired token can auto-refresh                                                                                                        |
| MS Teams (channel plugin) | pr    | P1       | #79185  | fix(tts/xiaomi): support Token Plan TTS endpoint                                                                                                                                        |
| MS Teams (channel plugin) | pr    | P1       | #77921  | feat(inworld): default to inworld-tts-2 (Realtime TTS-2)                                                                                                                                |
| MS Teams (channel plugin) | pr    | P1       | #59986  | refactor(plugins): add lane-oriented channel interface                                                                                                                                  |
| Windows platform          | issue | P1       | #111476 | Windows: Telegram voice-note STT + exec-approvals writer fail silently with EPERM on fsync/rename (no retry, no user feedback)                                                          |
| Windows platform          | issue | P1       | #109436 | Model fallback selection ignores candidate context windows, causing overflow/compaction storms on mid-turn failover                                                                     |
| Windows platform          | issue | P1       | #105528 | exec/read tools silently return empty output on Windows (v2026.6.x regression)                                                                                                          |
| Windows platform          | issue | P1       | #102755 | [Bug]: The project won't start on Windows and WSL.                                                                                                                                      |
| Windows platform          | issue | P1       | #91675  | fetch failed / UND_ERR_SOCKET on Windows WSL when connecting to Google Gemini                                                                                                           |
| Windows platform          | issue | P1       | #91144  | [Bug]: Windows native CLI gateway Scheduled Task does not stay running; foreground window worksWindows native CLI gateway Scheduled Task does not stay running; foreground window works |
| Windows platform          | issue | P1       | #90548  | macOS: per-port lsof port-health polling can saturate launchservicesd and trigger a WindowServer watchdog reboot                                                                        |
| Windows platform          | issue | P1       | #90158  | Gateway self-restart on Windows fails silently when schtasks /Run cannot relaunch the scheduled task                                                                                    |
| Windows platform          | issue | P1       | #88373  | Windows post-onboarding provider switch path is not discoverable                                                                                                                        |
| Windows platform          | issue | P1       | #88372  | Windows provider switch leaves stale model/provider config and session cache                                                                                                            |
| Windows platform          | issue | P1       | #87136  | compaction: absolute token thresholds break when switching models with different context windows                                                                                        |
| Windows platform          | issue | P1       | #74378  | [Bug]: OpenClaw CLI commands remain alive as node.exe processes after execution on Windows                                                                                              |
| Windows platform          | issue | P1       | #63491  | [Bug]: Windows Scheduled Task gateway restart/health becomes inconsistent after ready                                                                                                   |
| Windows platform          | pr    | P1       | #116797 | fix(agent-exec): cold runs time out on slow hosts and fail on Windows cleanup EBUSY                                                                                                     |
| Windows platform          | pr    | P1       | #116570 | fix(windows): report Startup fallback launch failures                                                                                                                                   |
| Windows platform          | pr    | P1       | #111523 | fix(json-parse): exclude code-context tails from Windows-path heuristic (#93139)                                                                                                        |
| Windows platform          | pr    | P1       | #95982  | fix(json-parse): exclude code-context tails from Windows-path heuristic (#93139)                                                                                                        |
| WSL                       | issue | P1       | #116731 | Cron failureAlert silently swallowed by quiet exits and misses WSL2 drvfs mount failure                                                                                                 |
| Azure                     | issue | P1       | #111386 | Azure OpenAI embedding provider fails — api-version not forwarded as URL query parameter                                                                                                |
| Azure                     | issue | P1       | #102907 | Azure OpenAI Responses throws 400 when prompt_cache_key is sent to endpoints that do not support it                                                                                     |
| Azure                     | issue | P1       | #80926  | Azure OpenAI Responses stalls before first event when memory tools are exposed                                                                                                          |
| Azure                     | issue | P1       | #71058  | [Feature]: Support for multiple Azure/Teams bots on a single Openclaw Gateway                                                                                                           |
| Azure                     | pr    | P1       | #108482 | refactor(skills): centralize internal write paths                                                                                                                                       |
| Azure                     | pr    | P1       | #98259  | fix(openai): enable prompt cache keys for Azure                                                                                                                                         |

## Appendix: Stale Items (Consider Closing)

| Category                  | Type  | Priority | #      | Title                                                                         |
| ------------------------- | ----- | -------- | ------ | ----------------------------------------------------------------------------- |
| MS Teams (channel plugin) | issue | P2       | #81084 | [Feature]: MSTeams channel-bound agents need opt-out from per-thread sessions |

## Audit Notes

- Rebuilt from the format of PR #49126 after the issue/PR purge.
- Source set is currently open GitHub issues and PRs from `openclaw/openclaw`; closed counts are intentionally reset to `0` for this refreshed tracker.
- Included title/label matches for `msteams`, Microsoft Teams, Windows, WSL, Azure, Entra/AAD, MSAL, managed identity, DefaultAzureCredential, Microsoft Graph, SharePoint, OneDrive, and Microsoft 365.
- Kept broad multi-channel PRs when they carry `channel: msteams`, because those can still affect the Microsoft surface area.
- Generated with `node scripts/generate-microsoft-tracker.mjs` so the tracker and PR body can be refreshed after future triage passes.
