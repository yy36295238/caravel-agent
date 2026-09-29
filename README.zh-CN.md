<div align="center">

[English](README.md) · **简体中文**

<a href="https://caravel-site.pages.dev/?lang=zh-CN"><img src="https://caravel-site.pages.dev/assets/og-zh-CN.png?v=2" width="100%" alt="Caravel"></a>

# Caravel

### 你掌舵，Agent 并行。

本地优先的多 AI 编码 Agent 工作台，把项目、任务、会话和代码验收放在一起。

**Claude Code · Codex · OpenCode · pi · Grok · TRAE**

<p>
  <a href="https://caravel-site.pages.dev/?lang=zh-CN"><strong>访问官网 ↗</strong></a>
  &nbsp; · &nbsp;
  <a href="https://caravel-site.pages.dev/demo/?lang=zh-CN"><strong>在线体验</strong></a>
  &nbsp; · &nbsp;
  <a href="https://caravel-site.pages.dev/?lang=zh-CN#film"><strong>观看短片</strong></a>
  &nbsp; · &nbsp;
  <a href="https://github.com/yy36295238/caravel-releases/releases/latest"><strong>下载 Caravel</strong></a>
</p>

[![Latest Release](https://img.shields.io/github/v/release/yy36295238/caravel-releases?display_name=tag&style=flat-square&label=release&color=416fae)](https://github.com/yy36295238/caravel-releases/releases/latest)

macOS（Apple Silicon / Intel）与 Windows x64 · 使用你自己的 Agent 和模型账号<br>TRAE 需要 CLI 2.0 与企业版旗舰版账号。

[![Caravel 工作台：全部任务、Agent 会话与代码验收](https://caravel-site.pages.dev/assets/workbench-zh-CN.png?v=ad7f5950761d)](https://caravel-site.pages.dev/?lang=zh-CN)

**点击截图，访问官网并体验完整工作台。**<br>
<sub>演示使用产品原版界面与示例数据，无需安装。</sub>

</div>

## 从目标，到交付

- **并行派发**：给不同项目创建任务，选择 Agent，让多项工作同时推进。
- **集中跟进**：查看执行状态，接续会话，在需要时确认权限或调整方向。
- **审查交付**：查看代码 Diff，继续修改，或在验收后合并、推送独立分支。

我的应用、定时器、工作流和更多功能，前往 [官网查看](https://caravel-site.pages.dev/?lang=zh-CN#possibilities) 或 [在线操作体验](https://caravel-site.pages.dev/demo/?lang=zh-CN)。

## 开始使用

1. [下载安装包](https://github.com/yy36295238/caravel-releases/releases/latest)：macOS 打开 `.dmg`，将 **Caravel** 拖入「应用程序」；Windows x64 下载并运行 `Caravel_*_x64-setup.exe`。
2. 准备 Git 和至少一个已安装、完成登录或配置的受支持 Agent CLI。
3. 添加本地项目，创建任务，选择 Agent 并开始运行。

macOS 与 Windows 均提供包含全部功能模块的 Caravel 通用版。macOS 与 Windows x64 支持应用内签名更新；旧 Windows 客户端需先手动安装支持自动更新的版本。Windows 安装前准备 Git for Windows、Node.js 和 Agent CLI。Windows 安装包尚未使用 Authenticode 签名，如遇 SmartScreen 提示，确认来自本仓库 Releases 后，点击「更多信息 → 仍要运行」。任务与会话保存在本机；Agent 调用在线模型或使用外部集成时仍会联网。

<details>
<summary><strong>首次打开被 macOS 阻止？查看「仍要打开」和终端放行命令</strong></summary>

当前公开版本尚未使用 Apple Developer ID 签名和公证。确认安装包来自本仓库 Releases，并将 Caravel 放入「应用程序」后，可选择以下任一方式打开。

**方式一：在系统设置中允许打开**

1. 先尝试打开一次 Caravel，让 macOS 显示阻止提示。
2. 打开「系统设置 → 隐私与安全性」，向下找到 Caravel 被阻止的说明，点击「仍要打开」。
3. 按提示输入 Mac 登录密码或使用 Touch ID，再点击「打开」。部分系统版本的按钮文案为「仍然打开」。

**方式二：终端放行命令**

打开 Mac 的「终端」，执行以下命令，再重新打开 Caravel：

```sh
xattr -dr com.apple.quarantine /Applications/Caravel.app
```

此命令仅移除 Caravel 的下载隔离属性。其他安装问题见 [官网安装帮助](https://caravel-site.pages.dev/?lang=zh-CN#install-help)。

</details>

---

本仓库提供 **macOS / Windows 安装包与版本记录**。产品介绍、交互演示与常见问题请以 [官网](https://caravel-site.pages.dev/?lang=zh-CN) 为主。

[版本记录](https://github.com/yy36295238/caravel-releases/releases) · [完整功能说明](docs/product-overview.md) · [常见问题](https://caravel-site.pages.dev/?lang=zh-CN#faq)
