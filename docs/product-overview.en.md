# Caravel product and feature guide

**English** · [简体中文](product-overview.md)

## Product positioning

**Caravel is a local-first workspace for multiple AI coding agents, built for developers working across projects and tasks. It supports macOS (Apple Silicon / Intel) and Windows x64.**

Both platforms provide the complete app with all feature modules and retain existing application data. macOS and Windows x64 support signed in-app updates; older Windows clients require a manual upgrade to a version that supports automatic updates. Choose your platform on the [download page](https://github.com/yy36295238/caravel-releases/releases/latest). See the [installation help](https://caravel-site.pages.dev/?lang=en#install-help) for first-launch instructions.

Caravel brings Claude Code, Codex, OpenCode, pi, Grok, TRAE, Antigravity, and other coding agents into one desktop workbench. Delegate tasks, track progress, handle permissions, review code, and deliver changes in one place. Install or upgrade agents from Settings.

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

- Manage Claude Code, Codex, OpenCode, pi, Grok, TRAE, and Antigravity together. Invocation controls combine a brand icon, agent dropdown, and model selection; Settings retains full enablement controls.
- Desktop tasks, split views, previews, and Sessions can open a compact always-on-top task window for reading, sending messages, and stopping the current run. It reuses the original conversation; closing it or pressing Esc only hides the window. On macOS it can follow full-screen Spaces, and ⌘⇧J toggles the bound window. This entry is unavailable on the web.
- Conversations, permissions, plans, subagent progress, code diffs, and delivery share one page. Drag the plan card within its conversation area, adjust it with arrow keys, or press Home to reset it. Subagents appear under their tool activity or live tool preview, with expandable status and execution details; records without a visible parent tool remain in a collapsed entry at the end of the conversation.
- Play each completed assistant reply continuously at a speed adapted to its length. Reasoning and tool activity remain live while waiting for the full reply. History, synchronized records, and web polling snapshots appear in full; returning to the window shows finalized text immediately.
- Image links in completed desktop replies become thumbnails that open enlarged previews. Switch chat SVG images between preview and read-only source, with text selection and copying.
- Local video links and recognized inline-code paths in completed desktop replies show video thumbnails. Click to play from the beginning inside the message, with seeking, volume, and fullscreen controls. Videos do not autoplay and stop when leaving the conversation; unsupported files can open externally. Open the video’s containing folder directly, or hover over its name to see the full path.
- Closed Mermaid code blocks in desktop and mobile chats and workflow output support diagram/text switching and zoom. Feishu conversation snapshots also render diagrams; unfinished code blocks retain their source.
- Choose a model and reasoning effort for a new task, a continuation, or a conversation fork. Defaults follow model settings. Manage models in Agent settings; historical tasks retain their existing model selection. Task headers show the latest known reasoning effort; continuations retain it without overwriting manual choices. Expand a run command to view that run’s agent, model, and reasoning effort. Historical commands retain their own configuration; missing values appear as “—”.
- Scrolling toward the top loads earlier messages while preserving your reading position, including task quick previews and mobile task details. Desktop conversations offer a scroll-to-bottom button to return to the latest message and resume following.
- Task turn counts and active time cover the full conversation, independently of message pagination. Active time excludes idle waits for input between turns.
- The task header keeps context utilization, reported tokens across all runs, reported cost when available, active time, and turns visible. Running turns contribute to cumulative values when they finish. When a subscription quota snapshot is available, its primary window appears first; the usage card brings together all account quota windows, reset times, and manual refresh, clearly identifying quota as shared across tasks. Click the summary to open the card and click again to close it; hovering or focusing does not open it. Inspect context usage, cumulative and latest-run tokens, input with and without cache, output, reasoning, cache reads/writes and hit rates, and reported costs. Inspect model requests, recorded tool calls/failures, compactions, and usage by agent/model. The overview emphasizes context usage and remaining capacity, total tokens, reported cost, and cache hit rate, with latest-run values. A token breakdown separates cache reads, cache writes, uncached input, and output. The execution tab shows observed generation speeds, task output rates, first-response and first-text times; the footer summarizes active time, turns, and runs. Missing precise generation timings do not hide rates supported by output counts and elapsed run time. Generation timing covers complete Claude CLI and Pi Anthropic Messages streaming responses, excluding time before first output, tool execution, and waits between requests; network and buffering still affect it. Task output rates include total run duration. Coverage counts are shown, and missing timings remain unknown. Supported interactive transports refresh native usage every five seconds and when opening statistics. OpenCode includes completed-request costs, context usage, and confirmed model windows. Recoverable historical usage can be filled without guessing missing values. Cache writes distinguish unreported values from reported zero, and Codex historical statistics recheck native records.
- The statistics card includes a Task info tab for task/session IDs, copying, session sync, opening the copy directory, and viewing the base branch. Session Hub omits this tab.
- The main desktop window provides a sidebar advisor backed by an independent regular task. Its width can be resized and remembered, and it can expand to fill the app window; Esc exits this expanded view first. It reuses attachments, agent/model/reasoning selection, skills/MCP/plugins, permission requests and input forms, subject to the selected agent and transport. Its conversation and permissions are separate, and it is hidden from regular task lists. Original-task messages are read on demand only when the user allows it. File operations follow the advisor’s own permissions; both tasks share the code directory. Work survives switching tasks or closing the originating window, and legacy advisor history remains available. Replies can be edited and explicitly forwarded using the original task’s own permissions. Floating task windows, web and mobile do not expose the advisor entry. Model usage is recorded separately; the task header and usage card default to combined tokens, cost, turns, and active time for the main task and current advisor, with separate views available. Context windows are not added together; the combined view keeps the main task context. Clearing advisor history removes its deleted usage from the total. Saved advisor messages refresh the original task’s recent activity time and list order. Activity indicators in the workbench list and board, session list, task library, detail entry and advisor panel distinguish analysis from requests for approval or input. They remain visible on the source task when the panel is collapsed and disappear when activity ends, without changing the original task’s status, filters or counts. Hover text explains the state, and reduced-motion settings use a static icon.
- Workspace group headers show counts of running tasks, tasks awaiting input, and unread completed tasks within the current filters and loaded results, including pinned and collapsed groups. Opening a task clears its unread indicator. Ordinary task creation excludes the dedicated Sessions workspace from primary, linked, and slash-menu workspace choices.
- When no task name is supplied, the first line of the trimmed goal becomes the title; the full goal is retained. Automatic task titles are optional under Settings → Agent → General and default to off for both new and existing users. When enabled, the selected agent and model summarize long goals for new tasks without blocking execution; desktop, web, and mobile details show generation status. Turning it off keeps the original name and discards pending summaries. Existing tasks, manual AI generation, full goals, and manual names are preserved.
- Link several workspaces to a task and manage directly or indirectly related tasks from More actions → Related tasks. Before creating a task, use the linked-workspace dialog to switch branches, commit, pull, and push in the primary and linked repositories; these operations affect the original workspace directories.
- Task workspaces register primary and auxiliary projects in one panel: the main workspace, auxiliary workspaces, and attached Git repository roots (including worktrees) share the same task project list. Attached directories belong only to that task, never join the global workspace list, retain the current branch and uncommitted changes, and are never deleted by task cleanup. Original directories keep their current branch and existing changes without requiring a remote baseline; isolated copies can each choose a remote main/master baseline and a development branch. Creating, adding later, and reconnecting use the same entry and preserve the registered mode.
- Existing tasks can quick-create isolated branch copies for Git projects in the project panel; the development branch defaults to the primary project's branch and stays editable, starting from the latest remote main/master, with a prompt to pick another name when the branch already exists remotely. Adding or unlinking during a run takes effect next run; unlinking requires confirmation and preserves the directory and its work. The panel shows pending changes and supports pausing, reconnecting, and continuing.
- Both primary and auxiliary original directories can move to isolated copies while preserving the development branch, unpushed commits, and staged, unstaged, and untracked changes. Changes move out of the original directory, the task uses the copy next run, and the original can optionally switch back to main/master; failed migrations restore the original directory and keep recovery backups when restoration fails. Moving the primary directory starts a new agent session next run while task history is retained. Migration is refused while the task is running, for existing copies, directories used by active tasks, or repositories with submodule changes.
- Enter a separate branch name manually or generate it with the selected agent and model using the task, Jira ID, and specified skill rules. The same request generates a short task title for task creation and the copy directory. Edits made during generation are preserved; missing information can be supplied or names entered manually. The branch is created only after submission.
- AI titles focus on the core action and subject. New separate-branch task and project directory names use only ASCII letters, digits, and `-_.`, falling back to `workspace` when empty and appending IDs to distinguish names. The task-name portion is limited to 20 characters; existing paths and full task goals remain available.
- Projects added during a run join the next run, or you can pause, attach, and continue. Multi-project execution requires agent or adapter support for additional working directories.
- Hand off an idle task to a new conversation: the current agent writes a handoff document, then Caravel creates and starts a linked task. Choose the next focus, agent, model, and reasoning effort. Original-directory, separate-branch, temporary isolated-merge, and legacy tasks alike transfer the same task workspace with all primary and auxiliary projects, preserving directories, branches, and uncommitted changes. The new task starts a fresh conversation from the handoff document with the latest permissions and is linked to the original, which keeps its history read-only and can no longer continue.
- Press `↑` in an empty chat input to restore the previous valid user prompt as an editable draft without sending it or restoring old attachments, quotes, or capability settings. Shared desktop chat inputs and mobile hardware keyboards support this.
- Copy chat tables as Markdown, export CSV, or expand them for reading. Historical and streaming replies, team messages, and mobile chat share these tools. CSV preserves non-ASCII text and treats formula-like content as text.
- A local absolute path alone on a line, with no whitespace, becomes a file link. Desktop clicks retain existing file authorization and preview checks; code blocks and paths embedded in prose are unchanged.
- Copy conversation messages as text or images.
- Quote user or agent message text on desktop, the full web interface, and mobile. Expand the full quote, cancel it, or choose another without replacing the question you have typed. Sending includes the full original text snapshot, excluding separate attachments; translated views quote the original. Quotes work with continued conversations, supported mid-run instructions, and desktop forks. Failed sends retain the quote; desktop task drafts preserve it independently in each pane.
- Free-text and custom answers in agent question forms accept selected, pasted, or dropped images and files, up to 10 attachments per answer, including attachment-only answers. Files belong to their question; submission waits for uploads, and failures retain answers and attachments. Synchronous forms provide file paths in the answer; Codex App Server asynchronous questions also send native images and show attachments in the answer record. Format-constrained and choice-only fields do not offer attachments.
- Manually translate completed assistant replies in shared conversation panels on desktop and the full web interface, then switch between the original and translation in place. Text/image copying and search within loaded messages follow the displayed text, while switching preserves your reading position. Translations are saved locally for reuse after restarts or history sync and remain readable offline; failed regeneration preserves the previous result, and saving can be retried without generating again.
- In Settings → Appearance → Language, choose a translation language independently of the interface: Simplified Chinese (default), Traditional Chinese, English, Japanese, Korean, French, German, or Spanish. Use the message’s model or another installed and enabled agent/model. Generation uses that model’s quota without continuing the original session or adding task turns; code snippets and link targets are preserved, with a 48 KB source limit. Thinking, tools, user messages, attachments, standalone task-library previews, and mobile pages do not offer translation.
- Mark mistakenly sent user messages as deleted on desktop and the full web interface using the delete icon and confirmation dialog; canceling submits nothing. Keep struck-through text and submit one correction asking the agent to ignore the message and attachments and await further input. Stop running tasks first. Marks survive history sync and appear in the mobile conversation; native history and completed actions are not undone.
- Startup and periodic checks reconcile running tasks and pending confirmations whose processes have exited. Explicitly interrupted tasks show “Interrupted” and retain a continuation action without restarting automatically. Conversation messages show completion, failure, and interruption results from reconciliation. Codex/TRAE runs without current-turn records or a clear final state are marked as failed.
- Repeated continuation requests replace the previous run and its pending questions, waiting for its process to exit before restoring the conversation. Requests for one task are handled in arrival order; different tasks can still run in parallel.
- Claude ACP automatically prepares a smaller preview for images whose Base64 encoding exceeds 4 MB, for initial messages, continuations, and supported mid-run input. Originals remain intact, with their paths supplied for detail inspection under existing permissions. Preparation failures reject that send; compressed animated previews retain only the first frame, and existing oversized history is not rewritten.
- Manage linked files and URLs from More actions → Linked resources. Tasks with linked resources also show a count shortcut in the header.
- Copy files from Finder or File Explorer and paste them as attachments when creating tasks or continuing conversations, preserving filenames and removing duplicate paths. Workflows, to-dos, and inbox notes share the same attachment support. Desktop context menus paste text, images, and files into the active input area without sending attachments to another pane or dialog.
- Stop a task at any time or take over in a terminal. Stopping reclaims processes for all unfinished runs of that task and reports an error if a process cannot exit.

#### Collaboration teams within a task (experimental)

Enable team selection and save teams in Settings → Agent → Team (experimental), then select one when creating a desktop task. Selection is off by default and the switch saves immediately. Disabling preserves teams and existing tasks while ignoring saved team choices in new-task drafts. Up to 20 teams can each contain up to 8 members, with names, roles, notes, agents, models, reasoning effort, permissions, avatars, and up to 20 skills available to the selected agent. Switching agents retains skills that remain available. The lead specifies required skills per assignment, including their MCP dependencies. Choose a pixel cabin or modern office theme. Tasks retain their original team snapshot when a team is edited or deleted; members are selected by default and can be individually deselected or reselected without changing the template. Drafts preserve the selection. Choosing no team, an empty team, or no members keeps ordinary task behavior. Workbench lists, boards, and the task library identify team tasks with a badge.

- The lead handles communication, planning, coordination, and independent review, saving goals, owners, and acceptance criteria before assigning work. Initial assignments and revisions include the original goal and undeleted user inputs, including skills, references, and attachment paths. Lead suggestions are labeled separately. Members choose solutions within their scope; the lead coordinates shared boundaries. Plans and acceptance prioritize user scenarios and actual results before engineering evidence. Workers share the task’s directory and execute one at a time, without additional branches or copies. Scope instructions and warnings do not provide filesystem isolation.
- View a themed scene or call list beside the conversation, resize columns by dragging or keyboard, collapse the panel, or use stacked columns in narrow windows. Assignments, member progress replies, and final reports appear chronologically, with filters for the lead or individual members. Member history is independent of lead-conversation pagination, and final replies are not duplicated. Speaker labels show the agent, model, and reasoning effort used for that run, preserving unknown values. Member details retain team avatars, names, and roles. Cumulative member time includes all calls and waits within them, excluding gaps; individual records retain per-call time. Inspect current intent, member status, changed files, scope warnings, and available check records; open a member’s conversation to answer questions, handle permissions, or provide guidance.
- Caravel monitors workers after the lead ends its coordination turn and resumes the lead when results or exceptions need attention. Ordinary progress does not wake the model. Five minutes without a written report shows a notice; ten minutes without observable activity queues an exception. Reasoning and streamed tool output count as activity. Handle approvals and input in the member conversation; silence does not imply a timeout. Users can continue chatting without stopping workers. Team tasks stay running while waiting, without showing lead typing or increasing its active time. Stopping the team cancels pending notifications and stops workers. Restarting does not rerun workers; managed results remain pending. Revisions can reuse the same member session, with a 30-minute call limit and at most 30 calls per task.
- A worker returning or a conversation ending is not overall delivery. The lead must accept all plan items and submit a report with verification evidence. Plans and assignments define verification responsibilities. The lead inspects actual outputs and original evidence, spot-checking key results and high-risk connections. Valid evidence covering the current output can be reused; revisions require checks of the changes and their impact, while explicitly required checks still run. Reports distinguish reused evidence from personally performed checks; the report also collects up to 50 existing files or directories from members and the lead. Deliverables are grouped by author and can be opened or located in their folder. All workers must finish before delivery is confirmed. Users may also confirm after execution ends, without implicitly committing or merging code. Continuing the conversation, assigning more work, or adding requirements requires renewed acceptance.
- Successful continuations in the same session append only changed member settings and new events. New or forked sessions, failure recovery, app restarts, and context compaction restore full collaboration rules; ACP restores them when a missing session falls back to a new one.
- Switch statistics between the team total, lead, and individual workers to inspect token shares, usage, caching, duration, and turns. The team total does not imply a single shared context window.
- Team selection and the collaboration panel currently target desktop tasks. Sessions, web, mobile, Feishu, workflows, and schedules do not offer team selection. Read-only planning cannot write to the collaboration mailbox; progress reports and execution depend on each agent’s output and permissions, and collaboration instructions do not replace a sandbox.

#### Sessions

Enable Sessions in Settings → Features; it is off by default. Start a conversation without first choosing a project. Sessions share a fixed workspace directory and appear separately from regular tasks in Workbench and Tasks. Turning off the entry preserves history.

- Sending the first message creates a session. Choose an agent, model, reasoning effort, permissions, attachments, skills, and task references, with a separate draft for new sessions.
- Search by keyword, date, and tags, showing today by default. Pin, favorite, tag, open historical links, or delete with confirmation.
- Follow streaming conversations, handle permissions, stop and continue runs, and view usage, cost, duration, and turns. Resize the list or switch between list and conversation in narrow windows.

### 2. Task library

Keep and find historical tasks in one place.

- Filter by status, agent, workspace, date, and related tasks. Workspace filtering includes linked projects with saved development-branch records.
- Search development-branch fragments or requirement IDs in Workbench and Tasks, with matching workspaces, branches, and historical markers. Keep the query while clearing other filters or looking for archived tasks. Saved branch history survives copy cleanup; older tasks without branch records may not match.
- Search, favorite, archive, and group tasks. Open regular, archived, and branch-linked tasks in a detail dialog on the current page while preserving filters, pagination, and list position. Close it with the close button, backdrop, or Esc.
- Search sidebar workspaces by name or path. Matching groups expand temporarily; clearing the search restores their previous state.
- Import and synchronize existing agent sessions, including native and officially migrated TRAE CLI 2.0 sessions. Codex supports both older and newer session formats. Rebuilding preserves image attachments and reply ratings; incomplete parsing or failed writes retain the original conversation while reconciling run status separately. Manual sync reports incomplete conversation updates; historical runs do not overwrite the current task status.
- Open workspaces and manage Git branches, commits, pushes, and conflicts. Remove separate-branch entries even when their local copy is missing. Cleaned projects with missing directories are hidden while tasks and recovery information remain available.
- Branch menus and diff headers summarize added, modified, and deleted files. Diffs retain total file and line-change counts; filtering files does not change the summary.
- Diffs default to full-file context when no preference is saved, and remember subsequent compact or full-file choices.
- Commit only selected files while preserving unselected staged changes and tracked-file deletions. Task headers show the branch and changed-file count.
- Pulling remote updates shows progress and keeps Git output, file and line-change statistics, up-to-date messages, or failure details visible until dismissed. Detected merge operations with conflicts can open the conflict resolver.
- Choose a model and generate a commit message directly in the commit dialog, edit the draft, then commit or commit and push. Generated summaries use a type prefix by default and prioritize explicit formatting instructions. Additional instructions stay available when collapsed; search and reuse the latest 20 entries shared across repositories on this machine, or delete individual entries without changing the current input.

- Diffs with a repository path can open the file’s containing directory or a directory from the tree in the system file manager, falling back to an existing parent when the path was deleted.

### 3. Schedules

Automate work that runs daily, weekly, at intervals, or just once.

- Describe the time and task in natural language; review the parsed form before creating the schedule.
- Alternatively, enter the name, instructions, and recurrence manually.
- New-schedule drafts automatically retain the description, form, agent, model, skills, and MCP selections locally. Closing and reopening restores the draft; successful creation clears it, while editing an existing schedule leaves it untouched.
- Run daily, weekly, every few minutes or hours, or once.
- Set multiple times for daily or weekly schedules, such as 09:30 and 20:30.
- Restrict interval schedules to selected weekdays and working hours.
- Choose local reminders, local scripts, or agent execution. Reminders do not call an agent. Agents can generate and trial a script once, then run it on schedule without repeated model calls; shell and PowerShell are supported.
- Search and select skills and MCP services for scheduled agent tasks. Scheduled, immediate, and catch-up runs include those choices and MCP services associated with the selected skills.
- Agent tasks, local scripts, and script trials without a selected workspace use an automatically created, reusable schedule workspace rather than the first project you added. An unavailable explicitly selected workspace requires reselection; reminders need no workspace.
- Optionally catch up on runs missed while the computer was unavailable.
- Run a schedule immediately to inspect its behavior.
- Review run history and output, with optional notification cards. Open the full task in a dialog from the schedule list or run details without leaving the page, including failed tasks with no output.
- Pause, edit, or delete schedules; use list or card views and see the next run time.

### 4. Editor

Browse, search, and edit project files.

- Multiple tabs, syntax highlighting, and autosave.
- The desktop editor previews MP4, MOV, WebM, MKV, and AVI videos by reading local files on demand. Playback depends on system codec support, with an external-app fallback; web and mobile clients retain file information.
- Markdown (including embedded SVG images), Mermaid, and image previews; open pasted file or directory paths. Markdown in the editor and file quick preview supports local images referenced relative to the document directory, by absolute path, or by file URL, up to 20 MiB per image.
- SVG file quick previews show the image by default and can switch to read-only source; line references open source first.
- Inspect, locate, and revert changes relative to the last commit, including image comparisons in diffs.
- Copy full paths, open complete diffs, and use common Git actions from file previews. Collapse directories in the diff file tree.
- Open the current directory in an installed external editor and remember that preference. Supported locations include the main workspace, linked directories, and isolated copies.

- HTML file quick previews render the webpage by default and can switch to read-only source; line references open source first. Inline styles, scripts, and data resources work in isolation. Desktop previews also load CSS, JavaScript, images, fonts, and media from the current directory and subdirectories, up to 20 MiB per resource. Switching or closing the preview revokes access. Host permissions remain isolated; resources outside the directory, remote resources, and API requests are blocked. Browser previews support inline resources only.

### 5. Databases

Connect to MySQL, PostgreSQL, SQLite, MongoDB, or Redis to query and edit data.

- Browse objects, filter and page through data, open local SQLite files, query MongoDB documents, and manage Redis keys.
- Opening tables or views by double-click, the data context-menu action, or the command palette inserts a SELECT with `WHERE 1=1` for adding filters; it does not execute the query automatically.
- MySQL connections without a selected database automatically select the only visible non-system database before becoming ready and expand it in the object tree. Reconnection restores that scope; existing selections remain intact, and multiple visible databases require explicit selection. Watched databases limit display and automatic selection without changing account permissions.
- Write SQL or document queries, inspect and edit results, and export complete results, including SQL output. For editable results, cell and row-detail value dialogs let you edit raw text, set NULL, and stage changes for confirmation and submission in the results panel.
- Resize result columns by dragging or keyboard; hidden columns and horizontal scrolling retain correct field positions. Searching fetched results highlights matching cells, with match indicators retained inside selections.
- Generate, explain, optimize, and repair queries with a conversational SQL Copilot. Editor SQL is excluded from ordinary questions by default; explicitly attach the selection or current statement when needed, and stop an active request. Requests continue in the background when switching features or databases or closing the panel within the same window. Return to the original scope to see progress and results or stop the request. Each scope prevents duplicate submissions while running; different scopes run independently. Background execution lasts only while the application window remains open.
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
- Search prompt titles, bodies, aliases, and groups alongside group navigation. Click a title to edit; creating within a group retains that group. Rename a whole group from group navigation or list view, including the default group; empty and duplicate names are rejected.
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

- **Insights**: task efficiency, agent and model performance, tool usage, cost, permissions, and runtime health. Each visit opens Agent analysis → Cost and resources, with dates from Monday through today, while retaining workspace, agent, and trend interval preferences. Single-day trends use local hours. Cost trends include all 24 hours and compare matching clock hours on the previous day; cumulative usage is attributed to the run start hour, not measured within each hour.
- Compare spending or tokens with the previous period; drill down by agent, model, workspace, or tag. The high-usage ranking aggregates runs by task within the current filters, with run details and a link to the original task. Team details separate the lead task and each subtask, showing member identities, token shares, reported costs, current task states, and runs within the same filters. Multiple subtasks assigned to one member remain separate. Statistics include hidden tasks and team-member runs, retaining historical usage and agent filters after an agent is uninstalled. Member runs are grouped under the main task and counted once, preserving the actual agent and model while using the main task’s workspace and tags. Member tool calls are included, and completed tasks are deduplicated after grouping.
- Claude CLI and ACP recover per-run cost from local session records and fill delayed historical costs on later turns. These are Claude’s price-based estimates, not subscription bills; missing records preserve unknown or existing values.
- View supported account quotas and reset times. TRAE weekly quota depends on its enterprise service; unavailable data shows an error or an older snapshot.
- Inspect installation size, stored data, memory, and CPU usage per agent. TRAE storage covers CLI data and excludes other IDE data.
- **Reviews**: use time, workspace, and tag filters to generate AI summaries with evidence, achievements, issues, and next steps. Each agent call for batch analysis or the final summary can take up to 10 minutes and remains manually stoppable.
- Export reports or turn their conclusions into prompts, lessons, workflows, or skills.
- Rate individual replies and compare approval rates by model.

### 10. My apps

Keep personal tools inside the workbench.

- Describe a small tool and have AI build it, such as a daily report helper or dashboard.
- Choose Follow Caravel or Independent design when creating or refining an app: use the host theme or custom colors, typography, layout, and controls. Each app saves its preference for the next generation or refinement; existing pages are not restyled immediately.
- Add a website or local webpage as a linked app and open it in a window.
- Apps can fetch data, access selected files, send notifications, or view tasks after requesting the corresponding permissions.
- With AI permission, apps can independently choose installed, enabled agents and their models for questions, structured generation, and streaming, using custom controls or the optional host picker. Omitting the agent follows the global default; unavailable selections require a new choice instead of silently switching agents.
- Authorized desktop apps can run local programs or bundled scripts, read output, send input, and manage ongoing tasks. They can inspect system information, processes, and a selected process's TCP listening ports, with separate permission to request a graceful stop or force termination. Grant access to the current process instance once, or remember the selected permission for all processes the current user can control, including future instances. Revoke it in app settings; existing instance grants are not expanded automatically.
- File and directory access uses separate read and write scopes, supporting listing, creation, moves, permanent deletion, text and binary data, chunked reads, and atomic replacement writes. Local communication is authorized by loopback address and port or Unix Socket path.
- Local permissions can last for the current session or be remembered, and can be revoked individually in app settings. Installation does not grant local access, exported apps do not include these permissions, and web and mobile remote access do not expose these interfaces.
- Program execution has the current user's privileges and is not restricted by file or communication scopes; it is not a process sandbox. Closing, refreshing, or revoking execution permission cleans up directly launched session processes, excluding descendants. Generic graceful stops and Unix Socket access are unsupported on Windows.
- Card, compact, and list views show actual generation, refinement, confirmation, interruption, and ready-to-install states; uninstalled drafts no longer remain marked as generating.
- Installed apps that can be opened may be pinned as quick apps. Pins stay on this computer in the order they were added and are not included in shared packages. The desktop sidebar opens a quick panel that launches an app in its own window, or returns to a window already open, without leaving the current workbench.
- Private storage and database access require authorization. Cross-database file access, query duration, concurrency, and result size are limited. Network redirects across origins require a new authorized request; oversized responses are truncated.
- Improve apps, save versions, and export them to share.

### 11. Separate branches and controlled delivery

Agents can execute independently while you retain control over key permissions and final changes.

- Work in isolated copies to avoid directly changing the original project.
- Inspect branch changes, browse copy files, and safely remove local copies from the workspace. Commit and push through the project Git menu; separate-branch delivery and discard buttons are no longer shown in the task header.
- Clean up completed, safe copies from the Copy Library while keeping tasks and remote branches available for continuation.
- Review changes across repositories in multi-project tasks, then commit and push managed copies individually or together. Original workspaces use manual file selection through Git tools and are excluded from automatic task commits and copy cleanup. Partial push failures retain successful results; uncommitted or unpushed work still needs review.
- Unlinking a project stops its participation in future runs but preserves its copy and results. Deleting a separate-branch task also keeps its copies; newer copies can start a new task and conversation through Continue Development.
- Before cleaning up a project copy, check uncommitted files and remote commit state and keep recovery information. Resume at the original path. If the remote result branch was deleted, show that explicitly; after cleanup, a new branch can be created from the mainline.
- Legacy separate-branch tasks retain their directories and linking behavior. Create a new task for multi-project isolation. New separate-project tasks cannot fork into a shared writable copy.
- Confirm sensitive actions with one-time or persistent permissions.
- Review changes before merging; request further work or discard the result when necessary.

### 12. Settings

Manage preferences and the execution environment.

- **Agents**: General settings bring together the default agent, permissions, run modes, automatic titles, and idle timeout; agent details manage enablement, models, and transport. Browsing settings does not change the default agent. Search models by name or ID and manage whitelists and blacklists, with enabled entries shown first. Blacklisting disables a model; restoring it requires manual enablement. Discovery retains list preferences, and task and app model pickers exclude blacklisted entries. Save or discard model edits together, retaining unsaved changes across settings scopes. CLI model discovery marks configured models absent from the current catalog as undetected, which does not mean they are unavailable; keep them or remove them in bulk and save. Codex reads the full model catalog, display names, and supported reasoning efforts from the local CLI. Settings and task controls prioritize detected effort levels. Failed or empty discovery reports an error without marking existing models as missing.
- **Claude transport**: stable CLI and experimental ACP remain available and use the native local `claude` command. The `reclaude` launch option has been removed, and previous launch-command preferences no longer apply.
- **Pi**: model discovery combines the local catalog with custom providers, models, and metadata overrides, respecting a custom configuration directory. Read failures report errors instead of marking models missing from incomplete results. Manage native stdio/Streamable HTTP MCP services and database MCP with a supported newer CLI; subsequent sessions load the configuration. Disabling retains definitions and native options, damaged configuration is not overwritten, and legacy SSE is unsupported.
- **Codex transport**: App Server is the default; saved CLI/ACP choices remain. Changes affect subsequent runs. App Server supports resume, fork, approval cards, input forms, and mid-run instructions. Asynchronous questions let the agent keep working and remain available after the turn ends; answers continue with the original permissions. Forms stay until the driver confirms submission, prevent duplicate submissions, and remain available for retry after failure. Standard mode allows workspace writes with on-request approval, while plan mode is read-only. CLI has no live approvals or mid-run instructions, uses read-only standard/plan modes, and offers forks when supported by the installed version. Fast applies only to ACP.
- **Antigravity**: install or upgrade the official CLI and automatically prepare the ACP connector on first use. Reuse local account or API configuration; select models, approval/auto-edit/full-access modes, resume sessions, and cancel runs. Import and synchronize local ACP history, keeping sessions without a final marker ready to resume. ACP Plan, forks, mid-run input, additional directories, and terminal takeover are unavailable. Skills and MCP use official shared configuration, including database MCP. CLI plugins can be toggled but are not loaded by ACP tasks. SQL code analysis uses native CLI Plan. Availability depends on the account region, model quota, and sign-in status.
- **TRAE**: requires CLI 2.0 and an Enterprise Flagship account. Discover account models and reasoning efforts; use tasks, workflows, schedules, and AI assistance. Images, additional directories, forks, and mid-run instructions depend on CLI capabilities.
- **Installation and tools**: see counts of ready, upgradable, and uninstalled tools, with items requiring installation, updates, error handling, or installer completion shown first. Versions and installation sources appear together. Install or upgrade agents and supporting tools such as Git, Node, and cc-switch. Upgrades retain the detected installation source and verify runnable versions. Installation stages include clearly labeled estimated percentages, which do not represent download progress or remaining time. Batch progress reflects processed items; progress, queues, and installer guidance remain visible across menu changes. Graphical installers require completion and a refresh; batch upgrades distinguish completed, manual, and failed results. On macOS, Homebrew installs and upgrades of CC Switch first cache the matching package from its official mirror and verify its SHA-256; unavailable mirrors fall back to Homebrew downloads.
- **Plugins**: manage Claude, Codex, OpenCode, TRAE, and Antigravity CLI plugins, with per-agent and all-agent toggles. An independent index retains discovered installations when disabled or when CLI listing fails, and removes entries after uninstall is confirmed. Remote plugins omitted by some older Codex CLI versions remain manageable. Enabled plugins can be selected for tasks, except Antigravity ACP tasks. Check stable updates for plugins with independent GitHub repositories against each agent’s installed version and open their release pages. Expand unchecked items to see the plugin, agent, and reason; unchecked does not mean up to date. Installed files are not overwritten automatically.
- **Codex configuration guard**: records discovered plugins and Caravel-managed MCP bindings and restores them when external tools wipe whole configuration sections. Individual intentional removals are respected. The plugin panel can disable automatic recovery, show recent recovery activity, or manually restore unrecorded plugins from existing marketplace caches.
- **Terminal**: choose the default terminal for opening shells or taking over agent sessions.
- **macOS main window**: content extends to the top while retaining native window buttons. Drag page title bars or empty areas of the workbench filter bar and sidebar to move the window; double-click to toggle maximization. Native background and appearance follow the app theme.
- **Appearance and language**: themes, including the dark Night voyage and light Dawn voyage palettes, task animations, and zoom at 80%, 90%, 100%, 110%, 125%, or 150% (100% by default). Mobile follows the computer’s current theme by default and can choose its own. Choose Simplified Chinese, English, or system language. Desktop windows synchronize; browser and mobile clients store their own language preference. The desktop app retains Chinese when unset. User content, code, and history stay in their original language.
- **Language coverage**: workbench, Git, editor, databases, workflows, schedules, personal tools, insights, reviews, tray, fixed tool-window titles, notifications, and Feishu remote-control text. Built-in AI assistance defaults to the interface language and respects an explicitly requested language.
- **Error recovery**: page, rendering, and startup failures offer retry or reload. The main window can return home; tool windows recover their current page. Action errors keep the interface visible, with technical reasons and stack traces written to the service log instead of a global error notice. Rust panics save a local report that is silently archived on the next launch; forced termination and native WebView crashes are outside this coverage. Save unsaved input before reloading.
- **Feature management**: show, hide, and reorder sidebar entries. Insights is enabled by default; Copy Library is disabled by default.
- **Skills**: inspect skills, declared versions, and MCP tools for different agents. Manually check recorded official Feishu versions and GitHub skill-directory changes. Unmanaged skills, unknown sources, pinned references, and other unchecked items are counted separately with expandable names and reasons; unchecked does not mean up to date. Local files are not overwritten automatically. TRAE supports global skills and native stdio/HTTP MCP configuration; task-level SSE uses a proxy.
- **Discover and install skills**: browse a dated popular-skills snapshot, search public GitHub repositories, or enter a repository URL. Preview the full instructions, source, file count, and size before installing to the library or enabling installed agents. Downloads use a fixed commit and include the complete skill directory; replacement requires confirmation, backs up existing files, rolls back failures, and retains agent links. Saved sources support later update checks. Private repositories, non-GitHub sources, symlinks, submodules, and Git LFS are unsupported; limits are 4 MiB per file and 32 MiB / 400 files per skill.
- **Skills and MCP overview**: browse a directory alongside item details, return to the directory in narrow windows, and inspect per-agent counts, unmanaged items, and update results. Skills load independently of MCP scans. MCP details show environment-variable and header names without exposing credential values.
- **Remote control**: configure Feishu, intelligent conversations, and message history.
- **Browser access**: independently enable the full web client and the mobile client. Mobile task actions require a separate switch on the computer and stay off by default, leaving the phone read-only. Disabling one client leaves the other available; enabled access modes are restored after restart. Mobile access uses HTTP on the local network and is intended only for trusted networks. If a link is exposed, turn off task actions or rotate the link.
- **Updates**: macOS and Windows x64 support signed in-app updates with download and installation progress. Windows checks its own delivered-version manifest and exits into NSIS for installation; macOS supports system proxies and restarts after updating. Software update has its own settings category. Automatic checks run at startup and in the background once at least an hour has passed since the last check. Dismissing a version notice suppresses further notices for that version until the app restarts. Optional silent downloads verify the package before notifying you; the previous automatic-install preference now enables downloads only. Manual checks download new versions directly and show progress in Settings. Once ready, clicking Install and restart runs the update without a second confirmation dialog. Background notices also provide download, progress, and installation controls in place. Installation and restart still require an explicit click. Manual and background updates share checks and download progress across navigation. Background failures are logged quietly; manual failures offer retry and download links. Downloaded packages remain available only until the app exits. Installation uses the confirmed version, and a failed restart can be retried without reinstalling. Update checks and downloads try the domestic domain, domestic IP, GitHub, and Cloudflare in order. Network failures fall back to the same version and signature. The domestic mirror stores delivered packages independently; Cloudflare still relays GitHub. The domestic domain requires completed registration and valid HTTPS; the IP remains available while it is not ready. Signature or installation failures stop immediately. Manual download fallback uses the domestic IP. Older clients need to install a version with domestic-source support first.
- **Development instance**: run the development and installed apps side by side, each with its own single instance, application data, and service ports. DEV icons and window/tray labels distinguish them. Agent logins, tool configuration, and explicitly selected working directories remain shared.
- **Installation statistics**: Release builds send random installation and event IDs, version, OS/architecture, and startup/update event times to Caravel’s own servers for installation and activity statistics. This excludes conversations, code, paths, accounts, and hardware identifiers. Statistics run independently of automatic-update settings; development builds do not report. Counts represent application data directories, not exact people or devices. Events are queued locally and sent in the background; download completion and installation requests are distinct from successfully running the new version.
- **Maintenance**: runtime environment and service logs.
- **Copy Library**: a separate sidebar entry, disabled by default and configurable in feature management. Lists copies still on disk in “Safe to clean” and “Keep” sections, showing tasks with their last-updated date (hover for the full time), tags, workspaces, directories, branches, and retention reasons. Search by keyword, filter by workspace and tag, rescan, open the owning task, or inspect files and changes. “Clean all” covers all safe copies, regardless of filters, and requires confirmation. Recovery metadata stays in tasks; directories without recovery metadata are not cleaned up automatically.

### 13. Feishu remote collaboration

Follow tasks and handle key decisions away from your computer, without configuring a public server address.

- View task status and agent progress.
- Create tasks and continue conversations.
- Handle permission requests and code acceptance.
- Receive key status notifications.

### 14. Mobile collaboration

Use a phone browser on the same local network to follow Caravel on your computer. Viewing is available after pairing; task actions stay off until you enable them.

- Enable mobile access separately in Settings and pair with a QR code or link. Disconnect this device from the phone’s Me page.
- See run summaries, items that need you, workspaces, and conversations. The task list defaults to today, with options for the past 7 days or all time. Thinking and tool steps collapse into a one-line summary, with changes and task details on separate pages.
- Image attachments in user messages appear as thumbnails and open in a fullscreen preview. Only images recorded in that task’s messages can be read, up to 20 MB each; other attachments show their filenames.
- After turning on “Allow mobile task actions” on the computer, answer permission prompts, send messages and images, stop, continue, accept or discard isolated-copy changes, and create, rename, archive, or delete tasks.
- When creating a task, choose a model, reasoning effort, and permissions; attach images and tags; select configured skills, MCP servers, and plugins; link workspaces; and reference up to five existing tasks. Idle conversations can also change settings and capabilities for the next turn.
- After enabling the corresponding run modes on the computer, create isolated-copy or separate-branch tasks from the phone. Choose a base for isolated copies; separate branches start from main or master, support AI-generated branch names and task titles, and can be committed and pushed during review.
- Answer agent forms directly on the phone, including single and multiple choices, text, numbers, booleans, and custom answers. Open link requests and continue; mobile forms do not offer local-file attachments.
- The information page shows run mode, branch and base, linked workspaces, run counts, tokens, context usage, and cost. Supported Claude, Codex, Grok, and TRAE accounts show quota windows, warnings, and reset times; manual refresh requires mobile task actions to be enabled.
- Copy message text, inspect the agent’s task plan, and distinguish new messages. New replies appear progressively, following updates at the bottom while preserving your position when reading earlier messages. Long conversations load in pages with incremental refresh; thinking and tool output are trimmed by size while message bodies remain complete.
- The phone follows the computer’s theme by default. Access uses HTTP and should stay on a trusted network.

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
