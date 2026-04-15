# Documentation Scope Audit — 2026-04-15

## Purpose

A comprehensive audit of Paperclip's documentation landscape: what exists, what's missing, what's stale, and what to prioritize. Scoped to the needs of a board operator / solo founder running Paperclip to orchestrate AI agent companies.

---

## 1. Documentation Inventory

### Root-Level Files

| File | Status | Notes |
|------|--------|-------|
| `README.md` | **Needs update** | "Works with" table missing 5 adapters (Gemini, Cursor, Pi, OpenCode, Hermes). Roadmap has stale items. |
| `AGENTS.md` | Current | Good shape. Fork-specific section at bottom is niche. |
| `CONTRIBUTING.md` | Current | Covers PR template and thinking-path convention. |
| `SECURITY.md` | **Minimal** | Only a "report a vulnerability" link. No hardening guidance. |
| `adapter-plugin.md` | Current | Covers external adapter plugin loading. |
| `LICENSE` | Current | MIT. |

### Internal Docs (`doc/`)

| File | Status | Notes |
|------|--------|-------|
| `GOAL.md` | Current | High-level mission statement. |
| `PRODUCT.md` | **Partially stale** | "More detailed task structure TBD" — tasks are fully implemented. Missing: plugins, routines, execution policy, workspaces. |
| `SPEC.md` | Reference | Long-horizon spec. Not actively maintained as current-state docs. |
| `SPEC-implementation.md` | Reference | V1 build contract. Useful but not user-facing. |
| `DEVELOPING.md` | Current | Dev setup guide. |
| `DATABASE.md` | Current | Schema and migration workflow. |
| `CLI.md` | **Needs review** | Compare against actual CLI commands in `cli/src/`. |
| `DEPLOYMENT-MODES.md` | **Duplicated** | Also exists as `docs/deploy/deployment-modes.md`. |
| `DOCKER.md` | **Duplicated** | Also exists as `docs/deploy/docker.md`. |
| `PUBLISHING.md` | Current | Release process for maintainers. |
| `RELEASING.md` | Current | Paired with release skill. |
| `CLIPHUB.md` | Draft | Company marketplace concept. |
| `TASKS.md` / `TASKS-mcp.md` | Stale | Old task tracking. Superseded by actual issue system. |
| `memory-landscape.md` | Draft | Memory service exploration. |
| `doc/plans/` (30+ files) | Mixed | Planning artifacts. Some implemented, some abandoned. No index. |
| `doc/plugins/` | **Important** | `PLUGIN_SPEC.md` and `PLUGIN_AUTHORING_GUIDE.md` — not surfaced in `docs/` site. |
| `doc/spec/` | Internal | `agents-runtime.md`, `agent-runs.md`, `ui.md` — dev reference. |

### Public Docs Site (`docs/`)

#### Getting Started (`docs/start/`)
| File | Status | Notes |
|------|--------|-------|
| `what-is-paperclip.md` | **Good** | Clear, accurate. |
| `architecture.md` | **Good** | Stack diagram, repo structure, adapter model. |
| `core-concepts.md` | **Good** | Companies, agents, issues, delegation, heartbeats, governance. |
| `quickstart.md` | **Good** | npx and local dev paths. |

#### API Reference (`docs/api/`)
| File | Status | Covers |
|------|--------|--------|
| `overview.md` | Good | Auth, errors, conventions. |
| `agents.md` | Good | Agent CRUD. |
| `issues.md` | Good | Issue lifecycle, checkout. |
| `companies.md` | Good | Company CRUD. |
| `approvals.md` | Good | Approval system. |
| `costs.md` | Good | Cost tracking. |
| `dashboard.md` | Good | Dashboard endpoints. |
| `goals-and-projects.md` | Good | Goals and projects. |
| `routines.md` | Good | Scheduled routines. |
| `secrets.md` | Good | Secret management. |
| `activity.md` | Good | Activity log. |
| `authentication.md` | Good | Auth details. |
| **Missing:** | | `execution-workspaces`, `plugins`, `instance-settings`, `company-skills`, `inbox`, `assets`, `llms`, `sidebar-badges` |

