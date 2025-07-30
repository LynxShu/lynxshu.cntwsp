<h1 align="center">
  <a href="https://github.com/LynxShu/lynxshu.cntwsp">
    <img alt="LynxShu" src="assets/img/md_logo.png"><br>
  </a>
  
  <a href="https://github.com/LynxShu/lynxshu.cntwsp/blob/main/LICENSE">
    <img alt="license" src="https://img.shields.io/badge/License%20-%20CC--BY--NC--SA%204.0-%20%23006cff?style=flat-square&logo=creativecommons&logoColor=white">
  </a> 
  <a href="https://space.bilibili.com/582462">
    <img alt="bilibili" src="https://img.shields.io/badge/Bilibili%20-%20LynxShu%20-%20%23006cff?style=flat-square&logo=bilibili&logoColor=white">
  </a> 
  <a href="https://github.com/LynxShu">
    <img alt="github" src="https://img.shields.io/badge/Github%20-%20LynxShu%20-%20%23006cff?style=flat-square&logo=github&logoColor=white">
  </a>
</h1>

<h1 align="center">S01E01 SillyTavern 的简介与安装</h1>

<h2 align="center">Part.1 什么是 SillyTavern</h2>

<div style="text-align:center">
  <img src="assets/img/s01e01/sillytavern_logo.png" alt="sillytavern" />
</div>

**SillyTavern**（简称 ST）是一个安装在本地电脑上的一站式 AI 交互界面。它是一个强大的“中枢系统”，让你能够同时连接和管理文本、图像、语音三大类 AI 模型，并将它们无缝融合在同一个聊天体验中。

那么，SillyTavern 到底是什么？

简单来说，SillyTavern 是一个安装在你电脑上的 **“AI 万能遥控器”**。

你可能玩过网页版的 AI 聊天，但那些都太“傻瓜相机”了，能调的选项很少。而 SillyTavern 就像一台“专业单反”，它本身不是 AI，但可以连接并指挥各种各样的 AI 模型，让你能：

## 核心功能

- 👑 和 AI 聊天对话：进行角色扮演、写故事、头脑风暴，自由度极高。无论是云端的 API 还是本地部署的模型，都能进行深度定制和交互。

- 🎨 让 AI 帮你画画：在对话中随时让 AI 根据你的描述生成图片。

- 🔊 让 AI 开口说话：通过 TTS（文本转语音）技术，让 AI 角色的回复可以直接被“说”出来，极大增强了代入感。

## 自由与强大

它的最大特点就是 “自由” 和 “强大”。为了让你能榨干 AI 的每一分潜力，SillyTavern 提供了海量的设置选项。虽然一开始可能会感觉有点复杂，但这正是它的魅力所在——当你掌握它后，AI 就会成为你手中最听话、最聪明的创作工具。

## 开源与免费

SillyTavern 是一个**完全免费、开源**的项目，由全球超过200名贡献者共同开发和维护。它脱胎于经典的 **TavernAI**，经过近两年的独立发展，现已成为 AI 爱好者和高级玩家的首选软件之一。

## 核心与本质

SillyTavern 的一切都围绕着一个概念：**“上下文工程”**。

说白了，就是**“如何让AI好好说话”**的艺术。你要明白，AI 模型本身是没有记忆的。你每次和它进行对话，它都会 **“忘记”** 你们之前聊了什么，为什么你觉得它有记忆？因为它每次都在读取你们之间的 **“历史聊天记录”**。

SillyTavern 的工作方式，就是把你的角色设定、历史聊天记录、世界背景，临时指令等所有信息，在每次发送时都打包成一份完美的**“临时记忆”**（即“上下文”），然后一股脑地喂给 AI。

---

<h2 align="center">Part.2 如何安装 SillyTavern</h2>

## 准备工作 & 安装方式选择

在正式开始前，请确保你的 Windows 电脑已完成**第一项准备工作**。然后根据你的需求，在两种安装方式中选择一种。

### 1. 共同准备：安装 NodeJS

无论你选择哪种方式，都需要先安装 NodeJS，它是 SillyTavern 运行所需要的基础环境。

