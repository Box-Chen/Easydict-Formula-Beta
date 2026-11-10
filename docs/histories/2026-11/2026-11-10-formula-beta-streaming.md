## 2026-11-10 | 任务：分发带流式翻译的理工科公式 Beta 2

**Links:** [上游 PR #1391](https://github.com/tisfeng/Easydict/pull/1391) · [执行计划](../../exec-plans/completed/2026-11/2026-11-10-formula-beta-streaming.md)

### 执行上下文

- **Agent Name:** `Codex`
- **Model:** `GPT-6`
- **Environment:** `macOS 27.0 / Xcode 27.2 (27B52)`

### 用户请求

把 11 月 10 日的流式翻译及 Luna 默认 Low 同步到个人 Beta 仓库与下载页。

### 变更

- 合入上游 PR #1391 的 `29c0daae`，保留 Beta 独立应用标识与原有隐私、更新策略。
- 将 Beta Release 构建号更新为 71，README 的下载链接和源码标签指向 `v2.27.0-formula-beta.2`。
- 构建通用 ZIP，并随包附上 GPL-3.0 许可证及独立 SHA-256 校验文件。

### 设计意图

按发行版本关联可下载的应用和对应源码。Beta 1 的发布页可提供 Beta 2 下载入口。

### 验证

- `xcodebuild build` 的 arm64 和 x86_64 Release 构建通过。
- 解压后确认独立标识、版本 2.27.0（71）、最低目标 macOS 13、Mach-O 架构及临时签名，核对 GPL 许可证与 ZIP 的 SHA-256。
- 流式翻译相关源码与上游 `29c0daae` 一致。132 项 Codex 与 Markdown 回归结果来自该上游提交的 Debug 构建。

### 受影响文件

- `Easydict.xcodeproj/project.pbxproj`
- `README.md` 与 `README_ZH.md`
- 上游源码合并及 Beta 分发记录。

### 后续事项

- 安装包未经 Apple 公证。Intel 已编译并通过包校验。
