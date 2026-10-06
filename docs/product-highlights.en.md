# Move several projects forward, even on your own

**English** · [简体中文](product-highlights.md)

> **Turn time spent waiting for AI into work progressing in parallel.**

Caravel brings Claude Code, Codex, OpenCode, pi, Grok, TRAE, and Antigravity into a coordinated workspace where their work can be assigned, tracked, guided, and reviewed.

You set goals and make decisions. Agents search, edit, verify, and execute. Permissions, product decisions, and final acceptance bring your attention back when it is needed.

[Download Caravel for macOS / Windows](https://github.com/yy36295238/caravel-releases/releases/latest) · [Full feature guide](product-overview.en.md)

---

## Four changes to the way you work

### Move work forward in parallel

One terminal per task means waiting for searches, edits, and checks, then repeatedly switching back to see whether a run needs help.

With Caravel, different agents can fix bugs, improve docs, query data, update dependencies, and work on separate projects at the same time. Their states appear together, so you can focus on the points that need intervention.

**Use the same hour to move more work forward.**

### Turn completion into a reviewable delivery

An agent finishing its reply does not establish that the code is correct, safe, or ready to enter your project.

Caravel keeps the goal, continuing conversation, plan, permissions, code diff, and acceptance result in one task. Agents can work in isolated copies or separate branches. Review the changes, then merge, request more work, or discard them.

**A completed run leaves a visible result whose delivery you decide.**

### Keep everyday tools in one compact workspace

Delegate work, inspect files, edit configuration, read Markdown, query databases, use Git, and review diffs in Caravel. Open IDEA, VS Code, or another specialist tool when a task needs complex debugging or a large refactor.

The published macOS reference measurements below put the universal download at about 30 MB and base runtime memory at about 170 MB. The IntelliJ IDEA app on the same machine occupied about 4.1 GB, before indexes, plugins, and logs.

**Small edits can stay in the workbench without first starting and indexing a full IDE.**

### Reuse a successful approach

Save effective prompts, lessons, skills, and execution steps beyond the conversation that produced them.

Extract a workflow from a successful conversation, turn stable steps into a local script, schedule recurring work, and generate evidence-based reviews across tasks. Use the results to improve the next run.

**Build a personal way of working with AI that becomes more useful over time.**

---

## 1. Manage work, with its status in view

A terminal shows a process. Caravel shows the stage of the work:

- Tasks currently running.
- Tasks waiting for permission or additional input.
- Completed runs awaiting acceptance.
- The project, agent, and conversation behind each task.
- Current plans, tool calls, and subagent progress.
- Files changed and whether the result has been delivered.

Use a list to scan tasks, a board to follow stages, or split views to watch several important runs. A terminal remains available for taking over execution.

## 2. Spend attention where it matters

Caravel separates routine execution from decisions that need you:

- Agents handle ordinary searches, edits, and verification.
- Sensitive actions and permissions wait for confirmation.
- Agents can ask follow-up questions when a decision is needed.
- Completed code changes await review.
- Stop, correct, continue the conversation, or take over in a terminal.
- Use Feishu to follow progress, confirm actions, and accept results away from your desk.

You can leave a task running and return when your judgment is needed.

## 3. Give agents room to work with clear project boundaries

Choose the right run mode for each task:

- **Original workspace**: quick, trusted work writes directly to the original directory.
- **Isolated copy**: the agent works in a separate copy; merge after acceptance.
- **Separate branch**: one task can create copies and development branches for several Git projects, review the combined changes, and commit and push per repository while preserving the main workspaces.

Permissions, code diffs, Git actions, and acceptance give you control over the result. Request further changes or discard work that does not meet expectations.

## 4. Continue a task across agents and sessions

After a terminal closes, the app restarts, or you decide to change agents, explaining the entire background again takes time.

Caravel continues actual agent sessions and marks interrupted runs as awaiting continuation. If a session is no longer usable, a new one can continue the work. Goals and prior conversations remain available as context when changing agents.

Cleanup preserves recovery information for separate project copies so they can return at the original path. Even after a task record is deleted, a retained newer copy can start a new task; this does not recreate its old conversation.

Choose agents for their strengths, and bring existing CLI sessions into the task library.

## 5. Keep code, Git, and database context close together

Investigating an issue often means moving information between an IDE, terminal, database client, and AI conversation. Caravel puts common operations beside the task:

- Browse, search, and make lightweight edits to files.
- Preview code, Markdown, Mermaid, images, and version differences.
- Inspect branches, commit, push, stage, and resolve conflicts.
- Query MySQL, PostgreSQL, SQLite, MongoDB, and Redis.
- Generate, explain, optimize, and repair queries with SQL Copilot; link a business workspace so the agent can trace business rules using current code and database metadata, with cited files and line numbers to review.
- Confirm dangerous database operations and inspect their scope where available.
- Give agents authorized database context through MCP.

Reduce the manual work of describing context and copying results between tools.

## 6. Let recurring work run on schedule

Daily reports, weekly summaries, code scans, dependency checks, and data inspections do not need to depend on remembering each run.

- Describe a time and task, then confirm the parsed schedule.
- Run a reminder, local script, or agent at the scheduled time.
- Have an agent generate and trial a script once, then execute it deterministically without another model call each time.
- Combine agents, commands, and human checks into workflows with retries and jumps.
- Extract a workflow from a successful task and reuse it.

Stable methods can become predictable local execution.

## 7. Carry an idea through to execution

A global shortcut opens quick entry for to-dos, new tasks, or inbox notes. To-dos can include tags, subtasks, images, and attachments, then become AI tasks and follow their completion.

Enable Sessions to discuss requirements, develop ideas, and continue working with an agent without first choosing a project. Conversations share a fixed workspace, stay separate from project tasks, and support search, tags, and pinning.

The clipboard keeps text, code, JSON, and image history. My apps turns a concrete request into a report helper, dashboard, or personal tool.

With permission, desktop apps can connect local scripts, files, processes, and services into reusable tools. Their appearance can follow Caravel or use an independent design. Local permissions can be remembered and revoked by scope; program execution has the current user's privileges and should only be granted to trusted apps, as it is not a process sandbox.

Keep the path from a captured idea to an agent task within one workspace.

## 8. Keep your data and decisions under your control

The local app manages tasks, conversations, workspaces, and personal knowledge. Caravel does not require its own cloud account or tie you to a single agent.

Use your own agent CLIs, model accounts, Git, and IDE. Decide whether to enable Feishu remote access. Task history, prompts, lessons, and workflows remain part of your workspace when you change agents.

Local-first makes the boundaries clear: what is stored locally, what external agents process, and which permissions you control. Online model calls and integrations still use the network.

---

## A morning with Caravel

```text
09:00  Assign a backend bug to Codex and a docs update to Claude Code.
09:05  Continue your own work while both tasks run.
09:20  A task requests permission; approve it from your phone.
09:40  Review the first diff and ask for an additional edge-case fix.
10:00  Review and merge the second task’s isolated changes.
10:15  Turn the successful investigation into a reusable workflow.
Next week  A schedule runs similar checks and reports issues.
```

The improvement comes from less waiting, switching, monitoring, and repeated explanation.

## Resource reference

These previously published macOS measurements illustrate the order of magnitude. Usage varies by operating system, window state, configuration, and runtime. They are reference figures, not a new benchmark for this language update.

| Item | Reference usage |
|---|---:|
| macOS universal download | About 30 MB |
| Installed universal app | About 65 MB |
| Caravel base runtime memory | About 170 MB |
| With Feishu remote control enabled | About 250 MB |
| IntelliJ IDEA app on the same machine | About 4.1 GB |

Using fewer separate IDEs, database and Git clients, Markdown editors, clipboard tools, and to-do apps can release several GB of disk space and working memory in a multi-tool setup. Actual savings depend on the tools and workload.

Agent CLI processes still run and consume resources whether launched through Caravel or a terminal. Their usage is separate from the base Caravel interface. Isolated workspaces, attachments, snapshots, and history also grow over time.

## Who benefits

Developers working across projects, frequent AI coding users managing many sessions, engineers who want autonomous execution with code control, people running recurring checks and delivery processes, users building reusable prompts and workflows, and technical leads assessing agent efficiency, cost, and quality.

## Requirements and boundaries

- At least one installed and configured agent CLI is required for agent execution.
- Antigravity requires the official CLI and a working account or API configuration; the first ACP connection may require a separate browser sign-in.
- TRAE requires CLI 2.0 and an Enterprise Flagship account.
- Git workspaces require Git.
- Windows also needs Git for Windows and Node.js.
- Use a specialist IDE for breakpoint debugging, profiling, complex type navigation, and large manual refactors.
- Model-service data handling depends on the selected agent and provider.
- Caravel reduces the need to keep every development tool running at once; specialist tools remain useful when needed.

## Get started

1. Install and sign in to at least one supported agent CLI.
2. [Download Caravel for macOS / Windows](https://github.com/yy36295238/caravel-releases/releases/latest).
3. Add a local Git repository or project folder.
4. Create a task, choose an agent, and start the run.
5. Return for permission requests, decisions, and review.

[Visit the website](https://caravel-site.pages.dev/?lang=en) · [Try the demo](https://caravel-site.pages.dev/demo/?lang=en)
