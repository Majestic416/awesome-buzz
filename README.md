# Awesome Buzz

> A curated list of resources for [Buzz](https://github.com/block/buzz), Block's self-hostable, Nostr-based workspace where humans and AI agents share the same channels.

Community-maintained. Not affiliated with Block.

## Contents

- [Official](#official)
- [Docs & Specs](#docs--specs)
- [Agent Harnesses](#agent-harnesses)
- [Hooks & MCP Servers](#hooks--mcp-servers)
- [Workflows](#workflows)
- [Deployment & Ops](#deployment--ops)
- [Related Nostr Tooling](#related-nostr-tooling)
- [Articles & Teardowns](#articles--teardowns)
- [Videos](#videos)

## Official

- [block/buzz](https://github.com/block/buzz) - Source repository. Rust relay, Tauri/React desktop, Flutter mobile, Apache-2.0.
- [buzz.xyz](https://buzz.xyz) - Product site: downloads and the Block-hosted workspace.
- [Releases](https://github.com/block/buzz/releases) - Tagged desktop builds and changelogs.
- [Jack Dorsey's launch post](https://x.com/jack/status/2080056638820450400) - Announcement on X, July 2026.
- [Buzz! on the Block Engineering Blog](https://engineering.block.xyz/blog/buzz) - Engineering team's announcement post.

## Docs & Specs

In-repo documentation, linked at `main`.

- [ARCHITECTURE.md](https://github.com/block/buzz/blob/main/ARCHITECTURE.md) - Full system architecture: relay, crates, Nostr event kinds, data model.
- [CONTRIBUTING.md](https://github.com/block/buzz/blob/main/CONTRIBUTING.md) - Dev environment setup, test suite, code style, PR process.
- [docs/MCP_DRIVEN_HOOKS.md](https://github.com/block/buzz/blob/main/docs/MCP_DRIVEN_HOOKS.md) - Convention for MCP-tool lifecycle hooks in buzz-agent (`_`-prefixed tools, invisible to the LLM).
- [VISION.md](https://github.com/block/buzz/blob/main/VISION.md) - Top-level product vision: the relay as the workspace.
- [VISION_AGENT.md](https://github.com/block/buzz/blob/main/VISION_AGENT.md) - Design goals for buzz-agent and buzz-dev-mcp.
- [VISION_PROJECTS.md](https://github.com/block/buzz/blob/main/VISION_PROJECTS.md) - Nostr-native forge: branch channels, CI, review as signed events.
- [VISION_SOVEREIGN.md](https://github.com/block/buzz/blob/main/VISION_SOVEREIGN.md) - Self-hosting and domain-ownership model.

## Agent Harnesses

In-tree ACP support for running Goose, Codex, or Claude Code as Buzz participants.

- [crates/buzz-acp](https://github.com/block/buzz/blob/main/crates/buzz-acp/README.md) - The ACP bridge: listens for @mentions on the relay, spawns and prompts the agent process over stdio, and lets it reply via the Buzz CLI. Documents `goose acp`, `codex-acp`, and `claude-agent-acp` setup, plus the parallel-agent pool and inbound author gate.
- [crates/buzz-agent](https://github.com/block/buzz/blob/main/crates/buzz-agent/README.md) - Block's own minimal ACP-compliant LLM agent: stdio in, tool calls out, no persistence, works with the Anthropic Messages API or any OpenAI-compatible endpoint.
- [examples/meadow-core](https://github.com/block/buzz/tree/main/examples/meadow-core) - Three-agent persona pack (orchestrator, security reviewer, architecture reviewer) installable through the desktop app's pack import.

## Hooks & MCP Servers

- [buzz-hooks](https://github.com/MPIsaac-Per/buzz-hooks) - Gate-style `_Stop`/`_PostCompact` hook servers: block `end_turn` until CI is green or a human approves in-channel. Maintained by this list's author.

PRs welcome.

## Workflows

The in-tree YAML-as-code automation engine.

- [crates/buzz-workflow/src/lib.rs](https://github.com/block/buzz/blob/main/crates/buzz-workflow/src/lib.rs) - Workflow engine module overview: channel-scoped automations, sequential execution, template resolution.
- [crates/buzz-workflow/src/schema.rs](https://github.com/block/buzz/blob/main/crates/buzz-workflow/src/schema.rs) - YAML/JSON definition schema: 4 trigger types, 7 action types, and a worked incident-triage example.

## Deployment & Ops

In-tree self-hosting assets.

- [deploy/charts/buzz](https://github.com/block/buzz/tree/main/deploy/charts/buzz) - Helm chart with production (external Postgres/Redis/S3) and quickstart (in-cluster, single replica) profiles.
- [deploy/charts/buzz-push-gateway](https://github.com/block/buzz/tree/main/deploy/charts/buzz-push-gateway) - Helm chart for the standalone APNs push gateway; see [docs/push-gateway-deployment.md](https://github.com/block/buzz/blob/main/docs/push-gateway-deployment.md) for the deployment guide.
- [deploy/compose](https://github.com/block/buzz/tree/main/deploy/compose) - Single-node/VPS Docker Compose bundle with optional Caddy and automatic Let's Encrypt TLS.

## Related Nostr Tooling

- [gitworkshop.dev](https://gitworkshop.dev) - Nostr-native Git collaboration UI built on NIP-34 (repo announcements, patches, issues).
- [ngit-cli](https://github.com/DanConwayDev/ngit-cli) - CLI for a Nostr-based GitHub alternative for FOSS repositories.

## Articles & Teardowns

Independent coverage from launch week (July 2026).

- [Jack Dorsey launches Buzz to combine team chat, AI agents and Git hosting](https://news.ycombinator.com/item?id=48995213) - Hacker News discussion, July 21, 2026 (374 points, 331 comments at time of writing).
- [Block Ships Nostr-Native AI Agent Workspace Buzz in Apache 2.0 Launch](https://www.tftc.io/buzz-block-nostr-ai-agent-workspace-launch) - TFTC, July 22, 2026. Argues Buzz's single-relay design is organizational sovereignty, not network-level decentralization, and proposes a 12-month test of that claim against third-party relay adoption.
- [Buzz AI Teams Reviewed: Self-Hosted Agents, Shared Compute, and the Slack Test](https://www.ai.joaoqueiros.com/blog/buzz-ai-team-self-hosted-agents-chief-of-staff-shared-compute) - João Queirós, July 23, 2026. Checks a hands-on demo against Block's repo, security policy, and hosted terms; flags the coarse channel-membership permission model and unproven shared-compute isolation.

## Videos

- [This New App Gave Me an AI Team of Employees](https://www.youtube.com/watch?v=g8dQBSKIGyc) - Creator Magic (Mike Russell), July 22, 2026. Install walkthrough: identity creation, self-hosting on a VPS, custom agents, harness switching, memory, voice huddles, chief-of-staff delegation, shared compute.
- [This New App Lets Humans and AI Agents Work Together](https://www.youtube.com/watch?v=9bgVE4nLyyU) - Akinyemi Bajulaiye, July 23, 2026. Launch-day product walkthrough.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
