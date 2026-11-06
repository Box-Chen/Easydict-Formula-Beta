## 2026-11-06 | 任务：准备理工科公式 Beta

**Links:** [执行计划](../../exec-plans/completed/2026-11/2026-11-06-formula-beta-distribution.md)、[上游 PR #1391](https://github.com/tisfeng/Easydict/pull/1391)

### 执行上下文

- **Agent Name:** Codex
- **Model:** GPT-6
- **Environment:** macOS 27.0 / Xcode 27.2 (27B52)

### 用户请求

提供临时公开的公式截图翻译 Beta 下载。首页优先注明原作者仓库及正式版发布后的下架计划。

### 变更

- 使用独立的应用名称和标识构建 Beta。
- Release 配置关闭上游更新、使用统计和崩溃报告。
- 首页提供出处、Beta 期限、使用方法、源码构建方法及许可证。

### 设计意图

分发仓库独立于上游贡献 fork。Beta 安装包和对应源码通过同一版本标签分发。

### 验证

- Xcode 27.2 Release 构建：arm64 与 x86_64 双架构成功。
- 本地 ZIP 解包后验证应用签名、二进制架构及 SHA-256 校验。

### 受影响文件

- `README.md`、`README_ZH.md`
- `Easydict.xcodeproj/project.pbxproj`、`Easydict/App/Info.plist`
- Beta 的更新及隐私设置和应用名称资源

### 后续事项

- 应用使用临时签名。Beta 未经 Apple 公证。
