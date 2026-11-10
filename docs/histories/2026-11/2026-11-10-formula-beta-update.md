## 2026-11-10 | 任务：更新理工科公式 Beta 至 2.27.0

**Links:** [上游 PR #1391](https://github.com/tisfeng/Easydict/pull/1391) · [执行计划](../../exec-plans/completed/2026-11/2026-11-10-formula-beta-update.md)

### 执行上下文

- **Agent Name:** `Codex`
- **Model:** `GPT-6`
- **Environment:** `macOS 27.0 / Xcode 27.2 (27B52)`

### 用户请求

将最新版本同步到个人 Easydict-Formula-Beta 仓库。

### 变更

- 合入 PR #1391 的 `2b5a1265`，保留独立应用标识、关闭上游自动更新和遥测的 Beta 配置。
- 保持个人仓库的机器人禁用策略，并把 README 下载链接指向 `v2.27.0-formula-beta.1`。
- 构建 Apple Silicon 与 Intel 通用 ZIP，附上 GPL-3.0 许可证和 SHA-256 校验文件。

### 设计意图

保留旧发布和主分支历史，使体验者可以直接下载新版，同时能找到与安装包对应的源码。

### 验证

- `xcodebuild build` 的双架构 Release 构建通过。安装包版本为 2.27.0，最低目标为 macOS 13。
- `lipo -archs` 确认包内可执行 Mach-O 文件包含 arm64 与 x86_64。
- 解压后的应用通过 `codesign --verify --deep --strict`，ZIP 通过 `shasum -c SHA256SUMS.txt`。

### 受影响文件

- `Easydict.xcodeproj/project.pbxproj`
- `README.md` 和 `README_ZH.md`
- 上游源码合并及 Beta 分发记录。

### 后续事项

- 应用采用临时签名，未经 Apple 公证。双架构已编译并校验，未进行 Intel 真机运行测试。
