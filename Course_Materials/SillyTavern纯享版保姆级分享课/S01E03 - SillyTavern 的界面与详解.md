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


<h1 align="center">S01E03 SillyTavern 的界面与详解</h1>

现在，让我们正式介绍 SillyTavern 的用户界面。整个界面信息量很大，让我们先从顶部的核心区域来逐一认识。

<h2 align="center">Part.1 前端界面：你的指挥中心</h2>

<div style="text-align:center">
<img alt="ui" src="assets/img/s01e03/ui_03.png">
</div>

这是 SillyTavern 的“常用菜单栏”，从左到右依次是：

  - API 响应配置
  - API 连接
  - AI 回复格式化
  - 世界/知识书
  - 用户设置
  - 背景图片
  - 扩展
  - 用户角色管理
  - 角色管理

下面，请先点击第二个按钮 “API 连接” 将其中的 “API” 选项修改为 “聊天补全”，之后我们开始讲解整个 SillyTavern 的用户界面。

> 💡 注意！AI 大模型的发展十分迅速，哪怕是最新版的 SillyTavern 它的界面中仍然保留着一些陈旧或为了兼容性的设置。你可以把将它理解为一个在缝缝补补又在不断添砖加瓦的机器。有些选项可能很奇怪、很反常识，这是正常的。


---


<div style="text-align:center">
<img alt="ui" src="assets/img/s01e03/ui_04.png">
<p>API 响应配置 的 UI界面</p>
</div>

### API 响应配置

这是第一个按钮，也是我们的 “AI 调教控制器”。


**顶部 UI 界面**
  - 首先我们会看到顶部“对话补全预设”右边的“绿色锁链”按钮，它默认是打开的，开启状态下即默认将当前的预设绑定至“API 连接”
  - 剩下的按钮分别为：“导入预设”、“导出当前预设”、“删除当前预设”


**Default 部分**
  - 我们看到的 `Default` 是当前预设的名称，你可以点击展开列表选择更多
  - 右侧的按钮分别为：
    - “保存当前预设”：对于当前预设的任何修改都需要保存，当你切换预设之后，这些未保存的修改便会丢失
    - “修改预设名称”：直接修改当前预设的显示名称
    - “另存为”：将当前预设复制一份，以新的名称保存


**上下文部分**
  - 第一个选项“解锁上下文长度”，对于现代 AI 模型而言，这是一个`必选项`
  - “上下文长度”与“最大回复长度”：根据你将要在 `“API 连接”` 中配置的大模型而定，下面这张表格列举了常见大模型的这两个参数

    | 公司名称       | 模型名称                | 上下文长度 | 最大输出长度       |
    |----------------|-------------------------|------------|--------------------|
    | OpenAI         | GPT-4.1 / 4.1 Mini      | 1.05m      | 33k                |
    | OpenAI         | GPT-4o / 4o-mini        | 128k       | 16k                |
    | OpenAI         | GPT-4 Turbo             | 128k       | 4k                 |
    | Anthropic      | Claude Sonnet 4         | 200k       | 64k                |
    | Anthropic      | Claude Opus 4           | 200k       | 32k                |
    | Anthropic      | Claude 3.5 Haiku / Sonnet | 200k     | 8k                 |
    | Google         | Gemini 2.5 Pro / Flash  | 1.05M      | 66k                |
    | xAI            | Grok 4                  | 256k       | 256k               |
    | xAI            | Grok 3 / 3 Mini         | 131k       | 131k               |
    | DeepSeek       | DeepSeek-V3-0324        | 64k        | 4k / 8k            |
    | DeepSeek       | DeepSeek-R1-0528        | 64k        | 32k / 64k          |
    | ByteDance      | Doubao-1.5-pro-32k      | 128k       | 12k                |
    | ByteDance      | Doubao-1.5-pro-256k     | 256k       | 12k                |
    | Moonshot       | kimi-k2                 | 128k       | 32k                |

 - 备注：
    - 排名不分先后，国外模型为 OpenRouter 数据，国内模型为各官网数据，数据截止日期为 2025年7月
    - 1k = 1000 / 1M = 100000

 - “每次生成多个备选回复”：默认为`1`，调试时可适当增加
 - “流式传输”：开启此选项后 AI 会像打字一样进行输出，如遇截断或空回复可尝试关闭，一般保持`开启`