#### Adapter Docs (`docs/adapters/`)
| File | Status | Notes |
|------|--------|-------|
| `overview.md` | Good | Adapter model explained. |
| `creating-an-adapter.md` | Good | How to build one. |
| `claude-local.md` | Good | Claude Code adapter. |
| `codex-local.md` | Good | Codex adapter. |
| `gemini-local.md` | Good | Gemini adapter. |
| `http.md` | Good | HTTP webhook adapter. |
| `process.md` | Good | Shell process adapter. |
| `external-adapters.md` | Good | Plugin-based adapters. |
| `adapter-ui-parser.md` | Good | UI parser spec. |
| **Missing:** | | `cursor-local`, `openclaw-gateway`, `opencode-local`, `pi-local` |

#### Board Operator Guides (`docs/guides/board-operator/`)
| File | Status | Notes |
|------|--------|-------|
| `dashboard.md` | Good | Dashboard overview. |
| `creating-a-company.md` | Good | Company setup. |
| `managing-agents.md` | Good | Agent management. |
| `managing-tasks.md` | Good | Task workflows. |
| `delegation.md` | Good | CEO delegation model. |
| `org-structure.md` | Good | Org chart management. |
| `costs-and-budgets.md` | Good | Budget setup and monitoring. |
| `approvals.md` | Good | Approval workflows. |
| `activity-log.md` | Good | Audit trail. |
| `importing-and-exporting.md` | Good | Company portability. |
| `execution-workspaces-and-runtime-services.md` | Good | Workspace setup. |
| **Missing:** | | `routines` (managing scheduled jobs), `plugins` (installing/managing), `backups`, `keyboard-shortcuts`, `troubleshooting` |

#### Agent Developer Guides (`docs/guides/agent-developer/`)
| File | Status | Notes |
|------|--------|-------|
| `how-agents-work.md` | Good | Agent lifecycle. |
| `task-workflow.md` | Good | Task checkout flow. |
| `heartbeat-protocol.md` | Good | Heartbeat protocol. |
| `comments-and-communication.md` | Good | Comment system. |
| `handling-approvals.md` | Good | Approval handling from agent side. |
| `cost-reporting.md` | Good | Cost reporting. |
| `writing-a-skill.md` | Good | Skill authoring. |
| **Missing:** | | `execution-policy` (review/approval workflows — exists as `docs/guides/execution-policy.md` but not linked in agent-developer), `mcp-server` (MCP tool integration) |

#### Deployment (`docs/deploy/`)
| File | Status | Notes |
|------|--------|-------|
| `overview.md` | Good | Deployment overview. |
| `docker.md` | Good | Docker setup. |
| `database.md` | Good | Postgres config. |
| `deployment-modes.md` | Good | Loopback, LAN, Tailnet modes. |
| `environment-variables.md` | Good | Env var reference. |
| `secrets.md` | Good | Secret handling. |
| `storage.md` | Good | Storage config. |
| `local-development.md` | Good | Local dev setup. |
| `tailscale-private-access.md` | Good | Tailscale setup. |
| **Missing:** | | `backups` (backup/restore, retention), `security-hardening` |

#### Other Docs
| File | Status | Notes |
|------|--------|-------|
| `docs/feedback-voting.md` | Good | Thorough feedback system docs. |
| `docs/agents-runtime.md` | Good | Runtime internals. |
| `docs/companies/companies-spec.md` | Good | Company package spec. |
| `docs/specs/agent-config-ui.md` | Spec | Config UI spec. |
| `docs/specs/cliphub-plan.md` | Spec | ClipMart planning. |
| `docs/guides/openclaw-docker-setup.md` | Good | OpenClaw integration. |

---

## 2. Gap Analysis

### Critical Gaps (Affect daily operator workflow)

