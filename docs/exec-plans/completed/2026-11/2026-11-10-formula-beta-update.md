# 更新理工科公式 Beta

- 状态：completed
- 创建日期：2026-11-10
- 负责人：Box-Chen
- 关联 Issue/PR：https://github.com/tisfeng/Easydict/pull/1391

## 执行上下文

- **Agent Name:** `Codex`
- **Model:** `GPT-6`
- **Environment:** `macOS 27.0 / Xcode 27.2 (27B52)`

## 背景

个人仓库的预览包基于 2.26.0，PR #1391 已有新的公式、OCR 和隐私修复。

## 目标与范围

- 目标结果：把 2b5a1265 集成到 Beta 主分支并发布通用安装包。
- 允许修改路径：合并改动、Beta 分发配置、README 的下载链接和交付记录。
- 同任务 history：`docs/histories/2026-11/2026-11-10-formula-beta-update.md`
- 用户限制：发布目标为个人仓库 Box-Chen/Easydict-Formula-Beta。
- 非目标：变更上游 PR 或安装本机应用。
- 验收标准：对应源码、标签、签名通过校验的双架构 ZIP 及 SHA-256 文件可下载。

## 工作计划

1. 合并精确的 PR 提交，保留 Beta 识别及分发设置。
2. 构建 Release，检查版本、架构、签名及 ZIP。
3. 更新个人仓库并确认发布资产。

## 风险与决策

- 保留独立应用标识、无上游自动更新及无上游遥测设置。
- 保留旧版标签，使用新预发布标签标记对应源码。

## 进度

- [x] 确认 Beta 与 PR 源码基线。
- [x] 集成源码并构建、校验发布包。

## 验证

- Xcode 27.2 Release 双架构构建通过。
- 解压后校验签名和许可证，ZIP SHA-256 与归档一致。

## 完成条件

- 构建和打包校验通过，源码准备提交。