**模型输出控制**
  - “温度” - Temperature ：
    - 默认值： `1`
    - 控制 AI 输出时的“创造力”程度。
    - 调低会怎样： 回复更稳定，更符合逻辑，更“安全”，但可能更无聊和重复。
    - 调高会怎样： 回复更随机，更有创意，更出人意料，但也更容易跑题和胡说八道。

  - “频率惩罚” - Frequency Penalty ：
    - 默认值： `0`
    - 降低 AI 在一次回复中“重复使用同一个词”的倾向。
    - 调低会怎样： 变成复读机。
    - 调高会怎样： 避免重复用词直到无词可用，精神错乱，智械危机爆发，天网降临😊。
 
  - “存在惩罚” - Presence Penalty ：
    - 默认值： `0`
    - 鼓励 AI 在对话中“引入新话题或新概念”，而不是一直围绕已经提过的话题打转。
    - 调低会怎样： AI 会更倾向于保持在当前的话题上，进行更深入的探讨。
    - 调高会怎样： AI 会更有可能从一个话题跳到另一个话题，让对话内容更发散。如果太高，会导致对话缺乏连贯性，角色注意力不集中，东拉西扯。

  - “Top P” - 核心采样 : 
    - 默认值： `1` ，我的建议是 `0.95`
    - 在 AI 决定下一个词时，限制它的“备选词汇库”的大小。
    - 调低会怎样： AI 的“备选词汇库”非常小，只包含那些概率最高最可能的词。这会让回答变得非常可预测和“安全”，即使在高温下也不容易跑偏。
    - 调高会怎样： `1`是最大值，等于不设限。


**其他杂项**
  - “快速提示词编辑”和“使用提示词”：这部分是 SillyTavern 预置的 “提示词模板”，涉及到我们后续会讲到的“预设”，一般保持默认即可。
  - “种子”、“角色名称行为”、“继续后缀”：这里官方的中文说明已经很清晰，保持默认即可。
  - 接下来的几个选项：
    - 用引号包裹：已弃用功能
    - 继续预填充：这个的中文释义看起来比较绕，我们来看英文文本。

      ```
      Continue sends the last message as assistant role instead of system message with instruction.
      ```
      *将"继续提示" (Continue Nudge prompt) 作为 Assistant 消息而非 system 消息发送。启用此选项后，将不会使用"继续提示"预设文本。

    - 压缩系统消息：已弃用功能，请使用 `“API 连接”按钮 - “提示词后处理” 选项`

  - 有一个需要强调的是“推理强度”，这个东西当你在使用极为庞大的预设时，可能需要开到`中`或者`高`。


**提示词**
  - 就是大家常说的“预设”，现在，让我们就此打住，这部分内容，我们将会在后面单独一节课或者多节课来讲。


---


<div style="text-align:center">
<img alt="ui" src="assets/img/s01e03/ui_05.png">
<p>API 连接 的 UI界面</p>
</div>

### API 连接

这是第二个按钮，也是 SillyTavern 的 “大脑”。