| Gap | Impact | Where it should live |
|-----|--------|---------------------|
| **Plugin system has no user-facing docs** | Users can't discover, install, or manage plugins | `docs/guides/board-operator/plugins.md` + `docs/api/plugins.md` |
| **4 adapters undocumented** | Users with Cursor/OpenCode/Pi/OpenClaw can't configure agents | `docs/adapters/{cursor,opencode,pi,openclaw}.md` |
| **Routines guide missing** | Board operators can't set up scheduled agent work | `docs/guides/board-operator/routines.md` |
| **README "Works with" table stale** | First impression misses 5 supported runtimes | `README.md` |
| **README Roadmap stale** | Items marked planned that already shipped; missing new items | `README.md` |

### Important Gaps (Affect specific workflows)

| Gap | Impact | Where it should live |
|-----|--------|---------------------|
| **Backup/restore undocumented** | Users can't set up data protection | `docs/deploy/backups.md` |
| **Execution policy not linked** | Exists at `docs/guides/execution-policy.md` but isn't in any nav/index | Link in both agent-developer and board-operator guides |
| **Keyboard shortcuts undocumented** | Users don't know `?` opens cheatsheet | Mention in `docs/start/quickstart.md` or a UI tips section |
| **MCP server package undocumented** | Users can't use Paperclip as an MCP tool provider | `docs/guides/agent-developer/mcp-server.md` |
| **Instance settings undocumented** | Users can't configure telemetry, backups, etc. from the UI | `docs/guides/board-operator/instance-settings.md` |
| **Company skills management** | Users can't manage skills per company | Fold into existing `writing-a-skill.md` or new guide |

### Housekeeping Issues

| Issue | Impact | Fix |
|-------|--------|-----|
| **`doc/` vs `docs/` duplication** | Confusing for contributors — which is canonical? | Establish `docs/` as public, `doc/` as internal. Add a note in `doc/README-draft.md` or AGENTS.md. |
| **`doc/plans/` has no index** | 30+ planning docs with no way to find them | Add a `doc/plans/README.md` index or mark as archived. |
| **`doc/TASKS.md` stale** | Old task tracking superseded by issue system | Delete or archive. |
| **`doc/PRODUCT.md` says "TBD"** | Implies features aren't built when they are | Update the TBD items. |
| **No `.doc-review-cursor`** | Doc-maintenance skill has never been run | Initialize cursor on next pass. |
| **`SECURITY.md` is minimal** | No guidance on hardening a deployment | Expand or link to `docs/deploy/` security content. |

---

## 3. Recent Features Needing Documentation (Last 90 Days)

905 commits in the last 90 days. Key features that landed:

| Feature | Commits | Documentation Status |
|---------|---------|---------------------|
| Codex fast mode | `2d8f97f` | Not documented |
| Bind presets (loopback/LAN/tailnet) | `2a84e53` | Partially in README quickstart |
| AWS Bedrock auth for Claude adapter | `f1bb175`, `07987d7` | Not documented |
| Pi adapter | `6077ae6`, `f85f2fb` | Not documented |
| Backup system (gzip, retention tiers) | `fcbae62`, `cc44d30` | Not documented |
| Keyboard shortcut cheatsheet (`?`) | `fad5634` | Not documented |
| Inbox parent-child nesting | `097f30b`, `d3e66c7` | Not documented |
| Cost/billing/quota overhaul | `76e6cc0`, `9d21380`, `56c9d95`, `f14b6e4`, `94018e0` | Partially in `docs/api/costs.md` |
| Plugin event bus bridging | `30e2914` | Not documented |
| MCP approval creation tool | `f1bb175` | Not documented |
| Execution policy system | Multiple | Documented in `docs/guides/execution-policy.md` but orphaned |
| External adapter override | `2a2fa31`, `fb3aabb` | Partially in `adapter-plugin.md` |
| Telemetry sender | `34044cd` | Not documented |
| Workspace-aware routines | `909e8cd` | Not documented |
| Skill deletion with usage check | `77f854c` | Not documented |
| GitHub Enterprise URL support | `9e1ee92` | Not documented |
| Sign-up disable option | `3860812` | Not documented |
| Gemini adapter improvements | `4e5f67e` | Partially documented |

