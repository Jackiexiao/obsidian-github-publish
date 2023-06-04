---
alias: [chatgpt-md]
share: true
comments: true
---

# obsidian-chatgpt插件介绍
## 十款插件介绍
https://forum-zh.obsidian.md/t/topic/16422

## 哪款最好用呢?
目前我用的是chatgpt-md

## 教程
> https://github.com/bramses/chatgpt-md

1. 安装插件

首先，你需要在Obsidian中安装chatgpt-md插件。你可以在插件商店中搜索chatgpt-md，然后点击安装。

2. 获取API Key

在使用chatgpt-md之前，你需要先获取一个API Key。你可以在OpenAI的官网上注册一个账号，然后创建一个新的API Key。将API Key复制到剪贴板中。

3. 设置API Key

在Obsidian中，点击插件栏中的chatgpt-md插件，然后点击“Settings”。在API Key一栏中，将你之前复制的API Key粘贴进去。

4. 开始对话

在Obsidian中，打开一个笔记，然后在编辑模式下输入`/chat`命令（有时候`/`前面需要一个空格），聊天机器人会自动回复你的消息。你可以和它进行多轮

另外，你也可以给 `ChatGPT MD:Chat` 绑定一个快捷键，按下快捷键进行对话

5. 如何免科学上晚

添加这个参数，里头的url需要替换成你自己的代理，或者是 azure openai url
```
---
url:  https://gptproxy.lesswrong.cc/proxy
---
```

6. 如何提高最大生成字数
```
---
url:  https://gptproxy.lesswrong.cc/proxy
max_tokens: 1024
---
```
7. 完整的参数列表
```
---
system_commands: ['I am a helpful assistant.']
temperature: 0
top_p: 1
max_tokens: 512
presence_penalty: 1
frequency_penalty: 1
stream: true
stop: null
n: 1
model: gpt-3.5-turbo
url: null
---
```

