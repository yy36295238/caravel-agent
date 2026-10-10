<div align="center">

**English** · [简体中文](README.zh-CN.md)

<a href="https://caravel-site.pages.dev/?lang=en"><img src="https://caravel-site.pages.dev/assets/og-en.png?v=2" width="100%" alt="Caravel"></a>

# Caravel

### You steer. Agents work in parallel.

A local-first workspace for multiple AI coding agents. Projects, tasks, conversations, and code reviews in one place.

**Claude Code · Codex · OpenCode · pi · Grok · TRAE · Antigravity**

<p>
  <a href="https://caravel-site.pages.dev/?lang=en"><strong>Visit website ↗</strong></a>
  &nbsp; · &nbsp;
  <a href="https://caravel-site.pages.dev/demo/?lang=en"><strong>Try the demo</strong></a>
  &nbsp; · &nbsp;
  <a href="https://caravel-site.pages.dev/zh-CN/docs/"><strong>User guide</strong></a>
  &nbsp; · &nbsp;
  <a href="https://caravel-site.pages.dev/?lang=en#film"><strong>Watch the film</strong></a>
  &nbsp; · &nbsp;
  <a href="https://github.com/yy36295238/caravel-releases/releases/latest"><strong>Download Caravel</strong></a>
</p>

[![Latest Release](https://img.shields.io/github/v/release/yy36295238/caravel-releases?display_name=tag&style=flat-square&label=release&color=416fae)](https://github.com/yy36295238/caravel-releases/releases/latest)

macOS (Apple Silicon / Intel) and Windows x64 · Use your own agent and model accounts<br>TRAE requires CLI 2.0 and an Enterprise Flagship account.

[![Caravel workbench: tasks, agent conversations, and code review](https://caravel-site.pages.dev/assets/workbench-en.png?v=20589f435134)](https://caravel-site.pages.dev/?lang=en)

**Click the screenshot to explore the full workbench on the website.**<br>
<sub>The demo uses the actual product interface and sample data. No installation required.</sub>

</div>

## From goal to delivery

- **Delegate in parallel**: create tasks across projects, choose agents, and move several pieces of work forward together.
- **Follow up in one place**: track execution, continue conversations, grant permissions, and adjust direction when needed.
- **Review and deliver**: inspect code diffs, request changes, then merge or push separate branches after review.

Explore apps, schedules, workflows, and more on the [website](https://caravel-site.pages.dev/?lang=en#possibilities), or [try them in the demo](https://caravel-site.pages.dev/demo/?lang=en).

## Get started

1. [Download the installer](https://github.com/yy36295238/caravel-releases/releases/latest). On macOS, open the `.dmg` and drag **Caravel** into Applications. On Windows x64, download and run `Caravel_*_x64-setup.exe`.
2. Prepare Git and at least one supported agent CLI, installed and signed in or configured.
3. Add a local project, create a task, choose an agent, and start the run.

Both platforms provide the complete Caravel app with all feature modules. macOS and Windows x64 support signed in-app updates. Older Windows clients need a manual upgrade to a version with automatic update support. Windows requires Git for Windows, Node.js, and an agent CLI. The Windows installer is not yet Authenticode-signed: if SmartScreen appears, verify that it came from this repository’s Releases, then choose “More info → Run anyway”. Tasks and conversations stay on your machine; online model calls and external integrations still use the network.

<details>
<summary><strong>First launch blocked on macOS? Use Open Anyway or Terminal</strong></summary>

The public macOS app is not yet signed with an Apple Developer ID or notarized. Verify that the installer came from this repository’s Releases and move Caravel into Applications, then use either option below.

**Option 1: Allow the app in System Settings**

1. Try opening Caravel once to trigger the macOS warning.
2. Open “System Settings → Privacy & Security”, find the notice about Caravel, and click “Open Anyway”.
3. Enter your Mac login password or use Touch ID, then click “Open”. Button wording may vary by macOS version.

**Option 2: Use Terminal**

Open Terminal on your Mac, run this command, and reopen Caravel:

```sh
xattr -dr com.apple.quarantine /Applications/Caravel.app
```

This command only removes Caravel’s download quarantine attribute. See the [installation help](https://caravel-site.pages.dev/?lang=en#install-help) for more details.

</details>

## Free use and license

Caravel installers are provided under the [Apache License 2.0](LICENSE), free for personal and commercial use. Modification and redistribution are permitted under its terms; retain the required license and attribution notices and identify changes when redistributing modified files.

The application source code remains private and is not provided, so Caravel is not presented as open-source software. Third-party components retain their own licenses. Agent subscriptions, model APIs, and other external services may charge separately.

---

This repository provides **macOS / Windows installers and release history**. Visit the [website](https://caravel-site.pages.dev/?lang=en) for product information, the interactive demo, and FAQs.

[Releases](https://github.com/yy36295238/caravel-releases/releases) · [Feature guide](docs/product-overview.en.md) · [FAQ](https://caravel-site.pages.dev/?lang=en#faq)