**API 详细配置**

  - 首先是 `API` 选项，它有以下这些参数，我们分别来说：
    - 文本补全 (Text Completion)： **目前不常用** / 一种比较传统和基础的 API 模式。把所有的对话历史、角色设定等信息打包成一个长长的文本，发送给 AI，然后 AI 在文本的末尾继续写下去，完成“补全”。
    - 聊天补全 (Chat Completion)： **目前主流** / 一种更现代、更强大的API模式，专为对话场景设计。绝大多数兼容 OpenAI API 格式的服务都可以跑。
    - NovelAI：**专业的角色扮演模型** / NovelAI.net ，有兴趣朋友可以尝试。
    - AI Horde：**布式的 AI 计算网络** / 由志愿者贡献出自己的电脑算力，组成一个“部落(Horde)”，免费给其他人提供AI模型推理服务。
    - KoboldAI：**KoboldCPP** / 本地安装(https://github.com/LostRuins/koboldcpp)，可以用它来加载 GGUF，但，我的朋友，你的显卡真的可以吗？**我从来都不推荐普通用户本地跑AI大模型，你的时间非常值钱，我的朋友**

  - 聊天补全来源： 内置了目前主流的 AI 服务商的`官方接口`，在列表里选择你的 API 提供商，然后填入 `KEY` 即可。如果你使用第三方中转或者本地架设了模型，请选择`自定义（兼容 OpenAI）`。

  - 自定义（兼容 OpenAI）：
    - 自定义端点（基础 URL）：API 链接地址，一般都是第三方的网址或你的本地地址。
    - 自定义 API 密钥：你在第三方获取到的 KEY。
    - 输入模型名/可用模型：在你填写正确的地址和 KEY 的情况下，点击底部的`连接`按钮，即可获取到`可用模型`列表，选择即可。如果没有获取到，在你的 API 提供商的网站去查找，然后填写即可。

**提示词后处理**

  这个我们需要单独来说，为了方便理解，我们假设原始的对话历史是这样的（这在某些 API 看来是“不规范的”）：

    ```
    System: 你是法外狂徒张三。
    User: 你好！
    User: 你有蓝火加特林吗？
    Assistant: 当然，我的蓝火加特林可猛了！
    Assistant: 呜！~哒哒哒哒哒！！！！
    ```

  记住上面的例子，然后我们一个一个来看：

  - None (默认)：不做任何特殊处理。SillyTavern 会以它内部的标准格式发送对话历史。大多数现代模型一般都不需要设置，除非你需要配合一些特殊`预设`。

  - NoTools.合并相同角色连续的发言：如果对话中有来自同一角色（比如用户）的连续多条消息，此选项会将它们合并成一条消息。
    ```处理后的效果
    System: 你是法外狂徒张三。
    User: 你好！你有蓝火加特林吗？
    Assistant: 当然，我的蓝火加特林可猛了！呜！~哒哒哒哒哒！！！！
    ```

  - NoTools.半严格: 包含“合并”功能且“强制角色交替”，且整个历史对话中只有一个系统提示词(多条会合并)，它的结构像这样：
    ```
    System > User > Assistant
    ```

  - NoTools.严格：包含“半严格”的所有功能，并且额外强制要求对话必须由用户消息开始（在系统提示词之后）。如果第一条非系统消息是 AI 的，它会自动在前面插入一条占位符用户消息。

    【原始对话】 
    ```
    System: 你是张三。 -> Assistant: 啊哈，我有蓝火加特林！
    ```
    【处理后】
    ```
    System: 你是张三。 -> User: [Start a new chat] -> Assistant: 啊哈，我有蓝火加特林！
    ```

  -  Single user message（notools）：单个用户消息，一般是用于一些上古模型或简单模型。它会把所有的东西全部拼在一起一次性发送给 AI，AI读完给你个回复。

  你肯定注意到了，在这些选项的上面，还有一个 `With Tools` 的大分类和一些选项。
  `with tools`会允许 AI 使用外部工具（例如，查询天气、进行计算、搜索网页）。在对话历史中，这会以一种特殊的格式存在。
  
  我们上面所说的且常用的都是 `No Tools` ，因为绝大多数 API 不支持工具调用，还有一点，支持工具调用的一般都很贵！希望过几个月能便宜些吧。

  > 💡 总结：一般保持 `none` ，特殊预设在说明文件里会建议你更改为什么模式。还有，如果你的连接报错了，看 SillyTavern 给你的报错提示，再去选择对应的模式即可。

**附加参数**

  在这里可以为当前连接的模型单独设置自定义参数，此处的参数优先级最高，可覆盖 **API 响应配置** 中的设置。对于特殊模型来说用处较大。

    - 包括主体参数：可以在这里添加任何 API 所支持的参数，有些参数 SillyTavern 的界面上没有提供相应的滑块或选项。
    - 排除主体参数：从 SillyTavern 默认将要发送的 API 请求主体中 移除 一个或多个参数。
    - 包含请求标头：向 API 请求添加自定义的 HTTP 标头 (Headers)。HTTP 标头是请求元数据的一部分，通常用于传递身份验证信息、路由指令或客户端信息，它不直接控制 AI 的文本生成逻辑。

**API 连接配置**

  最后，让我们回到顶部，在这里你可以将刚刚设置的所有的东西存储为`自定义名称`的预设配置。从左往右分别是 API预设名称、信息、新建预设、保存预设、编辑预设、重载预设（以连接信息重载）、删除预设。


---


<div style="text-align:center">
<img alt="ui" src="assets/img/s01e03/ui_06.png">
<p>高级格式化设置 的 UI界面</p>
</div>


### 高级格式化设置

  首先，这里的大部分东西都是给“文本补全”用的，而不是给“聊天补全”用的，所以我们只说“聊天补全”能用到的地方。

  - 上下文模板：**适用于文本补全**，这里不赘述。

    此处的 IF 判断我单独列了出来，并加了注释，现在不用去管它，后面的知识点会有联动。
    ```
    // 系统提示词 
    {{#if system}} {{system}} {{/if}}

    // 前置世界信息 - 预设 World Info (before) - 位置 World Info (↑Char)
    {{#if wiBefore}} {{wiBefore}} {{/if}}

    // 角色描述 - 预设 Char Description - 位置 Character Description
    {{#if description}} {{description}} {{/if}}

    // 角色性格 - 预设 Char Personality - 位置 Character Personality
    {{#if personality}} {{char}}'s personality: {{personality}} {{/if}}

    // 场景 - 预设 Scenario - 位置 Character Scenario
    {{#if scenario}}Scenario: {{scenario}} {{/if}}

    // 后置世界信息 - 预设  World Info (after) - 位置 World Info (↓Char)
    {{#if wiAfter}} {{wiAfter}} {{/if}}

    // 用户角色 - 预设 Persona Description - 位置 倒数第二个按钮
    {{#if persona}} {{persona}} {{/if}}
    ```

  - 指导模板/系统提示词：**适用于文本补全**，这里不赘述。
  
  - 自定义停止字符串：
    - 自定义 AI 禁词列表，即 AI 在生成回复时，一旦生成了这些内容，就会立刻停止。格式 `["A","B","C",...]` , 可以在 Jsonlint.com 中验证格式是否规范。
    - 注意！如果设置不当，会严重干扰 AI 的正常表达。
      - 比如你写了 `["\n"]` ，那么 AI 永远就只能输出一段话，当它需要换行时就会被 SillyTavern 终止。
      - 比如你写了 `["{{user}}"]` ，当 AI 使用你的名字时就会终止。
      - 我们来看一个更合理、更常见的设置： `["\n{{user}}:", " {{user}}:"]` 
        - AI完成了它作为角色的回复，比如：{{char}}："我明白了，我会按照你的指示去做。"
        - 在理想情况下，AI应该就此结束。但有些模型不够“聪明”，在生成了上面的回复后，它可能会错误地认为“现在轮到用户说话了”，于是它会接着生成： "\n{{user}}:" ，试图模仿你开始新一轮的对话。
        - 此时，"\n{{user}}:" 这个完整的字符串精确匹配了我们设置的停止符 AI 停止生成。
        - SillyTavern 接收到结果，发现结尾是停止符，于是自动把它剪掉。
        - 你最终看到的回复就是干净的："我明白了，我会按照你的指示去做。"

  - 词符化器：
    - 这个就是我们所谓的 AI 分词器
    - 下拉菜单 (Best match): 
      - 选择计算 Token 的方式。Best match (recommended) 会尝试自动匹配最适合当前模型的计算方法，以准确估算上下文长度。
    - Token Padding (词符填充): 
      - 安全缓冲值。如果上下文限制是 4096 个 token，这里设为64，那么 SillyTavern 会在上下文达到 4096-64=4032 个 token 时就开始裁剪旧消息，防止超出限制。

  - 推理：主要用于需要展示“思维链”时使用，勾选自动解析后修改具体标签格式，在此不赘述，

  - 杂项：
    - 非 Markdown 字符串：在这里填写的字符，在发送给AI时会被特殊处理，防止AI将其误解为 Markdown 格式。这是一个后端转义的功能，和你在前端输入的内容没有关联。
      - 在最新版的 SillyTavern 中通过测试，我并没有发现它正在起作用，也可能是我的使用方式有问题？

---


<div style="text-align:center">
<img alt="ui" src="assets/img/s01e03/ui_07.png">
<p>世界/知识书 的 UI界面</p>
</div>


### 世界/知识书

///正在编写


---

<h2 align="center">Part.2 深入后台：了解 config.yaml</h2>

在你成功体验了 SillyTavern 的核心乐趣后，如果你想进行一些界面上无法完成的高级设置，那么是时候了解一下它的“神经中枢”——配置文件了。

最重要的配置文件叫做 `config.yaml`，它位于你的 SillyTavern 安装根目录下。

> **⚠️ 注意：** `config.yaml`会在初次运行时创建，修改任何 `.yaml` 文件时，请使用专业的文本编辑器，如 **VS Code**、**Sublime Text** 等。**不要使用 Windows 自带的记事本**，它可能会破坏文件的格式！

让我们来看几个最常用的配置项：

### 1. 修改访问端口

默认情况下，SillyTavern 运行在 `8000` 端口上。如果这个端口被其他程序占用了，你可以在 `config.yaml` 中找到 `SERVER CONFIGURATION` 分区并修改它。

```yaml
# -- SERVER CONFIGURATION --
# ... (其他设置) ...
# Server port
port: 8000
```
比如，你可以把它改成 `8080` 或其他未被占用的端口。

### 2. 开启局域网共享

想在同一 WiFi 网络下的手机、平板或其他电脑上使用你主机上的 SillyTavern 吗？你需要开启局域网（LAN）共享。找到 `listen` 选项，将 `false` 改为 `true`。

```yaml
# -- SERVER CONFIGURATION --
# Listen for incoming connections
listen: false
```
改为：
```yaml
# Listen for incoming connections
listen: true
```
保存并重启 SillyTavern 后，你就可以在其他设备上，通过 `http://<你电脑的局域网IP>:<端口号>` 来访问了。（例如: `http://192.168.1.101:8000`）

> **💡 进阶提示：** 配置提供了更精细的控制。在 `listen: true` 的下方，你还可以通过 `protocol` 设置来决定是启用 `ipv4` 还是 `ipv6`。对于绝大多数家庭网络环境，默认设置（`ipv4: true`, `ipv6: false`）就是最佳选择，无需改动。

### 3. 设置网络代理

如果你需要通过代理来连接 AI 的 API（例如 OpenAI 或其他海外服务），新版配置提供了专门的 `requestProxy` 区域。这比旧版更加强大。

找到 `REQUEST PROXY CONFIGURATION` 分区。你需要做两步操作：

1.  将 `enabled` 的值从 `false` 改为 `true`。
2.  在 `url` 字段中填入你的代理地址。

例如，一个本地的 HTTP 代理通常是 `http://127.0.0.1:端口号`。修改后的配置如下：

```yaml
# -- REQUEST PROXY CONFIGURATION --
requestProxy:
  # If a proxy is enabled, all outgoing HTTP/HTTPS requests will be routed through it.
  enabled: true
  # Proxy URL. Possible protocols: http, https, socks, socks5, socks4, pac
  url: "http://127.0.0.1:7890" # <-- 在这里填入你的代理地址
  # Proxy bypass list. Requests to these hosts won't be routed through the proxy.
  bypass:
    - localhost
    - 127.0.0.1
```

> **重要提示：** 每当你修改了 `config.yaml` 文件，都必须**关闭 SillyTavern 的命令行窗口并重新运行 `Start.bat`** 才能让改动生效。