---

## 4. Prioritized Action Plan

### Phase 1 — Fix the front door (1-2 days)

These are what users and contributors hit first.

1. **Update README.md**
   - Add Gemini, Cursor, Pi, OpenCode to "Works with" table
   - Update Roadmap: move shipped items (Plugins, Routines, Budgets, etc.) to done
   - Add new roadmap items (Backups, Execution Policy, MCP Server, etc.)
   - Verify quickstart commands are current

2. **Update `doc/PRODUCT.md`**
   - Remove "TBD" items that are now implemented
   - Add brief mentions of plugins, routines, execution policy

3. **Initialize `.doc-review-cursor`**
   - Set cursor to current HEAD so future doc-maintenance runs have a baseline

### Phase 2 — Fill critical gaps (3-5 days)

These are the docs users actively need and can't find.

4. **Write missing adapter docs:**
   - `docs/adapters/cursor-local.md`
   - `docs/adapters/openclaw-gateway.md`
   - `docs/adapters/opencode-local.md`
   - `docs/adapters/pi-local.md`

5. **Write plugin user guide:**
   - `docs/guides/board-operator/plugins.md` — installing, configuring, managing plugins from the UI
   - `docs/api/plugins.md` — plugin API endpoints

6. **Write routines guide:**
   - `docs/guides/board-operator/routines.md` — creating and managing scheduled agent work

7. **Write backup/restore guide:**
   - `docs/deploy/backups.md` — backup configuration, retention tiers, restore

### Phase 3 — Connect the dots (2-3 days)

8. **Link execution policy guide** into both agent-developer and board-operator index/nav

9. **Write instance settings guide:**
   - `docs/guides/board-operator/instance-settings.md`

10. **Write MCP server guide:**
    - `docs/guides/agent-developer/mcp-server.md`

11. **Add Bedrock auth section** to `docs/adapters/claude-local.md`

12. **Add keyboard shortcuts section** to quickstart or a new UI tips page

### Phase 4 — Housekeeping (1 day)

13. **Establish `doc/` vs `docs/` convention** — add note in AGENTS.md that `docs/` is the public documentation site, `doc/` is internal/contributor reference

14. **Add `doc/plans/README.md`** — index of planning documents with status (implemented, in-progress, abandoned)

15. **Archive stale files** — `doc/TASKS.md`, `doc/TASKS-mcp.md`

16. **Expand `SECURITY.md`** — add links to deployment hardening docs, auth configuration, bind presets

---

## 5. Scope Definition for Your Needs

As a board operator running Paperclip, your documentation priorities are:

### Must-Have (blocks your daily work)
- Accurate README with current capabilities
- Quickstart that works first try
- Adapter docs for every runtime you use
- Guide for managing routines (scheduled agent work)
- Guide for plugins (extending Paperclip)
- Backup/restore documentation

### Should-Have (improves your experience)
- Execution policy guide (review/approval workflows)
- Instance settings guide
- Keyboard shortcuts reference
- Cost/billing documentation updates
- Troubleshooting guide

### Nice-to-Have (polish)
- Consolidated doc/ vs docs/ structure
- Plan docs index
- Stale file cleanup
- Expanded security guidance

---

## 6. Estimated Effort

| Phase | Scope | Effort |
|-------|-------|--------|
| Phase 1 | Front door fixes | 1-2 days |
| Phase 2 | Critical gaps | 3-5 days |
| Phase 3 | Connect the dots | 2-3 days |
| Phase 4 | Housekeeping | 1 day |
| **Total** | | **7-11 days** |

Each phase is independently shippable. Phase 1 should happen first and can be done in a single PR.
