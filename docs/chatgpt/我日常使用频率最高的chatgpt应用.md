---
share: true
comments: true
---
# 我日常使用频率最高的chatgpt应用

我已经连续使用 Chatgpt 好几个月了，尝试过非常多的 Chatgpt 应用，但大部分应用在国内使用起来真的很困难（说的就是你，openai官网），很多套壳应用因为不符合我的习惯，后面都淘汰了。最后只留下几款我使用频率最高，最爱不释手的应用推荐给大家。

## 说明
下面的软件几乎都有两种可能的使用方式
- 付费：它们都有提供付费方案
- apikey：使用你自己的 openai apikey + 魔法网络，这是我采用的方案，见[[如何低成本全平台稳定访问chatgpt]]，不同软件的apikey和代理设置方式不同，具体看它们的文档

## chatgpt-sidebar: chrome浏览器插件
下载chrome插件： https://chrome.google.com/webstore/detail/sider-chatgpt-sidebar-gpt/difoiogjjojoaoomphldepapgpbgkhkb

最佳的浏览器chatgpt插件！！我使用频率最高的应用！！

你可以选中网页上的任何文本，让它帮你解释 / 翻译 / 润色 !! 这对于学习新知识超级有用

![[chatgpt-sidebar-hign 1.gif]]

你还可以在任何网页`Ctrl + P`打开侧边栏继续跟 chatgpt 聊天，让它继续解释刚才的概念

![[Pasted image 20230603104657.png]]

## Raycast / Utools 的 chatgpt 插件

[Raycast](https://www.raycast.com/) 和 [Utools](https://www.u.tools/) 分别是 MacOS 和 window 的超级效率工具，一键呼出输入框，在输入框中几乎可以做任何电脑操作。

在安装它们的 chatgpt 插件之后，你就可以在你的电脑中随时随地一键呼叫 chatgpt ，提任何问题，这个用起来真的超级方便。下面的 Gif 图展示的是 MacOs 上 raycast 的 chatgpt 插件 

![[raycast-chatgpt-more.gif]]

## Copilot chat
这绝对是近期最棒的AI代码生成工具！！生成的代码质量很高，实测明显优于chatgpt！！

我让它帮我生成了一个python贪吃蛇游戏，几十秒就生成了可运行，无bug的代码，还有代码说明。你还可以选中任意代码，让它帮你解释/找bug/生成测试代码。

![[Pasted image 20230531215430.png]]

加入 waitlist: https://github.com/github-copilot/chat_waitlist_signup/join

目前它要加入 waitlist 之后才可以使用，如果你等不及在 vscode 上使用了，可以考虑 [vscode genie](https://marketplace.visualstudio.com/items?itemName=genieai.chatgpt-vscode) 插件，提供你的 apikey 或者付费，就可以在 vscode 中愉快的使用 chatgpt 写代码了

## ChatGPT-Next-Web
https://github.com/Yidadaa/ChatGPT-Next-Web

一键免费部署你的私人 ChatGPT 网页应用！！当然前提是你有 apikey，有 vercel 帐号，会买域名，这个操作起来有一点门槛。

这个项目是我分享给朋友使用 chatgpt 的主要方式，部署之后，你就可以把你的网站分享给朋友啦，电脑手机端都可以用，由于它支持PWA，你甚至可以安装到电脑，或者在安卓&ios上添加到手机桌面，方便以后使用。

![[Pasted image 20230531231019.png]]

ps: 我在手机端使用最顺畅的还是 bing ，因为它可以直接语音交互，当然目前使用bing绕过重重障碍很困难....∏


## 其他推荐-来自网友
### chathub-跟多个LLM同时对话
为什么同时要跟几个人工智能对话？

ChatHub 能在一个窗口里同时操作几个 LLM 聊天机器人，一条指令、多条回复，支持 ChatGPT、Claude、Bing、Bard 和我不认识的 LLM😂

https://chathub.gg

我本来没想清楚这个工具的使用场景，我又不是 AI 器材派，除了测试 AI 性能、似乎也用不上这个工具。后来真的测试一段时间后，发现两个使用场景：

- 利用多重结果：ChatGPT 和 Claude 们输出的结果不同，在发散性的问题上，ChatHub 能帮我得到更多结果；而在确定性的问题上，几个结果能帮我互相验证输出质量
- 一次操作输出多组结果：这个操作目前实现不了，如果我打开两个 ChatGPT 窗口提问、工具会返回两个一模一样的结果。希望以后能支持串联使用多个 ChatGPT，方便我一次输入、输出多组结果，这在头脑风暴之类发散性问题上又能节约时间

多窗口的 LLM 聊天机器人应该还有很多其他使用场景，就等用户们不断发明创造吧

另外得特地表扬一下：ChatHub 的 UI 设计大方得体也还挺好看，在我测试的来自独立开发者的工具/产品里排名第二