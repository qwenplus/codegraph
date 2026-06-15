<div align="center">

# CodeGraph

## 🎉 1.0 已发布！

已安装？运行 `codegraph upgrade` 即可原地更新。

在 X 上关注 [@getcodegraph](https://x.com/getcodegraph) 获取更新。

### 为 Claude Code、Cursor、Codex、OpenCode、Hermes Agent、Gemini、Antigravity 和 Kiro 赋能语义代码智能

**~16% 更便宜 · ~58% 更少工具调用 · 100% 本地运行**

### [文档与网站 →](https://colbymchenry.github.io/codegraph/)

[![npm version](https://img.shields.io/npm/v/@colbymchenry/codegraph.svg)](https://www.npmjs.com/package/@colbymchenry/codegraph)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![自包含](https://img.shields.io/badge/Node.js-已捆绑·无需安装-brightgreen.svg)](https://nodejs.org/)

[![Windows](https://img.shields.io/badge/Windows-支持-blue.svg)](#支持的平台)
[![macOS](https://img.shields.io/badge/macOS-支持-blue.svg)](#支持的平台)
[![Linux](https://img.shields.io/badge/Linux-支持-blue.svg)](#支持的平台)

[![Claude Code](https://img.shields.io/badge/Claude_Code-支持-blueviolet.svg)](#支持的-agent)
[![Cursor](https://img.shields.io/badge/Cursor-支持-blueviolet.svg)](#支持的-agent)
[![Codex](https://img.shields.io/badge/Codex-支持-blueviolet.svg)](#支持的-agent)
[![opencode](https://img.shields.io/badge/opencode-支持-blueviolet.svg)](#支持的-agent)
[![Hermes Agent](https://img.shields.io/badge/Hermes_Agent-支持-blueviolet.svg)](#支持的-agent)
[![Gemini](https://img.shields.io/badge/Gemini-支持-blueviolet.svg)](#支持的-agent)
[![Antigravity](https://img.shields.io/badge/Antigravity-支持-blueviolet.svg)](#支持的-agent)
[![Kiro](https://img.shields.io/badge/Kiro-支持-blueviolet.svg)](#支持的-agent)

<br>

**CodeGraph 平台即将推出** —— 对于每个 PR，精确了解需要测试什么、可能破坏什么、哪些流程受影响以及业务逻辑是否受损。

<a href="https://getcodegraph.com"><img alt="加入等待名单获取早期测试资格" src="https://raw.githubusercontent.com/colbymchenry/codegraph/main/assets/waitlist.svg?v=2" height="52"></a>

<sub>获取<b>早期测试资格</b>访问托管产品 · <a href="https://getcodegraph.com">getcodegraph.com</a></sub>

</div>

## 快速开始

### 1. 安装 CLI

**无需 Node.js** —— 一条命令即可获取适合您操作系统的正确构建版本：

```bash
# macOS / Linux
curl -fsSL https://raw.githubusercontent.com/colbymchenry/codegraph/main/install.sh | sh

# Windows (PowerShell)
irm https://raw.githubusercontent.com/colbymchenry/codegraph/main/install.ps1 | iex
```

<details>
<summary><b>已有 Node？使用 npm 安装（适用于任何版本）</b></summary>

```bash
npm i -g @colbymchenry/codegraph
```

<sub>CodeGraph 捆绑了自己的运行时 —— 无需编译，无原生构建，到处运行一致。安装程序将 `codegraph` 放到您的 PATH 上，但**不会更改当前 shell** —— 在下一步之前打开新终端以便命令生效。</sub>

<sub>**随时升级** 使用 `codegraph upgrade` —— 它检测您的安装方式（捆绑包、npm 或 npx）并原地更新。添加 `--check` 查看是否有可用更新，或使用 `codegraph upgrade <version>` 固定特定版本。</sub>

</details>

### 2. 连接您的 agent(s)

在**新终端**中，运行安装程序以将 CodeGraph 连接到您使用的 agent：

```bash
codegraph install
```

<sub>检测并自动配置 Claude Code、Cursor、Codex CLI、opencode、Hermes Agent、Gemini CLI、Antigravity IDE 和 Kiro —— 将 CodeGraph MCP 服务器接入每一个。**这是将 CodeGraph 连接到您的 agent 的步骤；** 仅在第 1 步安装 CLI 本身不会完成连接。（快捷方式：`npx @colbymchenry/codegraph` 一步下载并运行此步骤。）</sub>

### 3. 初始化每个项目

```bash
cd your-project
codegraph init
```

<sub>`codegraph init` 在同一操作中创建本地 `.codegraph/` 目录并构建完整图谱 —— 一条命令，完成。</sub>

<div align="center">

![1_C_VYnhpys0UHrOuOgpgoyw](https://github.com/user-attachments/assets/f168182f-4d9a-44e0-94d7-08d018cc8a3a)

</div>

### 4. 不再需要同步！

自动同步默认启用。CodeGraph 监控项目并在每次文件更改时更新图谱 —— 当您的 agent 编辑代码，或您添加、修改、删除文件时。**索引永不过时，也无需重新运行任何内容。**

### 卸载

改变主意了？一条命令从每个配置的 agent 中移除 CodeGraph：

```bash
codegraph uninstall
```

<sub>反向安装程序 —— 从每个配置的 agent 中剥离 CodeGraph 的 MCP 服务器配置、指令和权限。您的项目索引（`.codegraph/`）保持不变；每个项目使用 `codegraph uninit` 移除。使用 `--target` 从特定 agent 移除，或使用 `--yes` 非交互式运行。</sub>

---

## 为什么选择 CodeGraph？

当 Claude Code 探索代码库时，它会生成**Explore agent**，使用 grep、glob 和 Read 扫描文件 —— 每次工具调用都消耗 token。

**CodeGraph 为这些 agent 提供预索引的知识图谱** —— 符号关系、调用图和代码结构。Agent 可以即时查询图谱而不是扫描文件。

### 基准测试结果

在**7 个真实开源代码库**（跨 7 种语言）上测试，比较 agent（Claude Code，无头模式）**有**和**没有** CodeGraph 回答一个架构问题。每个单元格是**每组 4 次运行的中位数**的节省。_在 Opus 4.8 (2026-06-02) 上重新验证，使用当前构建（`codegraph_explore` 作为主要工具）。_

> **平均：16% 更便宜 · 47% 更少 token · 22% 更快 · 58% 更少工具调用**

| 代码库 | 语言 | 成本 | Token | 时间 | 工具调用 |
|----------|----------|------|--------|------|------------|
| **VS Code** | TypeScript · ~10k 文件 | 18% 更便宜 | 64% 更少 | 11% 更快 | 81% 更少 |
| **Excalidraw** | TypeScript · ~640 | 持平 | 25% 更少 | 27% 更快 | 40% 更少 |
| **Django** | Python · ~3k | 8% 更便宜 | 60% 更少 | 13% 更快 | 77% 更少 |
| **Tokio** | Rust · ~790 | 持平 | 38% 更少 | 18% 更快 | 57% 更少 |
| **OkHttp** | Java · ~645 | 25% 更便宜 | 54% 更少 | 31% 更快 | 50% 更少 |
| **Gin** | Go · ~110 | 19% 更便宜 | 23% 更少 | 24% 更快 | 44% 更少 |
| **Alamofire** | Swift · ~110 | 40% 更便宜 | 64% 更少 | 33% 更快 | 58% 更少 |

CodeGraph 在**每个仓库上都减少了 token、工具调用和挂钟时间** —— 跨越小、中、大型代码库 —— 并且以**接近零的文件读取**回答问题，而没有 CodeGraph 的 agent 则将其预算花费在 grep/find/Read 发现上。`codegraph_explore` 完整展示答案 —— 机制以及您询问的确切方法，即使它们埋在数千行的文件中 —— 同时折叠冗余的可互换实现为签名，因此响应大小适合*答案*而非文件数量。**成本在各处保持持平到更便宜** —— 在小仓库（Alamofire、OkHttp）上最大，在响应最重的仓库（Excalidraw、Tokio）上大致持平，CodeGraph 用少数大型、缓存密集的工具响应换取无 CodeGraph agent 的许多小型 grep/read 往返。

<details>
<summary><strong>每个仓库的细分 —— 有 vs 无（4 次中位数）</strong></summary>

**VS Code** · ~10k 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 59s | 2m 13s | 11% 更快 |
| 文件读取 | 0 | 9 | −9 |
| Grep/Bash | 0 | 11 | −11 |
| 工具调用 | 4 | 21 | 81% 更少 |
| 总 token | 640k | 1.79M | 64% 更少 |
| 成本 | $0.68 | $0.83 | 18% 更便宜 |

**Excalidraw** · ~640 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 32s | 2m 6s | 27% 更快 |
| 文件读取 | 0 | 7 | −7 |
| Grep/Bash | 1 | 8 | −7 |
| 工具调用 | 9 | 15 | 40% 更少 |
| 总 token | 1.27M | 1.69M | 25% 更少 |
| 成本 | $0.78 | $0.78 | 持平 |

**Django** · ~3k 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 43s | 1m 58s | 13% 更快 |
| 文件读取 | 0 | 9 | −9 |
| Grep/Bash | 0 | 5 | −5 |
| 工具调用 | 3 | 13 | 77% 更少 |
| 总 token | 559k | 1.41M | 60% 更少 |
| 成本 | $0.57 | $0.62 | 8% 更便宜 |

**Tokio** · ~790 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 55s | 2m 20s | 18% 更快 |
| 文件读取 | 0 | 8 | −8 |
| Grep/Bash | 0 | 6 | −6 |
| 工具调用 | 6 | 14 | 57% 更少 |
| 总 token | 1.08M | 1.73M | 38% 更少 |
| 成本 | $0.82 | $0.82 | 持平 |

**OkHttp** · ~645 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 1s | 1m 29s | 31% 更快 |
| 文件读取 | 0 | 4 | −4 |
| Grep/Bash | 2 | 6 | −4 |
| 工具调用 | 5 | 10 | 50% 更少 |
| 总 token | 502k | 1.10M | 54% 更少 |
| 成本 | $0.41 | $0.55 | 25% 更便宜 |

**Gin** · ~110 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 14s | 1m 37s | 24% 更快 |
| 文件读取 | 1 | 6 | −5 |
| Grep/Bash | 1 | 2 | −1 |
| 工具调用 | 5 | 9 | 44% 更少 |
| 总 token | 651k | 847k | 23% 更少 |
| 成本 | $0.46 | $0.57 | 19% 更便宜 |

**Alamofire** · ~110 文件
| 指标 | 有 cg | 无 cg | Δ |
|---|---|---|---|
| 时间 | 1m 35s | 2m 21s | 33% 更快 |
| 文件读取 | 0 | 9 | −9 |
| Grep/Bash | 0 | 4 | −4 |
| 工具调用 | 5 | 12 | 58% 更少 |
| 总 token | 766k | 2.10M | 64% 更少 |
| 成本 | $0.57 | $0.95 | 40% 更便宜 |

</details>

<details>
<summary><strong>完整基准测试详情</strong></summary>

**方法论。** 每组是 `claude -p` (Claude Opus 4.8) 在无头模式下针对仓库运行，使用 `--strict-mcp-config`：**有** = 启用 CodeGraph 的 MCP 服务器，**无** = 空的 MCP 配置。内置的 Read/Grep/Bash 对两者都可用。每个仓库相同问题，**每组 4 次运行，报告中位数**。成本 = 运行的 `total_cost_usd`；Token = 总处理 token（输入包括缓存 + 输出）；时间 = 挂钟时间；工具调用 = 每次工具调用，包括任何子 agent 内部的调用。仓库以 `--depth 1` 克隆并由相同的 CodeGraph 构建索引和服务。2026-06-02 在当前构建上重新验证。这些数字低于之前的 Opus 4.7 验证 —— 不是 CodeGraph 退化，而是更强的原生基线：Opus 4.8 在主线程上高效地 grep/read，而不是分散到大型 Explore 子 agent 扫描中，因此无 CodeGraph 组比以前更精简。每个仓库的数字随无 CodeGraph 组的混乱程度而波动（4 次中位数平滑了它，但尾部仍然存在 —— 例如 Django 的无 CodeGraph 组一次运行达到 $2.71/14m）。

**查询：**
| 代码库 | 查询 |
|----------|-------|
| VS Code | "扩展主机如何与主进程通信？" |
| Excalidraw | "Excalidraw 如何渲染和更新画布元素？" |
| Django | "Django 的 ORM 如何从 QuerySet 构建和执行查询？" |
| Tokio | "tokio 如何在其运行时调度和运行异步任务？" |
| OkHttp | "OkHttp 如何通过其拦截器链处理请求？" |
| Gin | "gin 如何通过其中间件链路由请求？" |
| Alamofire | "Alamofire 如何构建、发送和验证请求？" |

**CodeGraph 获胜的原因：** 有了索引可用，agent 直接回答 —— 通常一个 `codegraph_explore` 返回相关源代码 —— 然后停止，通常零文件读取。没有它，agent 在发现（find/ls/grep）上花费大部分预算，然后才读取正确的代码。CodeGraph 仅在*直接查询*时有帮助，因此它的指令引导 agent 直接回答而不是将探索委托给文件读取子 agent —— 否则子 agent 无论如何都会读取文件，CodeGraph 成为开销。

</details>

---

## 核心功能

| | |
|---|---|
| **智能上下文构建** | 一次工具调用返回入口点、相关符号和代码片段 —— 无需昂贵的探索 agent |
| **全文搜索** | 在整个代码库中 instant 按名称查找代码，由 FTS5 驱动 |
| **影响分析** | 追踪调用者、被调用者和任何符号的完整影响范围，然后再进行更改 |
| **始终保持新鲜** | 文件监视器使用本机 OS 事件（FSEvents/inotify/ReadDirectoryChangesW），带有防抖自动同步 —— 图谱随着您编码保持最新，零配置 |
| **20+ 种语言** | TypeScript、JavaScript、Python、Go、Rust、Java、C#、PHP、Ruby、C、C++、Objective-C、Swift、Kotlin、Scala、Dart、Lua、Luau、R、Svelte、Vue、Astro、Liquid、Pascal/Delphi |
| **框架感知路由** | 识别 Web 框架路由文件，并在 17 个框架中将 URL 模式链接到其处理器 |
| **混合 iOS / React Native / Expo** | 闭合静态解析错过的跨语言流程：Swift ↔ ObjC 桥接、React Native 传统桥接 + TurboModules + Fabric 视图组件、native → JS 事件发射器、Expo Modules |
| **100% 本地** | 没有数据离开您的机器。无需 API 密钥。无需外部服务。仅 SQLite 数据库 |

<details>
<summary><strong>自动同步如何工作 —— 以及为什么您不需要手动运行 <code>codegraph sync</code></strong></summary>

当您的 agent（Claude Code、Cursor、Codex、opencode）启动 `codegraph serve --mcp` 时，三层保持索引与代码同步 —— 并确保 agent 在编辑和下次同步之间的短暂窗口中永远不会得到静默的错误答案：

1. **带防抖的文件监视器。** 本机 FSEvents / inotify / ReadDirectoryChangesW 监视器捕获每个源文件创建/修改/删除，并在防抖窗口后触发重新索引（默认 `2000ms`，可通过 `CODEGRAPH_WATCH_DEBOUNCE_MS` 调整，限制在 `[100ms, 60s]`）。批量编辑折叠为单次同步。

2. **每文件过时横幅。** 在短暂的防抖窗口期间，引用仍待处理文件的 MCP 工具响应会在前面加上 `⚠️` 横幅，命名文件并告诉 agent 直接 `Read` 它。未由响应引用的待处理文件改为显示为小页脚。无论哪种方式，agent 都会收到明确信号 —— 已在 Claude Code 上验证，agent 字面上说"直接读取文件获取实时内容"，然后打开它。

3. **连接时追赶。** 当 MCP 服务器（重新）连接时，codegraph 在回答第一个查询之前对工作组进行快速 `(size, mtime)` + 内容哈希协调 —— 因此在没有 MCP 服务器运行时进行的编辑（来自终端的 `git pull`、来自另一个编辑器的编辑、先前退出的 agent 会话）会在下次会话的第一个工具调用时被吸收。

```
agent 写入 src/Widget.ts
  → 监视器触发 (<100ms)
  → 防抖 (默认 2s)
  → 同步; Widget.ts 在索引中
  → 下一个 agent 查询看到它
```

**随时验证** 使用 `codegraph_status`（通过 MCP）或 `codegraph status`（CLI）。如果有待处理的内容，您将看到 `### Pending sync:` 部分命名文件及其编辑时间。

手动 `codegraph sync` 有意义的少数情况：监视器被禁用（沙盒环境，或 `CODEGRAPH_NO_DAEMON=1`），或者您在 agent 会话之外针对索引编写脚本，并希望在脚本开始时进行预检同步。

→ 完整深入探讨在 [指南 → 索引化项目](https://colbymchenry.github.io/codegraph/guides/indexing/#stay-fresh-automatically)。

</details>

---

## 框架感知路由

CodeGraph 检测 Web 框架路由文件并发出 `route` 节点，通过 `references` 边链接到其处理器类或函数。查询视图/控制器的调用者现在会显示绑定它的 URL 模式。

| 框架 | 识别的形状 |
|---|---|
| **Django** | `path()`、`re_path()`、`url()`、`include()` 在 `urls.py` 中（CBV `.as_view()`，虚线路径） |
| **Flask** | `@app.route('/path', methods=[...])`，蓝图路由 |
| **FastAPI** | `@app.get(...)`、`@router.post(...)`，所有标准方法 |
| **Express** | `app.get(...)`、`router.post(...)` 带中间件链 |
| **NestJS** | `@Controller` + `@Get/@Post/...`，GraphQL `@Resolver` + `@Query/@Mutation`，`@MessagePattern`/`@EventPattern`，`@SubscribeMessage` |
| **Laravel** | `Route::get()`、`Route::resource()`、`Controller@action`，元组语法 |
| **Drupal** | `*.routing.yml` 路由（`_controller`、`_form`、实体处理器）；`.module`/`.theme`/`.install`/`.inc` 中的 `hook_*` 实现 |
| **Rails** | `get '/x', to: 'users#index'`，hash-rocket `=>` 语法 |
| **Spring** | `@GetMapping`、`@PostMapping`、`@RequestMapping` 在方法上 |
| **Play** | `GET`/`POST`/… 动词路由在 `conf/routes` → `Controller.method` 动作（Scala + Java） |
| **Gin / chi / gorilla / mux** | `r.GET(...)`、`router.HandleFunc(...)` |
| **Axum / actix / Rocket** | `.route("/x", get(handler))` |
| **ASP.NET** | `[HttpGet("/x")]` 属性在动作方法上 |
| **Vapor** | `app.get("x", use: handler)` |
| **React Router** / **SvelteKit** | 路由组件节点 |
| **Vue Router** / **Nuxt** | `pages/` 基于文件的路由、`server/api/` 端点、路由中间件 |
| **Astro** | `src/pages/` 基于文件的路由（`.astro` 页面 + `.ts` 端点，`[param]`/`[...rest]` 语法） |

---

## 混合 iOS / React Native / Expo 桥接

真实的 iOS 和 React Native 代码库存在于多种语言之间 —— Swift 调用者调用已自动桥接的 Objective-C 选择器，JS 文件通过 React Native 桥接调用原生模块，JSX 组件委托给原生视图管理器。静态 tree-sitter 提取在每个语言边界停止。CodeGraph 桥接它们，使 `trace`、`callers`、`callees` 和 `impact` 端到端跨间隙连接。

| 边界 | JS / Swift 侧 | 原生侧 | 如何 |
|---|---|---|---|
| **Swift → ObjC** | Swift `obj.foo(bar:)` | ObjC 选择器 `-fooWithBar:` | `@objc` 自动桥接规则（包括 init/property/protocol 形式）+ Cocoa 介词前缀（`With`/`For`/`By`/`In`/`On`/`At`/…） |
| **ObjC → Swift** | ObjC `[obj fooWithBar:]` | Swift `@objc func foo(bar:)` | 反向桥接名称候选；从源验证 `@objc` 暴露 |
| **React Native 传统桥接** | JS `NativeModules.X.fn(...)` | ObjC `RCT_EXPORT_METHOD` / `RCT_REMAP_METHOD` · Java/Kotlin `@ReactMethod` | 解析宏/注解声明以构建 JS 名称 → 原生方法映射 |
| **React Native TurboModules** | JS `import M from './NativeM'; M.fn(...)` | 匹配 Codegen 规范的原生实现 | 将 `Native<X>.ts` 规范接口视为基本事实 |
| **RN native → JS 事件** | JS `new NativeEventEmitter(...).addListener('e', cb)` | ObjC `[self sendEventWithName:@"e" body:...]` · Swift `sendEvent(withName: "e", ...)` · Java/Kotlin `.emit("e", ...)` | 合成的跨语言事件通道，以字面事件名称为键 |
| **Expo Modules** | JS `requireNativeModule('X').fn(...)` | Swift / Kotlin `Module { Name("X"); AsyncFunction("fn") { ... } }` | 解析 Expo DSL 字面量；合成方法节点通过现有名称匹配解析 |
| **Fabric 视图组件** | JSX `<MyView prop={v}/>` | TS Codegen 规范 + 原生实现类 | 规范 → `component` 节点；基于约定 + 后缀的名称查找（`View`/`ComponentView`/`Manager`/`ViewManager`）桥接到原生 |
| **传统 Paper 视图管理器** | JSX `<MyView prop={v}/>` | ObjC `RCT_EXPORT_VIEW_PROPERTY` · Java/Kotlin `@ReactProp` | 与 Fabric 相同 —— Paper 时代的声明也产生 `component` + `property` 节点 |

**在真实代码库上验证**（每个桥接的小 + 中 + 大）：

| 桥接 | 小 | 中 | 大 |
|---|---|---|---|
| Swift ↔ ObjC | [Charts](https://github.com/danielgindi/Charts) | [realm-swift](https://github.com/realm/realm-swift) | [Wikipedia-iOS](https://github.com/wikimedia/wikipedia-ios) |
| RN 传统桥接 | [AsyncStorage](https://github.com/react-native-async-storage/async-storage) | [react-native-svg](https://github.com/software-mansion/react-native-svg) | [react-native-firebase](https://github.com/invertase/react-native-firebase) |
| RN native → JS 事件 | [RNGeolocation](https://github.com/Agontuk/react-native-geolocation-service) | — | react-native-firebase |
| Expo Modules | expo-haptics | expo-camera | expo SDK 扫描（7 个包） |
| Fabric / Paper 视图 | [react-native-segmented-control](https://github.com/react-native-segmented-control/segmented-control) | [react-native-screens](https://github.com/software-mansion/react-native-screens) | [react-native-skia](https://github.com/Shopify/react-native-skia) |

每个桥接发出标记为 `provenance:'heuristic'` 的边，`metadata.synthesizedBy:` 设置为稳定的通道名称（例如 `swift-objc-bridge`、`rn-event-channel`、`fabric-native-impl`、`expo-module-extract`），因此 agent 可以一目了然地知道跳变是如何进入图谱的。

---

## 快速入门

### 1. 运行安装程序

```bash
npx @colbymchenry/codegraph
```

安装程序将：
- 询问要配置哪个 agent —— 自动检测已安装的：**Claude Code**、**Cursor**、**Codex CLI**、**opencode**、**Hermes Agent**、**Gemini CLI**、**Antigravity IDE**、**Kiro**
- 提示在您的 PATH 上安装 `codegraph`（以便 agent 可以启动 MCP 服务器）
- 询问配置是应用于所有项目还是仅当前项目
- 写入每个选定 agent 的 MCP 服务器配置，以及在 agent 指令文件（`CLAUDE.md` / `AGENTS.md` / `GEMINI.md`）中添加一个小的标记围栏 CodeGraph 部分 —— 这就是子 agent 和非 MCP agent 了解 `codegraph explore` / `codegraph node` 命令的方式，因为 MCP 服务器自己的指导只到达主 agent。`codegraph uninstall` 干净地移除。
- 当 Claude Code 是目标之一时设置自动允许权限
- 初始化您当前的项目（仅限本地安装）

**非交互式（脚本/CI）：**

```bash
codegraph install --yes                              # 自动检测 agent，全局安装
codegraph install --target=cursor,claude --yes       # 显式目标列表
codegraph install --target=auto --location=local     # 检测到的 agent，项目本地
codegraph install --print-config codex               # 打印片段，不写入文件
```

| 标志 | 值 | 默认 |
|---|---|---|
| `--target` | `auto`、`all`、`none` 或 csv (`claude,cursor,...`) | 提示 |
| `--location` | `global`、`local` | 提示 |
| `--yes` | （布尔值） | 提示每个步骤 |
| `--no-permissions` | （布尔值）跳过 Claude 自动允许列表 | 权限开启 |
| `--print-config <id>` | 转储一个 agent 的片段并退出 | — |

### 2. 重启您的 Agent

重启您的 agent（Claude Code / Cursor / Codex CLI / opencode / Hermes Agent / Gemini CLI / Antigravity IDE / Kiro）以加载 MCP 服务器。

### 3. 初始化项目

```bash
cd your-project
codegraph init
```

构建每个项目的知识图谱索引，然后在每次文件更改时自动同步。单个全局 `codegraph install` 在您打开的每个项目中都有效 —— 无需每个项目重新运行安装程序。

就是这样 —— 当存在 `.codegraph/` 目录时，您的 agent 将自动使用 CodeGraph 工具。

<details>
<summary><strong>手动设置（替代方案）</strong></summary>

**全局安装：**
```bash
npm install -g @colbymchenry/codegraph
```

**添加到 `~/.claude.json`：**
```json
{
  "mcpServers": {
    "codegraph": {
      "type": "stdio",
      "command": "codegraph",
      "args": ["serve", "--mcp"]
    }
  }
}
```

**添加到 `~/.claude/settings.json`（可选，用于自动允许）：**
```json
{
  "permissions": {
    "allow": [
      "mcp__codegraph__codegraph_search",
      "mcp__codegraph__codegraph_explore",
      "mcp__codegraph__codegraph_callers",
      "mcp__codegraph__codegraph_callees",
      "mcp__codegraph__codegraph_impact",
      "mcp__codegraph__codegraph_node",
      "mcp__codegraph__codegraph_status",
      "mcp__codegraph__codegraph_files"
    ]
  }
}
```

</details>

<details>
<summary><strong>Agent 工具指导</strong></summary>

CodeGraph 的 MCP 服务器**自动**在 MCP `initialize` 响应中向您的 agent 提供使用指导。简而言之，它告诉 agent：

- **直接使用 CodeGraph 回答结构性问题** —— 它*是*预构建的索引，因此 grep/read 循环只是重复它已经完成的工作。将返回的源代码视为已读取。
- **按意图选择工具：** `codegraph_explore` 适用于几乎所有事情 —— "X 如何工作"、流程/"X 如何到达 Y"、或调查一个区域（一次调用返回按文件分组的相关符号的源代码）；`codegraph_search` 仅定位符号；`codegraph_callers` 获取每个调用点（包括回调注册）；`codegraph_node` 获取一个符号的完整源代码 + 调用者，或像 Read 工具一样读取文件。
- **信任结果 —— 不要用 grep 重新验证**，并在编辑后检查过时横幅。
- 在没有索引的工作区中，CodeGraph 宣布自己处于非活动状态且不服务任何工具 —— 索引由您决定。

确切文本在 `src/mcp/server-instructions.ts` —— 主 agent 的唯一真实来源。由于子 agent 和非 MCP harness 从未看到 MCP 指导，安装程序还会在 agent 指令文件中写入一个四行标记围栏部分，指向 `codegraph explore` / `codegraph node` CLI 等效项。

</details>

---

## 工作原理

```
┌───────────────────────────────────────────────────────────────────┐
│                            Claude Code                            │
│                                                                   │
│   "请求如何到达数据库？"                                           │
│       直接调用 CodeGraph 工具 —— 无需 Explore 子 agent             │
│                                 │                                 │
└─────────────────────────────────┬─────────────────────────────────┘
                                  │
                                  ▼
┌───────────────────────────────────────────────────────────────────┐
│                        CodeGraph MCP Server                       │
│                                                                   │
│       explore · search · callers · callees · impact · node        │
│                                 │                                 │
│                                 ▼                                 │
│                       SQLite 知识图谱                             │
│          symbols · edges · files · FTS5 全文搜索                  │
└───────────────────────────────────────────────────────────────────┘
```

1. **提取** —— [tree-sitter](https://tree-sitter.github.io/) 将源代码解析为 AST。特定语言的查询提取节点（函数、类、方法）和边（调用、导入、继承、实现）。

2. **存储** —— 所有内容都进入本地 SQLite 数据库（`.codegraph/codegraph.db`），带有 FTS5 全文搜索。

3. **解析** —— 提取后，引用被解析：函数调用 → 定义、导入 → 源文件、类继承和框架特定模式。

4. **自动同步** —— MCP 服务器使用本机 OS 文件事件监控您的项目。更改会被防抖（2 秒安静窗口），过滤为仅源文件，并增量同步。图谱随着您编码保持新鲜 —— 无需配置。

---

## CLI 参考

```bash
codegraph                         # 运行交互式安装程序
codegraph install                 # 运行安装程序（显式）
codegraph uninstall               # 从您的 agent 中移除 CodeGraph（install 的反向）
codegraph init [path]             # 在项目中初始化（--index 也索引）
codegraph uninit [path]           # 从项目中移除 CodeGraph（--force 跳过提示）
codegraph index [path]            # 完整索引（--force 重新索引，--quiet 减少输出）
codegraph sync [path]             # 增量更新
codegraph status [path]           # 显示统计信息
codegraph unlock [path]           # 移除阻止索引的陈旧锁文件
codegraph query <search>          # 搜索符号（--kind、--limit、--json）
codegraph explore <query>         # 相关符号的源代码 + 调用路径一次性获取（与 codegraph_explore MCP 工具输出相同）
codegraph node <symbol|file>      # 一个符号的源代码 + 调用者，或带行号读取文件（与 codegraph_node 输出相同）
codegraph files [path]            # 显示文件结构（--format、--filter、--max-depth、--json）
codegraph callers <symbol>        # 查找调用函数/方法的内容（--limit、--json）
codegraph callees <symbol>        # 查找函数/方法调用的内容（--limit、--json）
codegraph impact <symbol>         # 分析更改符号会影响哪些代码（--depth、--json）
codegraph affected [files...]     # 查找受更改影响的测试文件（见下文）
codegraph daemon                  # 管理后台守护进程 —— 选择一个停止（别名：daemons）
codegraph telemetry [on|off]      # 显示或更改匿名使用遥测
codegraph upgrade [version]       # 更新到最新版本（--check、--force）
codegraph version                 # 打印已安装版本（也是 -v、--version）
codegraph help [command]          # 显示帮助，可选针对一个命令
```

### `codegraph affected`

跟踪导入依赖关系以查找哪些测试文件受更改的源文件影响。

```bash
codegraph affected src/utils.ts src/api.ts         # 将文件作为参数传递
git diff --name-only | codegraph affected --stdin   # 从 git diff 管道输入
codegraph affected src/auth.ts --filter "e2e/*"     # 自定义测试文件模式
```

| 选项 | 描述 | 默认 |
|--------|-------------|---------|
| `--stdin` | 从 stdin 读取文件列表 | `false` |
| `-d, --depth <n>` | 最大依赖遍历深度 | `5` |
| `-f, --filter <glob>` | 自定义 glob 识别测试文件 | 自动检测 |
| `-j, --json` | 输出为 JSON | `false` |
| `-q, --quiet` | 仅输出文件路径 | `false` |

**CI/hook 示例：**

```bash
#!/usr/bin/env bash
AFFECTED=$(git diff --name-only HEAD | codegraph affected --stdin --quiet)
if [ -n "$AFFECTED" ]; then
  npx vitest run $AFFECTED
fi
```

---

## MCP 工具

当作为 MCP 服务器运行时，CodeGraph 公开了一组四个核心工具 —— 测量的 agent 行为表明，更简洁的列表引导 agent 使用正确的工具，并在每次会话中节省上下文：

| 工具 | 目的 |
|------|---------|
| `codegraph_explore` | **主要。** 一次调用回答几乎所有问题 —— "X 如何工作"、流程（"X 如何到达 Y"）、或调查一个区域 —— 返回相关符号的逐字源代码按文件分组，加上关系图和爆炸半径。展示 grep 无法跟随的动态分派跳转（回调、React 重新渲染、接口→实现）。 |
| `codegraph_node` | 一个符号的完整源代码 + 调用者/被调用者轨迹（每个歧义名称的所有重载）—— 或传递文件路径**像 Read 工具一样读取整个文件**（相同的行号输出，`offset`/`limit`），附带其依赖项。 |
| `codegraph_search` | 在整个代码库中按名称查找符号 |
| `codegraph_callers` | 函数的每个调用点 —— 包括注册为回调的地方 —— 当几个共享一个名称时，每个定义一个部分 |

还有四个工具（`codegraph_callees`、`codegraph_impact`、`codegraph_files`、`codegraph_status`）保持完全功能但未列出默认 —— 在评估运行中测量，agent 从不或很少选择它们，并且它们的信息已经在上述四个工具中内联到达（explore 的爆炸半径部分、node 的依赖项说明、符号的主体作为其被调用者列表）。使用 `CODEGRAPH_MCP_TOOLS` 环境变量重新启用其中任何一个（例如 `CODEGRAPH_MCP_TOOLS=explore,node,search,callers,impact`），或使用它们的 CLI 等效项（`codegraph callees` / `impact` / `files` / `status`）。

在没有 `.codegraph/` 索引的工作区中，服务器宣布自己处于非活动状态且**不列出任何**工具 —— agent 使用其内置工具正常工作，索引由您决定。

---

## 库用法

CodeGraph 可以直接嵌入。npm 包重新导出其编程 API，因此 `import` 和 `require` 都在您自己的进程中解析 `CodeGraph` 类 —— 适合嵌入到应用程序中（例如 Electron 主进程）。

```typescript
import CodeGraph from '@colbymchenry/codegraph';
// CommonJS 也可以：
//   const { CodeGraph } = require('@colbymchenry/codegraph');

const cg = await CodeGraph.init('/path/to/project');
// 或：const cg = await CodeGraph.open('/path/to/project');

await cg.indexAll({
  onProgress: (p) => console.log(`${p.phase}: ${p.current}/${p.total}`)
});

const results = cg.searchNodes('UserService');
const callers = cg.getCallers(results[0].node.id);
const context = await cg.buildContext('fix login bug', { maxNodes: 20, includeCode: true, format: 'markdown' });
const impact = cg.getImpactRadius(results[0].node.id, 2);

cg.watch();   // 文件更改时自动同步
cg.unwatch(); // 停止监控
cg.close();
```

更低级的构建块从同一入口点导出，供直接驱动图谱的调用者使用：`DatabaseConnection`、`QueryBuilder`、`getDatabasePath`、`initGrammars` / `loadGrammarsForLanguages` 和 `FileLock`。

**嵌入要求**

- 从 npm 安装（`npm i @colbymchenry/codegraph`），以便匹配的平台包（携带编译的库及其依赖项）与 shim 一起获取。
- API 在**您的**运行时上运行，因此需要**Node 22.5+** 用于内置的 `node:sqlite`（当 Electron 捆绑的 Node 是 22.5+ 时符合条件）。CLI 和 MCP 服务器不受影响 —— 它们在独立的捆绑运行时上运行。
- TypeScript 类型随包一起提供。与任何面向 Node 的库一样，保持 `@types/node` 可用和 `skipLibCheck: true`（常见的默认值）。

---

## 配置

没有任何配置 —— CodeGraph 是零配置的，**没有配置文件**可写或保持同步。语言支持从文件扩展名自动获得；无需为每种语言连接任何内容。

默认情况下排除的内容：

- **依赖、构建和缓存目录** —— `node_modules`、`vendor`、`dist`、`build`、`target`、`.venv`、`Pods`、`.next` 等，跨越每个 [支持的堆栈](#支持的语言) —— 因此图谱是您的代码，而不是第三方噪音。即使没有 `.gitignore` 也是如此。
- **.gitignore 中的任何内容** —— 在 git 仓库中通过 git 遵守，在非 git 项目中通过直接读取 `.gitignore`（根和嵌套）。
- **大于 1 MB 的文件** —— 生成的捆绑包、压缩的 JS、供应的 blob。

要排除其他内容，请将其添加到 `.gitignore`。要将默认排除的目录拉回**来**（比如您真的想要索引某个供应的依赖项），添加否定 —— `!vendor/`。默认设置统一应用，因此提交依赖或构建目录不会强制其进入图谱；`.gitignore` 否定是显式的选择加入。

## 遥测

CodeGraph 收集**匿名使用统计信息** —— 使用哪些工具和命令、索引哪些语言 —— 以指导语言和 agent 支持工作的方向。**绝不**收集任何代码、路径、文件或符号名称、查询或 IP 地址；使用在本地聚合为每日总数后再发送，摄取端点是 [此仓库中的公开代码](telemetry-worker/)，强制执行记录的字段列表。安装程序一开始就会询问；随时关闭：

```bash
codegraph telemetry off    # 或：CODEGRAPH_TELEMETRY=0，或 DO_NOT_TRACK=1
```

[`TELEMETRY.md`](TELEMETRY.md) 列出每个字段，包括关闭开关和完整的数据处理故事。

## 支持的平台

每个版本都为所有三个桌面操作系统提供独立构建（捆绑的 Node 运行时 —— 无需编译），适用于 Intel/AMD (x64) 和 ARM (arm64)：

| 平台 | 架构 | 安装 |
|----------|---------------|---------|
| Windows | x64, arm64 | PowerShell 安装程序或 npm |
| macOS | x64, arm64 | shell 安装程序或 npm |
| Linux | x64, arm64 | shell 安装程序或 npm |

请参阅 [快速开始](#快速开始) 获取单行安装命令。

## 支持的 Agent

交互式安装程序自动检测并配置每一个 —— 连接 MCP 服务器（提供自己的使用指导，因此不写入指令文件）：

- **Claude Code**
- **Cursor**
- **Codex CLI**
- **opencode**
- **Hermes Agent**
- **Gemini CLI**
- **Antigravity IDE**
- **Kiro**

## 支持的语言

| 语言 | 扩展 | 状态 |
|----------|-----------|--------|
| TypeScript | `.ts`, `.tsx` | 完全支持 |
| JavaScript | `.js`, `.jsx`, `.mjs` | 完全支持 |
| Python | `.py` | 完全支持 |
| Go | `.go` | 完全支持 |
| Rust | `.rs` | 完全支持 |
| Java | `.java` | 完全支持 |
| C# | `.cs` | 完全支持 |
| PHP | `.php` | 完全支持 |
| Ruby | `.rb` | 完全支持 |
| C | `.c`, `.h` | 完全支持 |
| C++ | `.cpp`, `.hpp`, `.cc` | 完全支持 |
| Objective-C | `.m`, `.mm`, `.h` | 部分支持（类、协议、方法、`@property`、`#import`、消息发送；`.mm` ObjC++ 可能解析不完整） |
| Swift | `.swift` | 完全支持 |
| Kotlin | `.kt`, `.kts` | 完全支持 |
| Scala | `.scala`, `.sc` | 完全支持（类、特征、方法、类型别名、Scala 3 枚举） |
| Dart | `.dart` | 完全支持 |
| Svelte | `.svelte` | 完全支持（脚本提取、Svelte 5 runes、SvelteKit 路由） |
| Vue | `.vue` | 完全支持（script + script-setup 提取、Nuxt page/API/middleware 路由） |
| Astro | `.astro` | 完全支持（frontmatter + script 提取、模板组件/调用引用、`src/pages/` 路由） |
| Liquid | `.liquid` | 完全支持 |
| Pascal / Delphi | `.pas`, `.dpr`, `.dpk`, `.lpr` | 完全支持（类、记录、接口、枚举、DFM/FMX 表单文件） |
| Lua | `.lua` | 完全支持（函数、带接收者的方法、局部变量、`require` 导入、调用边） |
| R | `.R` `.r` | 完全支持（每种赋值形式的函数、S4/R5/R6 类带方法、`library`/`require` 导入、`source()` 文件引用、调用边） |
| Luau | `.luau` | 完全支持（Lua 中的所有内容，加上 `type`/`export type` 别名、类型化签名和 Roblox 实例路径 `require`） |

## 测量的跨文件覆盖率

影响和爆炸半径查询的好坏取决于其背后的依赖图，因此测量覆盖率而不是断言。**公平覆盖率** = 至少有一个*解析的跨文件依赖项*（导入、调用、引用或通过框架约定路由到它们）的符号承载源文件的比例，在每种语言的真实基准仓库上。剩余部分始终是真正的静态分析前沿（运行时动态分派、反射/DI 容器、框架约定入口点、供应的第三方代码），从不通过操纵分母来隐藏。

| 语言 | 基准仓库 | 覆盖率 |
|---|---|---|
| TypeScript / JavaScript | 此仓库 | 95.8% |
| Python | psf/requests | 100% |
| Go | gin-gonic/gin | 96.6% |
| Rust | BurntSushi/ripgrep | 86.7% |
| Java | google/gson | 93.3% |
| C# | jbogard/MediatR | 85.2% |
| PHP | guzzle/guzzle | 100% |
| Ruby | sidekiq/sidekiq | 100% |
| C | redis/redis | 92.2% |
| C++ | google/leveldb | 94.8% |
| Objective-C | SDWebImage | 91.6% |
| Swift | Alamofire | 95.3% |
| Kotlin | square/okhttp | 96.2% |
| Scala | gatling/gatling | 91.2% |
| Dart | flutter/packages | 92.4% |
| Svelte / SvelteKit | sveltejs/realworld | 100% |
| Vue / Nuxt | nuxt/movies | 93.5% |
| Astro | xingwangzhe/stalux | 93.0% |
| Lua | nvim-telescope/telescope.nvim | 84.2% |
| Luau | dphfox/Fusion | 92.2% |
| Liquid | Shopify/dawn | 73.8% |
| Pascal / Delphi | PascalCoin | 77.4% |

框架路由以相同方式验证，每个框架一个规范应用：Express 100%、FastAPI 98%、Flask 100%、NestJS 96.8%、Gin 96.5%、Axum 100%、Rocket 93.8%、Vapor 100%、Laravel 92%、Rails 89.6%、React Router 100% —— 以及诚实的静态分析上限的约定/反射密集型：ASP.NET 83.9%、Spring 83.3%、Drupal 78.9%、Play 76.3%、Django 74.1%。SvelteKit、Vue/Nuxt 和 Astro 使用基于文件的路由，因此其页面/端点覆盖率是上表中的 Svelte/SvelteKit (100%)、Vue/Nuxt (93.5%) 和 Astro (93.0% —— 每个 `src/pages/` 文件在两个验证仓库上映射到一个路由节点) 数字。

## 故障排除

**"CodeGraph 未初始化"** —— 首先在您的项目目录中运行 `codegraph init`。

**索引慢** —— 检查 `node_modules` 和其他大目录是否被排除。使用 `--quiet` 减少输出开销。

**MCP 命中 `database is locked`** —— 当前构建不应该：CodeGraph 捆绑自己的 Node 运行时并使用 WAL 模式的 Node 内置 `node:sqlite`，其中并发读取永远不会阻塞写入者。如果您仍然看到它：

- **您在旧版（0.9 之前）安装上。** 重新安装以获取捆绑运行时 —— `curl -fsSL https://raw.githubusercontent.com/colbymchenry/codegraph/main/install.sh | sh`（macOS/Linux）、`irm https://raw.githubusercontent.com/colbymchenry/codegraph/main/install.ps1 | iex`（Windows）或 `npm i -g @colbymchenry/codegraph@latest`。
- **`codegraph status` 显示 `Journal:` 不是 `wal`** —— WAL 无法在此文件系统上启用（在网络共享和 WSL2 `/mnt` 上常见），因此读取可能会阻塞写入者。将项目（及其 `.codegraph/` 文件夹）移到本地磁盘上。

**MCP 服务器未连接** —— 您的 agent 自己启动服务器，因此您不必手动启动它。确保项目已初始化和索引（`codegraph status`），并且 MCP 配置中的路径正确。如果仍然无法连接，重新运行 `codegraph install` 重写配置。

**缺少符号** —— MCP 服务器在保存时自动同步（等待几秒钟）。如有需要手动运行 `codegraph sync`。检查文件的语言是否受支持，并且不在 `.gitignore` 或默认排除的目录中（例如 `node_modules`、`dist`）。

**在 Windows 和 WSL 之间共享一个检出** —— 不要让两者指向同一个 `.codegraph/`：后台服务器锁和 SQLite 索引与写入它们的操作系统绑定，并且 WSL2/Windows 文件系统边界上的 SQLite 锁定不可靠。通过在一个上设置 `CODEGRAPH_DIR` 为不同的名称，让每一侧在同一个树中有自己的索引 —— 例如 Windows 上 `CODEGRAPH_DIR=.codegraph-win`，WSL 留在默认的 `.codegraph`。CodeGraph 在索引和监视时跳过任何同级的 `.codegraph-*` 目录，因此两者永远不会相互干扰。

## Star 历史

<a href="https://www.star-history.com/?repos=colbymchenry%2Fcodegraph&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=colbymchenry/codegraph&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=colbymchenry/codegraph&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=colbymchenry/codegraph&type=date&legend=top-left" />
 </picture>
</a>

## 许可证

MIT

---

<div align="center">

**为 AI 编程助手打造 —— Claude Code、Cursor、Codex CLI、opencode、Hermes Agent、Gemini CLI、Antigravity IDE 和 Kiro**

[报告错误](https://github.com/colbymchenry/codegraph/issues) · [请求功能](https://github.com/colbymchenry/codegraph/issues)

</div>