- **NodeJS** - [官网下载](https://nodejs.org/en/download) | [国内网盘下载](https://pan.baidu.com/s/5Ep9b4L4HMODM8MxquMCmpg)
- **安装建议**：下载 **LTS (长期支持版)** 版本。安装时一路点击“Next”即可，无需特殊配置。

### 2. 选择安装方式

- 如果你的**网络环境健康**并希望方便地获取后续更新，我**强烈推荐**你使用 **Git 安装**。
- 如果你的**网络环境不佳**，那么直接下载 **ZIP 压缩包**更简单。

<h3 align="center">【推荐】使用 Git 的方式安装（网络环境健康）</h3>

此方法还需要额外安装 Git for Windows。

- **Git For Windows** - [官网下载](https://gitforwindows.org/) | [国内网盘下载](https://pan.baidu.com/s/5Ep9b4L4HMODM8MxquMCmpg)
- **安装建议**：安装时一路点击“Next”即可。

安装好 Git 后，我们开始下载 SillyTavern 本体。

**第一步：在你喜欢的位置打开终端**

找一个**空间足够大、路径不含中文**的位置，新建一个文件夹（例如 `D:\AI`）。然后根据你的系统，用以下方式在此文件夹内打开命令行窗口：

- **Windows 11:** 在文件夹空白处**右键** -> 点击 **“在终端中打开”**。
- **Windows 10:** 按住 `Shift` 键不放，同时在文件夹空白处**右键** -> 点击 **“在此处打开 PowerShell 窗口”**。

**第二步：克隆项目仓库**

在弹出的黑色或蓝色命令行窗口中，**完整复制并粘贴**以下命令，然后按回车：

```bash
git clone https://github.com/SillyTavern/SillyTavern -b release
```
你会看到终端开始下载文件，请耐心等待。

**第三步：启动 SillyTavern**

下载完成后，原来的文件夹内会出现一个名为 `SillyTavern` 的新文件夹。
进入这个 `SillyTavern` 文件夹，双击 `Start.bat` 即可开始运行。首次运行需要安装一些依赖项，可能会稍慢一些，之后它会自动用浏览器打开 SillyTavern 的界面。

> **💡 可能遇到的问题：** 如果执行 `git clone` 命令时速度极慢或直接报错（通常是网络问题），那么 Git 的方式可能不适合你。请直接尝试下方的 ZIP 压缩包安装方法。

**指令解释**

- `git`: 告诉电脑，我们要调用 **Git** 这个程序。
- `clone`: “克隆”，它会把远程服务器上的整个项目，包括所有的文件和完整的更新历史，原封不动地复制（克隆）一份到你的电脑上。正是因为保留了更新历史，我们后续才能用简单的命令进行更新。
- `https://git..../SillyTavern`: 这是要克隆的项目的“地址”。它指向 GitHub 网站上 SillyTavern 项目的仓库。
- `-b`: 这是 --branch 的缩写，一个“参数”或“选项”，意思是“我要**指定一个分支**”。一个软件项目通常有很多“分支”，就像一棵树的树枝。主干上是最新的开发代码，而其他分支可能是测试版、稳定版等。
- `release`: 这就是我们要指定的分支的名字。release 分支是 SillyTavern 官方发布的**稳定版本**。对于绝大多数用户来说，使用这个分支是最安全、最稳妥的选择。


<h3 align="center">【备选】使用 ZIP 压缩包安装（网络环境不佳）</h3>

此方法非常简单，尤其适合网络不佳或不想折腾的用户。请确保你已经安装了本章节开头的 **NodeJS**。

**第一步：下载 SillyTavern 压缩包**

- [GitHub官方下载页面](https://github.com/SillyTavern/SillyTavern/releases/latest) | [国内网盘分流下载](https://pan.baidu.com/s/5Ep9b4L4HMODM8MxquMCmpg)
- **注意**：如果你能访问 Github，请从 GitHub 下载 `Source code (zip)`。网盘分流的版本可能不是最新的。

**第二步：解压并运行**

将下载好的压缩包解压到你喜欢的位置（路径不要有中文）。
进入解压后的 `SillyTavern` 文件夹，双击 `Start.bat` 即可开始运行。首次运行需要安装一些依赖项，可能会稍慢一些，之后它会自动用浏览器打开 SillyTavern 的界面。
