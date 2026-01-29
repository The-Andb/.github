# 🌌 The-Andb Ecosystem

![Andb Logo](./andb-logo-transparent.png)

> **The ultimate database orchestration platform.** Seamlessly manage schema migrations, comparisons, and deployments across environments with high-performance engines and intuitive interfaces.

---

## 🏗️ Project Architecture

This repository is a **Monorepo** managed with NPM Workspaces. It orchestrates multiple specialized packages to provide a complete database management lifecycle.

### 📦 Component Matrix

| Package                 | Directory    | Role                                                    | Tech Stack                         | Status         |
| :---------------------- | :----------- | :------------------------------------------------------ | :--------------------------------- | :------------- |
| **@the-andb/core-nest** | `core-nest/` | **The Brain (Next-Gen)** - NestJS backend for DB logic. | NestJS, TypeScript, Better-SQLite3 | 🚀 Active      |
| **@the-andb/ui-next**   | `ui-next/`   | **The Face (Next-Gen)** - Modern Desktop App UI.        | Electron, Vue 3, Vite              | 🎨 Beta        |
| **@the-andb/cli**       | `cli/`       | **The Tool** - Terminal interface for CI/CD automation. | Node.js, TypeScript                | ✅ Stable      |
| **@the-andb/core**      | `core/`      | **Legacy Core** - Pure logic library (Legacy).          | Node.js, TypeScript                | 🔧 Maintenance |
| **@the-andb/ui**        | `ui/`        | **Legacy UI** - Original Desktop Application.           | Electron, Vue 2                    | 🔧 Maintenance |
| **@the-andb/landing**   | `landing/`   | **Marketing** - Official landing page & docs.           | Vite, HTML/CSS                     | ✅ Stable      |

---

## � Quick Start

### 1. Prerequisites

- **Node.js** (v18+)
- **NPM** (v9+)
- **Docker & Docker Compose** (for local DB testing)

### 2. Installation & Build

```bash
# Install dependencies for all workspaces
npm install

# Build the core engine
npm run build:core
```

### 3. Launching the App

We use workspace-aware scripts to run components from the root:

| Command               | Action                                         |
| :-------------------- | :--------------------------------------------- |
| `npm run ui-next`     | Launch the **Next-Gen UI** in development mode |
| `npm run andb:nest`   | Run core-nest commands                         |
| `npm run dev:cli`     | Start CLI in development mode                  |
| `npm run ui`          | Launch the **Legacy UI**                       |
| `npm run dev:landing` | Launch the landing page locally                |

---

## 🐳 Infrastructure (Local Databases)

The `docker/` directory contains configurations to spin up a full range of databases (MySQL/PostgreSQL) mirroring typical Dev/Stage/UAT/Prod environments.

### Spin up the Test Suite

```bash
# Start MySQL cluster (Ports: 3307-3310)
docker-compose -f docker/docker-compose.yml up -d

# Start PostgreSQL cluster (Ports: 5433-5436)
docker-compose -f docker/docker-compose-postgres.yml up -d
```

| Env       | MySQL Port | PG Port | User                | Password            | DB Name      |
| :-------- | :--------- | :------ | :------------------ | :------------------ | :----------- |
| **Dev**   | `3307`     | `5433`  | `root` / `postgres` | `root` / `postgres` | `andb_dev`   |
| **Stage** | `3308`     | `5434`  | `root` / `postgres` | `root` / `postgres` | `andb_stage` |
| **UAT**   | `3309`     | `5435`  | `root` / `postgres` | `root` / `postgres` | `andb_uat`   |
| **Prod**  | `3310`     | `5436`  | `root` / `postgres` | `root` / `postgres` | `andb_prod`  |

---

## 🛠️ Development Workflow

### Symlinking & Workspaces

The project uses **NPM Workspaces**, which automatically handles internal dependencies. No more manual `npm link`!

- `@the-andb/ui-next` depends on `@the-andb/core-nest`.
- `@the-andb/cli` depends on `@the-andb/core`.

### Watch Mode

When developing the core, use watch mode to auto-rebuild:

```bash
# For core-nest
npm run start:dev --workspace=core-nest
```

---

## 📂 Folder Guide

- `.agent/`: Automation and workflow definitions for AI assistance.
- `plans/`: Detailed architectural specs and roadmaps.
- `docker/`: DB initialization scripts and compose files.
- `ai/`: Specialized AI context for deep-dive tasks.

---

## �️ Key Resources

- **[Architecture Specs](./plans/ARCHITECTURE.md)**: Deep dive into the system design.
- **[Development Plan](./plans/MAIN_PLAN.md)**: Current roadmap and feature tracking.
- **[AI Context](./ai/CONTEXT.md)**: High-level context for AI-assisted development.
- **[Quality Control](./plans/QUALITY_CONTROL_PLAN.md)**: Testing strategies and standards.

---

## �📜 License

© 2026 The-Andb Team. All rights reserved.
