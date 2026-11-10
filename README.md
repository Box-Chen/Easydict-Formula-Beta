**原作者与官方仓库：[tisfeng / Easydict](https://github.com/tisfeng/Easydict)。**

# Easydict 理工科公式 Beta

这是由 [Box-Chen](https://github.com/Box-Chen) 提供的非官方 Beta，仅在 [上游 PR #1391](https://github.com/tisfeng/Easydict/pull/1391) 等待审查及发布期间，供有需要的用户提前体验。等原作者发布包含这些新增功能的正式版本后，我们会关闭 Beta 下载并删除本临时仓库。日常使用可前往 [Easydict 官方发布页](https://github.com/tisfeng/Easydict/releases)。

**[下载 macOS Beta](https://github.com/Box-Chen/Easydict-Formula-Beta/releases/tag/v2.27.0-formula-beta.1)** · [对应源码](https://github.com/Box-Chen/Easydict-Formula-Beta/tree/v2.27.0-formula-beta.1) · [GPL-3.0 许可证](./LICENSE)

应用最低目标为 macOS 13。公式模式还需要适用于该系统的本机 Codex CLI。下载 Release 里的 ZIP，解压后打开 **Easydict Formula Beta.app**。它使用独立的应用标识，可以与官方 Easydict 并存。此包采用临时签名，未经 Apple 公证，macOS 可能拦截首次打开。也可以从同一版本的源码自行编译。[Apple 的打开提示说明](https://support.apple.com/102445)

首次使用公式模式时，先安装本机 Codex CLI 并用自己的 ChatGPT 账户登录。公式模式会把框选的画面发送给 Codex 处理。在菜单栏或翻译窗口顶部打开「理工科公式模式」，用截图翻译快捷键（默认 `⌥S`）框选公式，按提示为 Beta 单独授予屏幕录制权限。原文和译文都支持 LaTeX 排版，复制按钮可获取源码。点击 Codex 卡片上的模型名称可选视觉模型与思考强度。关闭公式模式后可使用普通 OCR 翻译。查询历史、最近截图和 OCR 原文日志的自动保存默认关闭，可在「设置 → 隐私」调整。

### 从对应源码构建

用 Xcode（本次使用 27.2）打开 `Easydict.xcworkspace`，选择 `Easydict` scheme 和 Release 配置。仓库已包含 CocoaPods 依赖，首次构建需联网解析 Swift Package。也可以运行：

```sh
EASYDICT_RELEASE_PACKAGING=YES xcodebuild build \
  -workspace Easydict.xcworkspace -scheme Easydict -configuration Release \
  -destination 'generic/platform=macOS' -derivedDataPath .tmp/formula-beta-build \
  ARCHS="arm64 x86_64" ONLY_ACTIVE_ARCH=NO CODE_SIGN_IDENTITY=- \
  CODE_SIGN_STYLE=Manual PROVISIONING_PROFILE_SPECIFIER= DEVELOPMENT_TEAM= \
  CODE_SIGN_ENTITLEMENTS=
```

<details>
<summary>上游 Easydict 项目介绍 / Upstream Easydict README</summary>

<p align="center">
  <img src="https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/icon_512x512@2x.png" height="256">
  <h1 align="center">Easydict</h1>
  <h4 align="center"> Easy to look up words or translate text</h4>
<p align="center"> 
<a href="https://github.com/tisfeng/easydict/blob/main/LICENSE">
<img src="https://img.shields.io/github/license/tisfeng/easydict"
            alt="License"></a>
<a href="https://github.com/tisfeng/Easydict/releases">
<img src="https://img.shields.io/github/downloads/tisfeng/easydict/total.svg"
            alt="Downloads"></a>
<a href="https://img.shields.io/badge/-macOS-black?&logo=apple&logoColor=white">
<img src="https://img.shields.io/badge/-macOS-black?&logo=apple&logoColor=white"
            alt="macOS"></a>  
</p>

<div align="center">
<a href="./README_ZH.md">中文</a> &nbsp;&nbsp;|&nbsp;&nbsp; <a href="./README.md">English</a>
</div>

## Easydict

`Easydict` is a concise and easy-to-use translation dictionary macOS App that allows you to easily and elegantly look up words or translate text.

Easydict is ready to use out of the box, can automatically recognize the language of the input text, supports input translate, select translate, and OCR screenshot translate, and can query multiple translation services results at the same time.

**Supported services:** 20+ dictionary, translation, AI, local-model, and CLI services, including
Apple Dictionary, MDict, Apple Translate, OpenAI, Gemini, Claude, DeepSeek, Ollama, Claude Code,
Codex CLI, DeepL, Google, and Bing. See the [services overview](./docs/user-docs/en/SERVICES.md) for
the complete list and access requirements.

![Log](https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/Log-1688378715.png)

<table>
    <td> <img src="https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/iShot_2023-05-28_16.32.18-1685262784.png">
    <td> <img src="https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/iShot_2023-05-28_16.32.26-1685262803.png">
</table>

![immerse-1686534718.gif](https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/immerse-1686534718.gif)

## Features

- 🚀 Out of the box, automatic language recognition
- 🖱️ Auto select with mouse and shortcut key
- 📸 OCR screenshot translation and silent screenshot OCR
- 🔊 Multiple TTS voice services
- 📚 Support 🍎 [Apple Dictionary](./docs/user-docs/en/How-to-use-macOS-system-dictionary-in-Easydict.md) and [Apple Translate](./docs/user-docs/en/How-to-use-macOS-system-translation-in-Easydict.md)
- 🌐 Support 20+ dictionary, translation, AI, local-model, and CLI services
- 🗣️ Support 52 selectable translation languages

**If you like this app, please consider giving it a [Star](https://github.com/tisfeng/Easydict) ⭐️, thanks! (^-^)**

## Contributing

Contributions through issues and pull requests are welcome. Read the Chinese
[contribution guide](./CONTRIBUTING.md) for the development workflow and pull
request requirements.

### AI Coding

We welcome contributions assisted by programming agents such as `Codex` and
`Claude`. Prefer the latest available GPT or Claude model suitable for complex
coding tasks, and carefully review and test the final changes. See the Chinese
[contribution guide](./CONTRIBUTING.md) for the Agent workflow and
review requirements.

## Issue/PR Triage Notes

The maintainer has been quite busy recently and usually only has time to triage issues on weekends. PRs (especially bugfix PRs) are prioritized. Also, due to an overloaded inbox and notifications, some messages may not be seen or replied to promptly. Thanks for your understanding.

## Installation

### Homebrew Installation (Recommended)

```bash
brew install --cask easydict
```

### Manual Installation

[Download](https://github.com/tisfeng/Easydict/releases) the latest release.

> [!NOTE]
> Latest version supports macOS 13.0+, for older systems please use [2.7.2](https://github.com/tisfeng/Easydict/releases/tag/2.7.2)

---

## Usage

| Ways                      | Description                                                                                                                                  | Preview                                                                                                                                        |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| Input Translate           | Press the input translate shortcut key (default `⌥ + A`), enter the text to be translated, and `Enter` key to translate          | ![iShot_2023-01-20_11.28.46-1674185354](https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/iShot_2023-01-20_11.28.46-1674185354.gif) |
| Mouse Select Translate    | The query icon is automatically displayed after the word is selected, and the mouse hovers over it to query                                  | ![iShot_2023-01-20_11.01.35-1674183779](https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/iShot_2023-01-20_11.01.35-1674183779.gif) |
| Shortcut Select Translate | After selecting the text to be translated, press the shortcut key (default `⌥ + D`)                                                          | ![iShot_2023-01-20_11.24.37-1674185125](https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/iShot_2023-01-20_11.24.37-1674185125.gif) |
| Screenshot Translate      | Press the screenshot translate shortcut key (default `⌥ + S`) to capture the area to be translated                                           | ![iShot_2023-01-20_11.26.25-1674185209](https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/iShot_2023-01-20_11.26.25-1674185209.gif) |
| Silent Screenshot OCR     | Press the Silent Screenshot shortcut key（default `⌥ + ⇧ + S`）to capture the area, the OCR results will be copied directly to the clipboard | ![屏幕录制 2023-05-20 22 39 11](https://github.com/Jerry23011/Easydict/assets/89069957/c16f3c20-1748-411e-be04-11d8fe0e61af)                     |

---

## Documentation

- 📖 [Complete Usage Guide](./docs/user-docs/en/GUIDE.md) - Detailed features, configuration and tips
- 🌐 [Services Overview](./docs/user-docs/en/SERVICES.md) - Complete service list and access requirements
- 🔧 [Developer Build Guide](./docs/user-docs/en/GUIDE.md#developer-build) - Build and run from source code
- 🍎 [How to use Apple Dictionary](./docs/user-docs/en/How-to-use-macOS-system-dictionary-in-Easydict.md)
- 📚 [How to use MDict](./docs/user-docs/en/How-to-use-MDict-in-Easydict.md)
- 🍎 [How to use Apple Translate](./docs/user-docs/en/How-to-use-macOS-system-translation-in-Easydict.md)
- 🌍 [How to translate Easydict](./docs/user-docs/en/How-to-translate-Easydict.md)

---

## Acknowledgements

- This project was inspired by [saladict](https://github.com/crimx/ext-saladict) and [Bob](https://github.com/ripperhe/Bob), and the initial version was made based on [Bob (GPL-3.0)](https://github.com/1xiaocainiao/Bob). Easydict has made many improvements and optimizations on the original project, and many features and UI are referenced from Bob.
- Screenshot feature is based on [isee15](https://github.com/isee15)'s [Capture-Screen-For-Multi-Screens-On-Mac](https://github.com/isee15/Capture-Screen-For-Multi-Screens-On-Mac), and optimized on this project.
- Select text feature is referenced from [PopClip](https://pilotmoon.com/popclip/).

## Statement

Easydict is licensed under the [GPL-3.0](https://github.com/tisfeng/Easydict/blob/main/LICENSE) open source license, which is for learning and communication only. Anyone can get this product and source code for free. If you believe that your legal rights have been violated, please contact the [author](https://github.com/tisfeng) immediately. You can use the source code freely, but you must attach the corresponding license and copyright.

## Sponsor

Easydict is a free and open source project, currently mainly developed and maintained by the author. If you like this project and find it helpful, you can consider sponsoring this project to support it, so that it can go further.

Thanks to [@CanglongCl](https://github.com/CanglongCl) for providing the Apple Developer account, which solved the app [signature issue](https://github.com/tisfeng/Easydict/issues/2), allowing more people to use Easydict conveniently.

<a href="https://afdian.com/a/tisfeng"><img width="20%" src="https://pic1.afdiancdn.com/static/img/welcome/button-sponsorme.jpg" alt=""></a>

<div>
  <img src="https://raw.githubusercontent.com/tisfeng/ImageBed/main/uPic/IMG_4739-1684680971.JPG" width="30%">
</div>

Thanks to all sponsors for their generous support. For details, please see the [Sponsor List](./docs/user-docs/en/SPONSOR_LIST.md).

---

## Star History

<a href="https://tisfeng.github.io/Easydict/star-history/#tisfeng/easydict&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./docs/assets/star-history/star-history-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="./docs/assets/star-history/star-history-light.svg" />
    <img alt="Star History Chart" src="./docs/assets/star-history/star-history-light.svg" />
  </picture>
</a>

</details>
