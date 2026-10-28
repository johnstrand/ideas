# 💡 Ideas

A central backlog and incubator for game concepts, developer tools, AI agent experiments, and major upgrades to existing projects.

Each idea is tracked and expanded as a structured [GitHub Issue](https://github.com/johnstrand/ideas/issues) with high-concept overviews, core mechanical/architectural pillars, and MVP milestones before graduating into its own repository (or landing in an existing one).

---

## 🗂️ Active Idea Backlog

### 🎮 Game Concepts

| Issue | Concept | Genre & Perspective | Core Hook | Related Repos |
| :--- | :--- | :--- | :--- | :--- |
| **[#1](https://github.com/johnstrand/ideas/issues/1)** | **Space war sim thingy** | 3D Tactical Fleet Command + Sector Roguelite | *Homeworld* / *Nebulous: Fleet Command* style 3D positional combat with Tactical Pause, signature/E-warfare shenanigans (radar spoofing, cold-drift ambushes, active jamming), physicalized ballistics, localized subsystem damage, and a persistent ragtag fleet campaign. | [`AstroGuardian`](https://github.com/johnstrand/AstroGuardian) |
| **[#2](https://github.com/johnstrand/ideas/issues/2)** | **3D first person asteroids** | 6DoF Cockpit Arcade Roguelite | Classic toroidal wrap-around *Asteroids* reimagined inside a diegetic 3D fighter cockpit with a 3D holographic radar globe, toggleable Flight-Assist / Newtonian drift, momentum-conserving rock fracturing, ore-driven between-wave upgrades, and UFO hunter/boss waves. | — |
| **[#4](https://github.com/johnstrand/ideas/issues/4)** | **2d squad based shooter** | 2D Top-Down Real-Time-with-Pause (RTwP) CQB Roguelite | *Door Kickers* + *XCOM* meets `RootinTootin`: command a 4-operator squad across procedural floors with waypoint path drawing, decoupled firing cones, synchronized Go-Code room breaches, directional cover/suppression, and GPU raymarched line-of-sight fog of war. | [`rootintootin-public`](https://github.com/johnstrand/rootintootin-public) |

---

### 🤖 AI & Agent Tooling

| Issue | Concept | Stack & Domain | Core Hook |
| :--- | :--- | :--- | :--- |
| **[#5](https://github.com/johnstrand/ideas/issues/5)** | **My own stupid ollama-based harness** | C# / .NET 10 • Roslyn • Ollama | Build large software systems using small local models (3B–14B) by enforcing extreme decomposition: Contract-First DAG planning, deterministic Roslyn AST context slicing (<1.5k tokens per task), structured single-symbol output (zero open-ended tool calls), and an automated `dotnet build` + xUnit TDD gatekeeper loop that recursively splits failing nodes. |

---

### 🛠️ Developer Tools & Project Upgrades

| Issue | Concept | Target Project | Planned Upgrades |
| :--- | :--- | :--- | :--- |
| **[#3](https://github.com/johnstrand/ideas/issues/3)** | **Update SQL Server audit tool** | **[`sqlsrvaudit`](https://github.com/johnstrand/sqlsrvaudit)** | 1. **Self-Contained Interactive HTML Report (`--format html`)** with live severity/category/window filtering, object search, and one-click copyable SQL fix scripts.<br>2. **Execution Plan XML & T-SQL Anti-Pattern Checks** (`CONVERT_IMPLICIT`, key lookup hotspots, non-SARGable predicates, missing-index consolidation).<br>3. **Offline Snapshot Re-Analysis (`analyze --snapshot`)** and **Multi-Database / Instance-Wide Batch Scanning**. |

---

## 🔄 Workflow

1. **Capture**: Drop raw sparks and one-liners as new [Issues](https://github.com/johnstrand/ideas/issues/new).
2. **Expand**: Flesh out the issue body into a structured design spec covering core pillars, technical architecture, and MVP milestones.
3. **Graduate**: Spin the spec out into a dedicated repository (typically C# / .NET 10 / Raylib-cs for games, or .NET 10 CLI/Web for tools) or transfer the implementation checklist into the target repo.
