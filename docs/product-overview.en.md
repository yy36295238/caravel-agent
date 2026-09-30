# Caravel product and feature guide

**English** · [简体中文](product-overview.md)

## Product positioning

**Caravel is a local-first workspace for multiple AI coding agents, built for developers working across projects and tasks. It supports macOS (Apple Silicon / Intel) and Windows x64.**

Both platforms provide the complete app with all feature modules and retain existing application data. macOS and Windows x64 support signed in-app updates; older Windows clients require a manual upgrade to a version that supports automatic updates. Choose your platform on the [download page](https://github.com/yy36295238/caravel-releases/releases/latest). See the [installation help](https://caravel-site.pages.dev/?lang=en#install-help) for first-launch instructions.

Caravel brings Claude Code, Codex, OpenCode, pi, Grok, TRAE, and other coding agents into one desktop workbench. Delegate tasks, track progress, handle permissions, review code, and deliver changes in one place. Install or upgrade agents from Settings.

Keep using your own agent CLIs, model accounts, and IDE. Caravel organizes agents, projects, conversations, and code changes into a clear task workflow.

## Why Caravel exists

A CLI is straightforward for one or two tasks. With several projects and agents running at once, it becomes harder to know which task is running, waiting for input, or ready for review—and which conversation belongs to which project.

Developers end up maintaining a mental table of terminals, projects, agents, goals, permissions, and changes. Managing the agents becomes a bottleneck of its own.

Caravel turns these separate execution sessions into traceable tasks. Each task has a goal, workspace, agent, ongoing conversation, status, and final code changes. Delegate, monitor, intervene, and review from one workbench.

## Core value

- **Unified management**: multiple agents, projects, and parallel tasks in one workspace.
- **Visible progress**: follow execution, agent actions, pending decisions, and results.
- **Controlled delivery**: permissions, code review, and acceptance determine how changes reach your project.
- **Reusable methods**: save prompts, skills, lessons, and successful workflows.
- **Continuous improvement**: use cost insights and AI reviews to improve collaboration.
- **Tools close at hand**: schedules, databases, and small apps support everyday work.

## Feature map

| Area | Capabilities | Purpose |
|---|---|---|
| Core workflow | Agent coordination, tasks, safe delivery, mobile collaboration | Manage delegation, intervention, and code review |
| Automation | Schedules and workflows | Run recurring tasks and structured processes |
| Knowledge and effectiveness | Prompts, skills, lessons, insights, reviews | Reuse methods and assess results, cost, and runtime health |
| Development tools | Editor, databases, to-dos, inbox, clipboard, apps | Handle everyday development and personal productivity |
| Settings and environment | Agents, plugins, models, permissions, maintenance | Manage tools, capabilities, and preferences |

## Features

### 1. Workbench

Create and manage AI agent tasks with list, board, and split views.

The filter bar groups session sync, view, and split controls under “More actions” when space is limited. In list view, press `⌘F` (`Ctrl+F` on Windows/Linux) to search the current conversation, see match counts, and navigate with `Enter / Shift+Enter`. Press `Esc` to close and clear highlights. Split views search the focused conversation; embedded workflow conversations support the same controls.

- Manage Claude Code, Codex, OpenCode, pi, Grok, and TRAE together. Invocation controls combine a brand icon, agent dropdown, and model selection; Settings retains full enablement controls.
- Conversations, permissions, plans, subagent progress, code diffs, and delivery share one page. Drag the plan card within its conversation area, adjust it with arrow keys, or press Home to reset it.
- Play each completed assistant reply continuously at a speed adapted to its length. Reasoning and tool activity remain live while waiting for the full reply. History, synchronized records, and web polling snapshots appear in full; returning to the window shows finalized text immediately.
- Image links in completed desktop replies become thumbnails that open enlarged previews. Switch chat SVG images between preview and read-only source, with text selection and copying.
- Local video links and recognized inline-code paths in completed desktop replies show video thumbnails. Click to play from the beginning inside the message, with seeking, volume, and fullscreen controls. Videos do not autoplay and stop when leaving the conversation; unsupported files can open externally.
- Closed Mermaid code blocks in desktop and mobile chats and workflow output support diagram/text switching and zoom. Feishu conversation snapshots also render diagrams; unfinished code blocks retain their source.
- Choose a model and reasoning effort for a new task, a continuation, or a conversation fork. Defaults follow model settings. Manage models in Agent settings; historical tasks retain their existing model selection. Task headers show the latest known reasoning effort; continuations retain it without overwriting manual choices.
- Scrolling toward the top loads earlier messages while preserving your reading position, including task quick previews and mobile task details.
- Task turn counts and active time cover the full conversation, independently of message pagination. Active time excludes idle waits for input between turns.
- Automatic task titles are optional under Settings → Agent → General and default to off for both new and existing users. When enabled, the selected agent and model summarize long goals for new tasks without blocking execution; desktop, web, and mobile details show generation status. Turning it off keeps the original name and discards pending summaries. Existing tasks, manual AI generation, full goals, and manual names are preserved.
- Link several workspaces to a task and view directly or indirectly related tasks. Before creating a task, use the linked-workspace dialog to switch branches, commit, pull, and push in the primary and linked repositories; these operations affect the original workspace directories.
- Separate-branch tasks can create an isolated copy for each Git project, with per-project remote main/master baselines and development branches. Add projects, inspect connection status, browse files, and use Git from the task’s project panel.
- Enter a separate branch name manually or generate it with the selected agent and model using the task, Jira ID, and specified skill rules. The same request generates a short task title for task creation and the copy directory. Edits made during generation are preserved; missing information can be supplied or names entered manually. The branch is created only after submission.
- AI titles focus on the core action and subject. New separate-branch task and project directory names use only ASCII letters, digits, and `-_.`, falling back to `workspace` when empty and appending IDs to distinguish names. The task-name portion is limited to 20 characters; existing paths and full task goals remain available.
- Projects added during a run join the next run, or you can pause, attach, and continue. Multi-project execution requires agent or adapter support for additional working directories.
- Copy conversation messages as text or images.
- Mark mistakenly sent user messages as deleted on desktop and the full web interface using the delete icon and confirmation dialog; canceling submits nothing. Keep struck-through text and submit one correction asking the agent to ignore the message and attachments and await further input. Stop running tasks first. Marks survive history sync and appear read-only on mobile; native history and completed actions are not undone.
- Startup and periodic checks reconcile running tasks and pending confirmations whose processes have exited. Explicitly interrupted tasks await continuation without restarting automatically. Codex/TRAE runs without current-turn records or a clear final state are marked as failed.
- Repeated continuation requests replace the previous run and its pending questions, waiting for its process to exit before restoring the conversation. Requests for one task are handled in arrival order; different tasks can still run in parallel.
- Copy files from Finder or File Explorer and paste them as attachments when creating tasks or continuing conversations, preserving filenames and removing duplicate paths. Workflows, to-dos, and inbox notes share the same attachment support. Desktop context menus paste text, images, and files into the active input area without sending attachments to another pane or dialog.
- Stop a task at any time or take over in a terminal. Stopping reclaims processes for all unfinished runs of that task and reports an error if a process cannot exit.

#### Sessions

Enable Sessions in Settings → Features; it is off by default. Start a conversation without first choosing a project. Sessions share a fixed workspace directory and appear separately from regular tasks in Workbench and Tasks. Turning off the entry preserves history.

- Sending the first message creates a session. Choose an agent, model, reasoning effort, permissions, attachments, skills, and task references, with a separate draft for new sessions.
- Search by keyword, date, and tags, showing today by default. Pin, favorite, tag, open historical links, or delete with confirmation.
- Follow streaming conversations, handle permissions, stop and continue runs, and view usage, cost, duration, and turns. Resize the list or switch between list and conversation in narrow windows.

### 2. Task library

Keep and find historical tasks in one place.

- Filter by status, agent, workspace, date, and related tasks.
- Search, favorite, archive, and group tasks.
- Search sidebar workspaces by name or path. Matching groups expand temporarily; clearing the search restores their previous state.
- Import and synchronize existing agent sessions, including native and officially migrated TRAE CLI 2.0 sessions. Codex supports both older and newer session formats. Rebuilding preserves image attachments and reply ratings; incomplete parsing or failed writes retain the original conversation while reconciling run status separately. Manual sync reports incomplete conversation updates; historical runs do not overwrite the current task status.
- Open workspaces and manage Git branches, commits, pushes, and conflicts. Remove separate-branch entries even when their local copy is missing. Cleaned projects with missing directories are hidden while tasks and recovery information remain available.
- Diffs default to full-file context when no preference is saved, and remember subsequent compact or full-file choices.
- Commit only selected files while preserving unselected staged changes and tracked-file deletions. Task headers show the branch and changed-file count.
- Pulling remote updates shows progress and keeps Git output, file and line-change statistics, up-to-date messages, or failure details visible until dismissed. Detected merge operations with conflicts can open the conflict resolver.
- Choose a model and generate a commit message directly in the commit dialog, edit the draft, then commit or commit and push. Generated summaries use a type prefix by default and prioritize explicit formatting instructions. Additional instructions stay available when collapsed; search and reuse the latest 20 entries shared across repositories on this machine, or delete individual entries without changing the current input.

### 3. Schedules

Automate work that runs daily, weekly, at intervals, or just once.

- Describe the time and task in natural language; review the parsed form before creating the schedule.
- Alternatively, enter the name, instructions, and recurrence manually.
- Run daily, weekly, every few minutes or hours, or once.
- Set multiple times for daily or weekly schedules, such as 09:30 and 20:30.
- Restrict interval schedules to selected weekdays and working hours.
- Choose local reminders, local scripts, or agent execution. Reminders do not call an agent. Agents can generate and trial a script once, then run it on schedule without repeated model calls; shell and PowerShell are supported.
- Optionally catch up on runs missed while the computer was unavailable.
- Run a schedule immediately to inspect its behavior.
- Review run history and output, with optional notification cards.
- Pause, edit, or delete schedules; use list or card views and see the next run time.

### 4. Editor

Browse, search, and edit project files.

- Multiple tabs, syntax highlighting, and autosave.
- The desktop editor previews MP4, MOV, WebM, MKV, and AVI videos by reading local files on demand. Playback depends on system codec support, with an external-app fallback; web and mobile clients retain file information.
- Markdown (including embedded SVG images), Mermaid, and image previews; open pasted file or directory paths.
- SVG file quick previews show the image by default and can switch to read-only source; line references open source first.
- Inspect, locate, and revert changes relative to the last commit, including image comparisons in diffs.
- Copy full paths, open complete diffs, and use common Git actions from file previews. Collapse directories in the diff file tree.
- Open the current directory in an installed external editor and remember that preference. Supported locations include the main workspace, linked directories, and isolated copies.

- HTML file quick previews render the webpage by default and can switch to read-only source; line references open source first. Inline styles, scripts, and data resources work in isolation. Desktop previews also load CSS, JavaScript, images, fonts, and media from the current directory and subdirectories, up to 20 MiB per resource. Switching or closing the preview revokes access. Host permissions remain isolated; resources outside the directory, remote resources, and API requests are blocked. Browser previews support inline resources only.

### 5. Databases

Connect to MySQL, PostgreSQL, SQLite, MongoDB, or Redis to query and edit data.

- Browse objects, filter and page through data, open local SQLite files, query MongoDB documents, and manage Redis keys.
- Write SQL or document queries, inspect and edit results, and export complete results, including SQL output. For editable results, cell and row-detail value dialogs let you edit raw text, set NULL, and stage changes for confirmation and submission in the results panel.
- Resize result columns by dragging or keyboard; hidden columns and horizontal scrolling retain correct field positions.
- Generate, explain, optimize, and repair queries with a conversational SQL Copilot. Editor SQL is excluded from ordinary questions by default; explicitly attach the selection or current statement when needed, and stop an active request.
- Link a workspace per connection and database scope so the selected agent can search current on-disk code, including uncommitted changes, trace business logic alongside database metadata, and show cited files and line numbers. Query results are not sent; answers based on a previous workspace are excluded after switching or unlinking it. Analysis uses each agent’s native permissions and project configuration, without a uniform sandbox guarantee; code may differ from the deployed database environment.
- Connection settings group basic details, connection fields, safety policies, and advanced options, with password visibility and persistent test results. Marking a network connection as production automatically selects and locks required TLS.
- Save queries, use parameters, and inspect execution history and object definitions.
- Let agents access authorized database capabilities through MCP.
- Confirm dangerous production operations and inspect target-table size before changes.
- Refuse to save connection passwords when encryption fails; key errors do not silently replace the existing key.
- Collapse connection lists. Look up exact Redis keys directly or continue wildcard searches by cursor, with a clear distinction between an unfinished scan and no matches. Type filtering also works with Redis versions before 6.

### 6. To-dos, inbox, and clipboard

Keep personal tasks and reference material nearby.

- **To-dos**: to-do, in-progress, and done states; tags, date ranges, subtasks, images, and attachments. Convert a to-do into an AI task and follow its completion automatically.
- **Inbox**: collect ideas, questions, and material with tags, images, and files.
- **Clipboard**: retain text, code, JSON, and image history with search, categories, favorites, and reusable snippets. On macOS, capture runs only after clipboard changes and skips file references; explicit image pasting and attachments remain available.

### 7. Prompts, skills, and lessons

Reuse effective instructions, tools, and knowledge.

- Group prompts, use variables, pin entries, and preselect skills and MCP tools. Insert prompts from buttons or `/` commands while creating a task or continuing a conversation.
- Search prompt titles, bodies, aliases, and groups alongside group navigation. Click a title to edit; creating within a group retains that group.
- Combine skills and MCP tools for each task. MCP dependencies of selected skills follow into tasks and workflows.
- Reviews can still save solutions, usage scenarios, and lessons. There is no separate knowledge-library entry in the sidebar or feature settings; existing knowledge data remains intact.

### 8. Workflows

Combine agent steps, commands, and human approval into repeatable processes.

- Assign roles, models, skills, and requirements to individual steps.
- Use variables, automatic advancement, approval gates, retries, jumps, and cancellation. Reset any step of a stopped workflow, including its current step, while retaining the task and code. Confirmation opens the target step; click “Start this step” to resume execution.
- Rerun the current paused agent step or one awaiting completion confirmation using its configuration. Retain the task, existing code, and other steps while replacing this step’s output; running steps cannot be started again.
- Attach existing tasks to a workflow.
- Extract a reusable workflow from a successful agent conversation.
- Keep execution history for later review. The workflow entry beside task status shows the current step and count. Open it to inspect steps, inputs, outputs, and run statistics or control execution in a popup that leaves conversation layout unchanged.
- Search text within embedded workflow conversations, see match counts, and navigate between matches.

### 9. Insights and reviews

Assess effectiveness, cost, and opportunities to improve.

- **Insights**: task efficiency, agent and model performance, tool usage, cost, permissions, and runtime health. Each visit opens Agent analysis → Cost and resources, with dates from Monday through today, while retaining workspace, agent, and trend interval preferences.
- Compare spending or tokens with the previous period; drill down by agent, model, workspace, or tag. The high-usage ranking aggregates runs by task within the current filters, with run details and a link to the original task.
- View supported account quotas and reset times. TRAE weekly quota depends on its enterprise service; unavailable data shows an error or an older snapshot.
- Inspect installation size, stored data, memory, and CPU usage per agent. TRAE storage covers CLI data and excludes other IDE data.
- **Reviews**: use time, workspace, and tag filters to generate AI summaries with evidence, achievements, issues, and next steps.
- Export reports or turn their conclusions into prompts, lessons, workflows, or skills.
- Rate individual replies and compare approval rates by model.

### 10. My apps

Keep personal tools inside the workbench.

- Describe a small tool and have AI build it, such as a daily report helper or dashboard.
- Choose Follow Caravel or Independent design when creating or refining an app: use the host theme or custom colors, typography, layout, and controls. Each app saves its preference for the next generation or refinement; existing pages are not restyled immediately.
- Add a website or local webpage as a linked app and open it in a window.
- Apps can fetch data, access selected files, send notifications, or view tasks after requesting the corresponding permissions.
- With AI permission, apps can independently choose installed, enabled agents and their models for questions, structured generation, and streaming, using custom controls or the optional host picker. Omitting the agent follows the global default; unavailable selections require a new choice instead of silently switching agents.
- Authorized desktop apps can run local programs or bundled scripts, read output, send input, and manage ongoing tasks. They can inspect system information, processes, and a selected process's TCP listening ports, with separate permission to request a graceful stop or force termination.
- File and directory access uses separate read and write scopes, supporting listing, creation, moves, permanent deletion, text and binary data, chunked reads, and atomic replacement writes. Local communication is authorized by loopback address and port or Unix Socket path.
- Local permissions can last for the current session or be remembered, and can be revoked individually in app settings. Installation does not grant local access, exported apps do not include these permissions, and web and mobile remote access do not expose these interfaces.
- Program execution has the current user's privileges and is not restricted by file or communication scopes; it is not a process sandbox. Closing, refreshing, or revoking execution permission cleans up directly launched session processes, excluding descendants. Generic graceful stops and Unix Socket access are unsupported on Windows.
- Card, compact, and list views show actual generation, refinement, confirmation, interruption, and ready-to-install states; uninstalled drafts no longer remain marked as generating.
- Private storage and database access require authorization. Cross-database file access, query duration, concurrency, and result size are limited. Network redirects across origins require a new authorized request; oversized responses are truncated.
- Improve apps, save versions, and export them to share.

### 11. Separate branches and controlled delivery

Agents can execute independently while you retain control over key permissions and final changes.

- Work in isolated copies to avoid directly changing the original project.
- Inspect branch changes, browse copy files, and safely remove local copies from the workspace. Commit and push through the project Git menu; separate-branch delivery and discard buttons are no longer shown in the task header.
- Clean up completed, safe copies from the Copy Library while keeping tasks and remote branches available for continuation.
- Review changes across repositories in multi-project tasks, then commit and push individually or together. Partial push failures retain successful results; uncommitted or unpushed work still needs review.
- Unlinking a project stops its participation in future runs but preserves its copy and results. Deleting a separate-branch task also keeps its copies; newer copies can start a new task and conversation through Continue Development.
- Before cleaning up a project copy, check uncommitted files and remote commit state and keep recovery information. Resume at the original path. If the remote result branch was deleted, show that explicitly; after cleanup, a new branch can be created from the mainline.
- Legacy separate-branch tasks retain their directories and linking behavior. Create a new task for multi-project isolation. New separate-project tasks cannot fork into a shared writable copy.
- Confirm sensitive actions with one-time or persistent permissions.
- Review changes before merging; request further work or discard the result when necessary.

### 12. Settings

Manage preferences and the execution environment.

- **Agents**: General settings bring together the default agent, permissions, run modes, automatic titles, and idle timeout; agent details manage enablement, models, and transport. Browsing settings does not change the default agent. Save or discard model edits together, retaining unsaved changes across settings scopes. CLI model discovery marks configured models absent from the current catalog as undetected, which does not mean they are unavailable; keep them or remove them in bulk and save. Codex reads the full model catalog, display names, and supported reasoning efforts from the local CLI. Settings and task controls prioritize detected effort levels. Failed or empty discovery reports an error without marking existing models as missing.
- **Claude transport**: stable CLI and experimental ACP remain available and use the native local `claude` command. The `reclaude` launch option has been removed, and previous launch-command preferences no longer apply.
- **Codex transport**: App Server is the default; saved CLI/ACP choices remain. Changes affect subsequent runs. App Server supports resume, fork, approval cards, input forms, and mid-run instructions. Asynchronous questions let the agent keep working and remain available after the turn ends; answers continue with the original permissions. Forms stay until the driver confirms submission, prevent duplicate submissions, and remain available for retry after failure. Standard mode allows workspace writes with on-request approval, while plan mode is read-only. CLI has no live approvals or mid-run instructions, uses read-only standard/plan modes, and offers forks when supported by the installed version. Fast applies only to ACP.
- **TRAE**: requires CLI 2.0 and an Enterprise Flagship account. Discover account models and reasoning efforts; use tasks, workflows, schedules, and AI assistance. Images, additional directories, forks, and mid-run instructions depend on CLI capabilities.
- **Installation and tools**: see counts of ready, upgradable, and uninstalled tools, with items requiring installation, updates, error handling, or installer completion shown first. Versions and installation sources appear together. Install or upgrade agents and supporting tools such as Git, Node, and cc-switch. Upgrades retain the detected installation source and verify runnable versions. Installation stages include clearly labeled estimated percentages, which do not represent download progress or remaining time. Batch progress reflects processed items; progress, queues, and installer guidance remain visible across menu changes. Graphical installers require completion and a refresh; batch upgrades distinguish completed, manual, and failed results. On macOS, Homebrew installs and upgrades of CC Switch first cache the matching package from its official mirror and verify its SHA-256; unavailable mirrors fall back to Homebrew downloads.
- **Plugins**: manage Claude, Codex, OpenCode, and TRAE plugins and select them for tasks. Check stable updates for plugins with independent GitHub repositories against each agent’s installed version and open their release pages. Expand unchecked items to see the plugin, agent, and reason; unchecked does not mean up to date. Installed files are not overwritten automatically.
- **Terminal**: choose the default terminal for opening shells or taking over agent sessions.
- **macOS main window**: content extends to the top while retaining native window buttons. Drag page title bars or empty areas of the workbench filter bar and sidebar to move the window; double-click to toggle maximization. Native background and appearance follow the app theme.
- **Appearance and language**: themes, including the dark Night voyage and light Dawn voyage palettes, task animations, and zoom at 80%, 90%, 100%, 110%, 125%, or 150% (100% by default). Choose Simplified Chinese, English, or system language. Desktop windows synchronize; browser and mobile clients store their own preference. The desktop app retains Chinese when unset. User content, code, and history stay in their original language.
- **Language coverage**: workbench, Git, editor, databases, workflows, schedules, personal tools, insights, reviews, tray, fixed tool-window titles, notifications, and Feishu remote-control text. Built-in AI assistance defaults to the interface language and respects an explicitly requested language.
- **Error recovery**: page, rendering, and startup failures offer retry or reload. The main window can return home; tool windows recover their current page. Action errors keep the interface visible, with technical reasons and stack traces written to the service log instead of a global error notice. Rust panics save a local report that is silently archived on the next launch; forced termination and native WebView crashes are outside this coverage. Save unsaved input before reloading.
- **Feature management**: show, hide, and reorder sidebar entries. Insights is enabled by default; Copy Library is disabled by default.
- **Skills**: inspect skills, declared versions, and MCP tools for different agents. Manually check recorded official Feishu versions and GitHub skill-directory changes. Unmanaged skills, unknown sources, pinned references, and other unchecked items are counted separately with expandable names and reasons; unchecked does not mean up to date. Local files are not overwritten automatically. TRAE supports global skills and native stdio/HTTP MCP configuration; task-level SSE uses a proxy.
- **Remote control**: configure Feishu, intelligent conversations, and message history.
- **Browser access**: independently enable the full web client and read-only mobile client. Disabling one leaves the other available; enabled access modes are restored after restart.
- **Updates**: macOS and Windows x64 support signed in-app updates with download and installation progress. Windows checks its own delivered-version manifest and exits into NSIS for installation; macOS supports system proxies and restarts after updating. Manual and startup updates share progress across navigation. Failures offer a browser download link.
- **Development instance**: run the development and installed apps side by side, each with its own single instance, application data, and service ports. DEV icons and window/tray labels distinguish them. Agent logins, tool configuration, and explicitly selected working directories remain shared.
- **Maintenance**: updates, runtime environment, and service logs.
- **Copy Library**: a separate sidebar entry, disabled by default and configurable in feature management. Lists copies still on disk, grouped by task by default or optionally by project, with workspace names and task tags. Search, rescan, open the owning task, or safely clean up copies. Recovery metadata stays in tasks; directories without recovery metadata are not cleaned up automatically.

### 13. Feishu remote collaboration

Follow tasks and handle key decisions away from your computer, without configuring a public server address.

- View task status and agent progress.
- Create tasks and continue conversations.
- Handle permission requests and code acceptance.
- Receive key status notifications.

## Typical workflow

1. Install the agents you need in Settings, select a project, describe a goal, and choose an agent.
2. Follow multiple runs from the workbench.
3. Respond when permissions or decisions need your attention.
4. Review completed changes and choose to merge, continue, or discard them.
5. Save useful prompts, lessons, and workflows.
6. Schedule recurring work by describing the time and action, then confirming the form.
7. Improve future collaboration through reviews and cost insights.
8. Generate a personal tool or add a useful website in My apps.

## Who it is for

Developers using several coding agents, engineers working across projects, users who want autonomous execution with code control, people running recurring checks and fixes, heavy users building reusable AI methods, and technical leads tracking efficiency, cost, and delivery quality. It also brings reminders, scripts, databases, and small personal tools into the same workspace.

## Product principles

**Local-first**: the app manages tasks, conversations, workspaces, and personal knowledge on your machine. You choose whether to enable remote capabilities such as Feishu.

**Agent choice**: choose tools according to model strengths, task type, and personal preference. Install and upgrade them in Settings and manage them through one product interface.

**You decide; agents execute**: retain goal-setting, permission decisions, code review, and final acceptance while agents handle repetitive execution.

[Download Caravel](https://github.com/yy36295238/caravel-releases/releases/latest) · [Website](https://caravel-site.pages.dev/?lang=en) · [Try the demo](https://caravel-site.pages.dev/demo/?lang=en)
