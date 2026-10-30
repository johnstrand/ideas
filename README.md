# 💡 Ideas

A central backlog and incubator for game concepts, developer tools, AI agent experiments, and major upgrades to existing projects.

Each idea is tracked and expanded as a structured [GitHub Issue](https://github.com/johnstrand/ideas/issues) with high-concept overviews, core mechanical/architectural pillars, and MVP milestones before graduating into its own repository (or landing in an existing one).

---

## 🗂️ Active Idea Backlog

### 🎮 Game Concepts

| Issue | Concept | Genre & Perspective | Core Hook | Related Repos |
| :--- | :--- | :--- | :--- | :--- |
| **[#4](https://github.com/johnstrand/ideas/issues/4)** | **2d squad based shooter** | 2D Top-Down Real-Time-with-Pause (RTwP) CQB Roguelite | *Door Kickers* + *XCOM* meets `RootinTootin`: command a 4-operator squad across procedural floors with waypoint path drawing, decoupled firing cones, synchronized Go-Code room breaches, directional cover/suppression, and GPU raymarched line-of-sight fog of war. (Issues tagged `<model>-<effort>`). | [`rootintootin-public`](https://github.com/johnstrand/rootintootin-public) |
| **[#6](https://github.com/johnstrand/ideas/issues/6)** | **Rules-driven turned based combat game** | Turn-Based Programmable Tactics RPG | *Final Fantasy XII* Gambits / *Dragon Age: Origins* Tactics style combat where players program party member behaviors using declarative `condition` / `action` rules (e.g., `Healer: condition = any(party, p: p.health < 20%)`). | — |

---

### 🤖 AI & Agent Tooling

| Issue | Concept | Stack & Domain | Core Hook |
| :--- | :--- | :--- | :--- |
| **[#5](https://github.com/johnstrand/ideas/issues/5)** | **My own stupid ollama-based harness** | C# / .NET 10 • Roslyn • Ollama | Build large software systems using small local models (3B–14B) by enforcing extreme decomposition: Contract-First DAG planning, deterministic Roslyn AST context slicing (<1.5k tokens per task), structured single-symbol output (zero open-ended tool calls), and an automated `dotnet build` + xUnit TDD gatekeeper loop that recursively splits failing nodes. |

---

### 🛠️ Developer Tools & Project Upgrades

| Issue | Concept | Target / Stack | Core Hook & Planned Features |
| :--- | :--- | :--- | :--- |
| **[#3](https://github.com/johnstrand/ideas/issues/3)** | **Update SQL Server audit tool** | **[`sqlsrvaudit`](https://github.com/johnstrand/sqlsrvaudit)** | 1. **Self-Contained Interactive HTML Report (`--format html`)** with live severity/category/window filtering, object search, and one-click copyable SQL fix scripts.<br>2. **Execution Plan XML & T-SQL Anti-Pattern Checks** (`CONVERT_IMPLICIT`, key lookup hotspots, non-SARGable predicates, missing-index consolidation).<br>3. **Offline Snapshot Re-Analysis (`analyze --snapshot`)** and **Multi-Database / Instance-Wide Batch Scanning**. |
| **[#7](https://github.com/johnstrand/ideas/issues/7)** | **Simple 3d editor for games** | C# / .NET 10 • Raylib-cs • ImGui.NET | *TrenchBroom* meets *Blender* for simple 3D games: single Perspective/Ortho (`X`/`Y`/`Z`) viewport, parametric primitives, half-edge N-gon vertex/edge/face editing, draggable 3D transform gizmo handles + `X`/`Y`/`Z` (`Shift+` plane) locks, CSG mesh booleans, auto-planar UV texturing, `player_spawn`/`light`/`portal` entities, per-element key-value metadata, built-in First-Person Walk preview, and a dual-layer JSON level format. |

---

## 🎓 Graduated & Closed Ideas

Ideas that have been expanded and spun out into dedicated repositories:

| Issue | Concept | Category | Summary | Graduated Repo |
| :--- | :--- | :--- | :--- | :--- |
| **[#1](https://github.com/johnstrand/ideas/issues/1)** | **Space war sim thingy** | 3D Tactical Fleet Command + Sector Roguelite | *Homeworld* / *Nebulous: Fleet Command* style 3D positional combat with Tactical Pause, signature/E-warfare shenanigans (radar spoofing, cold-drift ambushes, active jamming), physicalized ballistics, localized subsystem damage, and a persistent ragtag fleet campaign. | **[`this-fleet-of-mine`](https://github.com/johnstrand/this-fleet-of-mine)** (`ThisFleetOfMine`) |
| **[#2](https://github.com/johnstrand/ideas/issues/2)** | **3D first person asteroids** | 6DoF Cockpit Arcade Roguelite | Classic toroidal wrap-around *Asteroids* reimagined inside a diegetic 3D fighter cockpit with a 3D holographic radar globe, toggleable Flight-Assist / Newtonian drift, momentum-conserving rock fracturing, ore-driven between-wave upgrades, and UFO hunter/boss waves. | **[`asteroids-3d`](https://github.com/johnstrand/asteroids-3d)** (`Asteroids3d`) |
| **[#7](https://github.com/johnstrand/ideas/issues/7)** | **Simple 3d editor for games** | 3D Level & Blockout Editor | Cross between *TrenchBroom* and *Blender* built on a headless half-edge N-gon mesh kernel: single-viewport perspective/ortho navigation, draggable 3D gizmos + `G`/`R`/`S` axis/plane constraints, parametric primitives, CSG booleans, auto-projected UVs, gameplay entities, walk-mode preview, and dual-layer `.level.json` export. | **[`leed-3d`](https://github.com/johnstrand/leed-3d)** (`Leed3d`) |

---

## ⚡ Agent Runner Template (`run-agent.ps1`)

[`run-agent.ps1`](./run-agent.ps1) is the canonical Antigravity CLI (`agy`) issue runner template used across graduated projects (adapted from `RootinTootin3d/run-agent.ps1`). Copy it into any project repository to automate sequential issue execution:

- **Dependency Unblocking (`on hold` → `ready`)**: Inspects open `on hold` issues (skipping those labeled `review needed` or `question`) and automatically promotes them to `ready` once all `Depends on: #...` prerequisites are closed—or closes `Tracking Epic: true` issues once all sub-issues finish.
- **Model & Effort Routing**: Picks the lowest-numbered open `ready` issue and extracts the target model and effort from `<model>-<effort>` labels (e.g., `gemini-4-argon-high`).
- **Real-Time Streaming & Session Persistence**: Streams NDJSON tool calls and responses to the console while persisting the active conversation ID in `.agy_session` across issues.
- **Post-Run Safeguards**: Automatically commits, pushes to the active branch (`main`/`master`), closes the completed issue, and re-evaluates blocked downstream issues. Use `-Loop` for continuous execution or `-NewSession` to reset context.

---

## 🔄 Workflow

1. **Capture**: Drop raw sparks and one-liners as new [Issues](https://github.com/johnstrand/ideas/issues/new).
2. **Expand**: Flesh out the issue body into a structured design spec covering core pillars, technical architecture, and MVP milestones.
3. **Graduate**: Spin the spec out into a dedicated repository (typically C# / .NET 10 / Raylib-cs for games, or .NET 10 CLI/Web for tools), copy [`run-agent.ps1`](./run-agent.ps1) and tag issues with `ready` / `on hold` and `<model>-<effort>`, and close the incubator issue.
