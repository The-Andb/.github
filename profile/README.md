<p align="center">
  <img src="https://avatars.githubusercontent.com/u/252973475" width="120" alt="The-Andb">
</p>

<h1 align="center">The-Andb</h1>
<p align="center"><b>Database schema evolution, as easy as Git.</b></p>

<p align="center">
  <a href="https://github.com/The-Andb/andb-desktop/releases"><img src="https://img.shields.io/github/v/release/The-Andb/andb-desktop?style=for-the-badge&color=8A2BE2" alt="Release"></a>
  <a href="https://github.com/The-Andb/andb-core/blob/main/LICENSE"><img src="https://img.shields.io/badge/License-AGPL--3.0-blue?style=for-the-badge&logo=gnu" alt="License"></a>
  <a href="https://github.com/sponsors/The-Andb"><img src="https://img.shields.io/badge/Sponsor-%E2%9D%A4-ff69b4?style=for-the-badge&logo=githubsponsors" alt="Sponsor"></a>
</p>

---

## What we're building

Most teams still treat database schemas the way they treated code before Git: manual diffs, tribal knowledge about what changed in prod, and a migration script someone wrote at 11pm hoping it's right.

**The-Andb is a schema reliability engine.** It reads your database structure as a semantic model — not just text — so you can diff `dev` against `prod`, catch destructive changes before they run, and generate migrations without guessing.

## Why AGPL-3.0, not open-core

Everything here — engine, CLI, MCP server, desktop app — ships under the same [AGPL-3.0](https://github.com/The-Andb/andb-core/blob/main/LICENSE) license. Nothing is held back behind a proprietary build.

We picked AGPL-3.0 specifically because it closes the SaaS loophole regular open-source licenses leave open: if someone re-hosts a modified TheAndb as a service, they have to publish their changes too. That's what lets us stay fully open without the code getting quietly forked into someone else's paid product. Sustainability comes from **sponsorship**, not from what's locked away.

## The ecosystem

Each repo does one job, and they compose into the same pipeline — inspect a schema, diff it, and act on the diff:

| Repo | Role |
|---|---|
| 🧠 **[andb-core](https://github.com/The-Andb/andb-core)** | The engine. AST-based SQL parsing, semantic diffing, and migration generation. Everything else is a client of this. |
| 🖥 **[andb-desktop](https://github.com/The-Andb/andb-desktop)** | Visual schema comparison and drift auditing (Electron + Vue 3). Where most people meet the project first. |
| ⚙️ **[andb-cli](https://github.com/The-Andb/andb-cli)** | The same engine, wired for automation — `andb compare`/`andb export` in CI/CD pipelines. |
| 🤖 **[andb-mcp](https://github.com/The-Andb/andb-mcp)** | Model Context Protocol server, so AI agents (Claude, ChatGPT) can run safe, read-audited schema checks. |
| 🌐 **[andb-www](https://github.com/The-Andb/andb-www)** | This project's public site and docs. |
| 📂 **[andb-monorepo](https://github.com/The-Andb/andb-monorepo)** | Orchestrates the repos above for local development — clone-all, docs, Docker fixtures. |

## Tech stack

<p align="left">
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" />
  <img src="https://img.shields.io/badge/Vue.js-35495E?style=for-the-badge&logo=vuedotjs&logoColor=4FC08D" />
  <img src="https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white" />
  <img src="https://img.shields.io/badge/Electron-47848F?style=for-the-badge&logo=electron&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" />
</p>

## Contributing

We're a small team, actively reviewing incoming issues and discussions. Bug reports and feature requests via GitHub Issues on the relevant repo are the fastest way to reach us. If you're picking up an issue to fix, comment first so we don't duplicate work.

## Support the project

Sponsorship doesn't unlock anything — it's already all AGPL-3.0. What it funds is the time behind it: development, testing across MySQL/Postgres, CI/CD, and keeping releases shipping on a predictable cadence.

**[Become a sponsor →](https://github.com/sponsors/The-Andb)**

---

<p align="center">
  ⭐ Star the repos you use · 🐛 File issues you hit · ❤️ <a href="https://github.com/sponsors/The-Andb">Sponsor</a> if TheAndb saves you time
</p>
