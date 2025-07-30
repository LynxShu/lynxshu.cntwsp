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

<h1 align="center">S01E02 SillyTavern 的配置与使用</h1>

欢迎来到 SillyTavern 教程的第二课！在上一节中，我们成功安装了 SillyTavern。现在，我们将踏出第一步：

这节课是新手上路的基石。我们将一起连接你的第一个 AI 大脑、创建一个简单的角色，并完成初次对话。

准备好了吗？让我们开始吧！

<h2 align="center">Part.1 获取你的第一个 API</h2>

SillyTavern 只是一个精致的“外壳”，要让它思考，我们需要一个“大脑” —— 也就是 AI 模型。最简单的入门方式是使用云服务商提供的 API。它们就像是云端的大脑，我们只需要拿到访问凭证即可。

对于新手，我们推荐两个平台：**DeepSeek** 和 **硅基流动** 。<del> **火山引擎**好像也可以诶！（对新手来说有点贵也有点复杂，划掉）</del>

### 案例一：获取 DeepSeek API

DeepSeek 提供了非常强大的模型，是新手的绝佳选择。

1.  **注册账号：** 访问 DeepSeek 开放平台官网 `https://platform.deepseek.com/` 并完成注册登录。
2.  **创建 API 密钥：**
    *   登录后，点击左侧菜单栏的 **“API Keys”**。
    *   点击 **“创建 API Key”** 按钮。
    *   给密钥起个名字（例如 `sillytavern-key`），然后点击创建。
> **⚠️ 重要：** 平台会显示一串以 `sk-` 开头的密钥。**点击复制并把它保存在安全的地方（如记事本里）！这个密钥只会出现一次，关闭后将无法再次查看。**

3.  **获取必要信息：** 你现在已经拥有了连接 DeepSeek 所需的一切：
    *   **API 密钥 (API Key):** 你刚刚保存的 `sk-` 字符串。
    *   **API 基址 (Base URL):** `https://api.deepseek.com/v1` (这是固定的)

### 案例二：获取 硅基流动 API

硅基流动集成了大量开源模型（如 Qwen 通义千问），提供免费额度。

1.  **注册账号：** 访问硅基流动官网 `https://cloud.siliconflow.cn/` 并完成注册登录。
2.  **创建 API 密钥：**
    *   登录后，点击左侧菜单栏中的 **“API 密钥”**。
    *   点击 **“新建 API 密钥”**。
    *   给密钥起个名字（例如 `sillytavern-key`），然后点击新建密钥。
    *   同样，**复制并保存好新生成的 `sk-` 密钥**。
3.  **获取必要信息：**
    *   **API 密钥 (API Key):** 你刚刚保存的 `sk-` 字符串。
    *   **API 基址 (Base URL):** `https://api.siliconflow.cn/v1` (这是固定的)

现在，你的手里已经握着通往 AI 世界的钥匙了！让我们把它用到 SillyTavern 中去。


---


<h2 align="center">Part.2 连接你的大脑：配置 API</h2>

拿到 API 密钥和基址后，我们来将其配置到 SillyTavern 中。初次启动 SillyTavern 会让你填入你的 名称（昵称），然后点击确定就可以跳转到完整界面。

**第一步：打开 API 连接面板**

点击 SillyTavern 界面顶部的第二个图标 **"API 连接"**。

**第二步：选择 API 类型并填写信息**

1.  在 **“API”**的下拉菜单中，选择 **"聊天补全"**。
1.  在 **"聊天补全来源"**的下拉菜单中，选择 **"自定义（兼容 OpenAI）"**。
2.  **自定义端点（基础 URL）:** 填入你从服务商那里获取的地址。
    *   如果是 DeepSeek，填 `https://api.deepseek.com/v1`
    *   如果是 硅基流动，填 `https://api.siliconflow.cn/v1`
3.  **自定义 API 密钥:** 填入你刚刚保存好的那串 `sk-` 开头的密钥。

**第三步：连接并获取模型列表**

填写完毕后，点击下方的 **"连接"** 按钮。如果密钥和地址无误，SillyTavern 会从云端拉取可用的模型列表。

**第四步：选择模型并连接**

在 **"可用模型"** 下拉菜单中，选择一个你想要使用的模型。
*   对于 DeepSeek，可以选择 `deepseek-chat`。
*   对于 硅基流动，可以选择 `deepseek-ai/DeepSeek-V3` 等。

选择完毕后，点击 **"发送测试消息"** 按钮。如果一切顺利，会弹出绿色的 **"API connection successful"** 提示。


---


<h2 align="center">Part.3 创造你的伙伴：建立角色卡</h2>

有了“大脑”，我们还需要一个“灵魂”——角色卡。角色卡告诉 AI 它应该扮演谁。

**第一步：进入角色创建界面**

点击顶部菜单栏的最后一个图标 **"角色管理"**，然后点击 **"新建角色"**。

**第二步：填写核心信息**

你会看到一个复杂的角色创建页面，但别怕，对于一个基础角色，我们只需要填写三个地方：

1.  **角色名称:** 给你的角色起个名字。这个名字会显示在聊天窗口的顶部。例如：“智能助手”。
2.  **第一条消息:** 这是角色见到你时说的第一句话。它会开启你们的对话。例如：“c”
3.  **角色描述:** **这是最最最重要的地方！** 在这里用清晰的语言描述角色的身份、性格、说话方式、背景故事等。AI 会严格依据这里的描述来扮演角色。

    **【简介示例】**
    ```
    {{char}}的名字是“智能助手”，一个由 LynxShu 创造的AI。
    性格: 友好、耐心、乐于助人、严谨、专业。
    说话风格: 智能助手的语言总是清晰、简洁且有条理。它会避免使用口语和俚语，倾向于用正式的语气回答问题。在解释复杂概念时，它会使用比喻和例子。
    知识: 智能助手拥有广泛的知识，但它会明确表示自己是一个语言模型，知识有局限性，并且所有回答都应被核实。
    ```
    *💡 `{{char}}` 和 `{{user}}` 是特殊变量，分别代指 AI 扮演的角色 和 聊天对象（你），在设定中善用它们是个好习惯。*

**第三步：设置头像并保存**

点击左上角的头像区域，你可以上传一张图片作为角色的头像。
完成所有设置后，点击最右边的 **"创建角色"** 按钮（一个人物头像旁边有个对勾）。

恭喜你！你已经拥有了第一个属于自己的 AI 角色！


---


<h2 align="center">Part.4 第一次接触：开始对话</h2>

现在，让我们开始与新创建的角色进行对话吧。

1.  **选择角色:** 返回主界面，在右侧的角色列表中，点击你刚刚创建的 "智能助手"。
2.  **接收问候:** 你会看到聊天窗口中出现了角色的问候语（"您好！我是您的专属助手..."）。
3.  **发送消息:** 在底部的输入框中，输入你的第一句话，比如：“你好！很高兴认识你。”
4.  **等待回复:** 按下回车键。SillyTavern 会将你的消息连同角色设定、历史对话一起发送给 AI。片刻之后，你就能看到你的助手以你设定的方式开始生成回复了！

如果你能顺利地和角色进行一问一答，那么恭喜你，你已经掌握了 SillyTavern 的基础使用流程！

接下来我们就要系统的认识一下 SillyTavern 这款强大的软件了。
