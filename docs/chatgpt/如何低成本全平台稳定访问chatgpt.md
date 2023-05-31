---
share: true
---

> [!info] 如果你就是普通用户想免费白嫖，建议看每日更新的国内可用chatgpt网站: https://lzw.me/x/chatgpt-sites/

[[程序员用ai]]

## TL'DR 太长不看版

- 小白用户
    - 白嫖用户点击: [[#如何免费白嫖]]
    - 愿意付费用户点击 : [[#付费网站推荐]]
- 愿意花点时间折腾的性价比用户点击 [[#如何获取apikey]]
- 高阶能翻墙，能注册海外信用卡用户: 你不用我教 哈哈哈哈哈

## 如何稳定地免费白嫖

- 现在很多付费网站每天都有免费额度，额度到了，换下一个付费网站继续白嫖[Doge]
- 推荐 chatgpt-sidebar chrome 插件，每天30条免费查询额度

# 低成本全平台稳定访问chatgpt

这篇文章介绍了如何便宜、稳定、不需要翻墙的获取 chatgpt 的服务: 主要通过 apikey 的方式，以及如何在电脑、手机、浏览器、输入法等多个设备中访问 chatgpt

## 为什么选择api key
- 优点
    - openai官网访问需要科学上网，而且每次都需要验证，服务有时不稳定
    - apikey 是一个`sk-`开头的字符串，用于访问chatgpt服务，openai每个账户都可以通过后台得到
    - apikey 很容易在网上买到（淘宝或者百度/google搜索），失效后重新买一个就行，这个过程并不需要你科学上网
    - apikey 按量计费，总的来说很便宜: **$0.002/1k tokens**，输出100万个单词，大约18块人民币
    - 有众多支持 apikey 的网站和APP: [支持Api Key 的海量应用-github](https://github.com/reorx/awesome-chatgpt-api/blob/master/README.cn.md)
- 缺点
    - 必须在同1个IP内使用，例如：您在自己的服务器搭建使用API接口的网站或应用，其它人访问您部署的服务，这种是没有问题的，不会被封号。
        - ⚠️警告：如果您将自己的API-Key遍地开花的给很多个IP同时使用，那么必被封号
    - 一般撸羊毛得到的apikey都有 rate limit 也就是速率限制，一般是每分钟只能发3个请求，除非你的apikey是真的向官方付费的
    - 之前OpenAI 的免费密钥，一旦遇到压力大，就不稳定，基本不可用。

## 如何获取apikey
有很多种方案，具体选择取决于你的实际需求

- 如果你有魔法能力: 到官网注册账户获取apikey
    - 正规不被封锁渠道: 有国外手机号码+国外信用卡自己到openai官网注册一个，对大多数人来讲很难，但这个也是最最稳定、能长期使用的方法，或者自己通过国外短信接码平台注册新账号，能获得5美元的apikey账号，便宜但稍麻烦
- 如果你更侧重稳定，且没有海外信用卡，没有魔法   
    - 推荐: https://api2d.com/
    - 通过它获取 apikey 以及 api 代理网站!! 费用是openai官方的1.5倍，也就是约$0.003/1k tokens, 21元能聊一万句（没有上下文的情况下）
- 如果你更侧重性价比（省钱）且有魔法: 买 apikey
    - google 搜索: 购买 apikey，但必须说明，这些 apikey 随时有被封的危险
        - https://eylink.cn/buy/4  （现在可能不能用了，网上随便找找吧）
            - 优点: 很便宜，3.6元一个5美元账户
            - 缺点: 很容易被封，程序注册得到的 openai 账号（质保1小时），另外一分钟只能调用3次，如果你是写代码的，不要买这个，普通用户可以
        - https://openaikey.xyz/ 
            - 优点: 相对靠谱，手工注册的账户，有250美元apikey出售
            - 缺点: 贵，质保1天
    - 目前我知道最便宜的（如果有更便宜的记得分享给我） 120美元账户-60元: https://www.51chatgpt.info/buy/3 ， 写代码的推荐这个，速率限制比较少
    
![[32e2e572758ebec62f78d09c691965b.jpg|500]]
- 5美元账户 3RPM 这里就是1分钟调用3次，写程序开个多线程就gg
- 120美元账户就是 `Pay -as you go users`

- 如果你是创业公司: [[申请openai的创业公司2500美元服务]]?

## 如何使用apikey并免科学上网
使用apikey很简单，就是在 支持apikey的软件中填入 apikey 就可以了，注意不要泄露给别人。

> [!info] 如果你能科学上网，下面的部分不需要阅读

如何免科学上网呢? 众所周知，访问chatgpt的api访问的是这个地址 https://api.openai.com 但是它被双向墙了..

那么需要搭建一个代理 来代替 api.openai.com， 你可以采用这个项目搭建: https://github.com/imyuanx/chatgpt-proxy

我这里提供了一个现成的代理网址，你不需要自己搭建（ps: 如果人多的话它很可能就无法访问了，无法预知它何时失效）
https://gptproxy.lesswrong.cc/proxy

为什么这个代理很多人用时有可能失效?
- 因为openai正在严打滥用API的行为，如果同一个IP（上述的公共代理），与其它免费APIKey 同时期发出了大量的请求，那它很有可能会封禁该 IP
- 此外，IP也有速率限制

%%  这个作者提供的服务: https://github.com/beidongjiedeguang/openai-forward https://caloi.top %%

%% 我用 小号 realjackiegeek 在vercel 上 部署，避免被 vercel 禁止账户... %%

那么如何配置呢?

以 chatgpt sidebar chrome插件为例（下文有介绍）在设置->通用配置 中如图填写

![[Pasted image 20230419205854.png|400]]


以 opencat 软件为例，在设置->apikey -> 自定义API域名中填写，记得勾选发送 API key
或者看教程: https://www.bilibili.com/video/BV1pV4y1f7A6

![[Pasted image 20230419204414.png|300]]

# 使用apikey

## 网站
- 输入你的 apikey 后可以使用，不用担心泄露
    - https://www.chatbotui.com/ 网站左下角输入 apikey
    - https://www.typingmind.com/ 
- [自己部署一个chatgpt 网站](https://github.com/Yidadaa/ChatGPT-Next-Web) 设置自己的apikey就能用，还能分享给自己的朋友，[搭建教程](https://www.youtube.com/watch?v=fuoAnkuDEsc)。 [类似的其他项目](https://github.com/Chanzhaoyu/chatgpt-web/issues/1161)

## 手机APP
- opencat: 支持apikey，能[集成到输入法里头!!](https://twitter.com/waylybaye/status/1647561195870900224?s=20) #ios
- 免费的Android版ChatGPT API聊天客户端：Bot郡
- 懂王（跟 chatgpt sidebar 同一家出品）
- charming， chatgpt 接入 siri （指令是 `嘿，siri，莫斯请回答`）

## chrome插件
- 能帮助你在浏览器中快速的使用 chatgpt 而不需要频繁的登录，或者拷贝，此外，还有优秀的UI 和点击即可用的功能
- chatgpt sidebar（==推荐==，每次搜索都给出 chatgpt 回答）
    - google 搜索给出侧边栏答案
    - 快捷键: `ctrl + p`
    - 可以代替 openai translator （因为也支持了划线功能）
    - 选中文本提供给 chatgpt
    - 每天30个免费（除非付费）或者自己设置一下 apikey
- merlin / monica 跟 chatgpt sidebar 基本一样，但不支持自定义apikey

## 电脑端
- utools #推荐 需要安装一个chatgpt的插件，填入 apikey，然后 `Alt+空格` 弹出界面 `chat/ai` 进入chatgpt聊天框

![[Pasted image 20230419171806.png]]

- mac-only : opencat #推荐
- openai-translator 
- [nofwl](https://github.com/lencx/nofwl)  #mac #pc

## 还有非常多支持 apikey 的工具
- [一键总结B站/youtube视频](https://b.jimmylv.cn/)
- openai translator: 翻译插件，支持 chrome / mac / windows / linux
- [使用ChatGPT搭建微信聊天机器人，基于GPT3.5 API和itchat实现](https://github.com/zhayujie/chatgpt-on-wechat)

## 写代码

先export环境变量，可以吧 API_BASE 换成上面的 https://gptproxy.lesswrong.cc/proxy/v1 （下面的apikey已失效[Doge]）
```
export OPENAI_API_KEY=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 
export OPENAI_API_BASE=https://gptproxy.lesswrong.cc/proxy/v1 
export OPENAI_ORGANIZATION=""
```

> https://platform.openai.com/docs/guides/chat/introduction

```python
# Note: you need to be using OpenAI Python v0.27.0 for the code below to work
import openai

response = openai.ChatCompletion.create(
  model="gpt-3.5-turbo",
  messages=[
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "Who won the world series in 2020?"},
        {"role": "assistant", "content": "The Los Angeles Dodgers won the World Series in 2020."},
        {"role": "user", "content": "Where was it played?"}
    ]
)

print(response)
```

# 如何访问gpt4
- chatgpt plus 账户（众所周知，很麻烦...） 一般让淘宝帮忙充值了
- [ ] poe: but `Subscriptions are currently unavailable in your region`

# 其他推荐
- 如果你能科学上网，免费使用的方案
    - Poe.com : 一款**免费**的 chatgpt 类整合引擎 #ios #科学上网
- 如果你愿意付费，倾向稳定服务
    - notion （集成了AI，是真的好用的写作工具）
    - aski.ai  
    - hayo
    - http://askchat.ai/
    - 或者应用商店搜索一下，一大把

# ps
如何注册chatgpt可用的海外信用卡
https://blog.aiservices.tech/12.html

https://compose.ai
类似 notion，但是在所有网页中
用 `//` 得到一个 AI prompt ，就可以继续

### 官网访问的频繁刷新问题解决方法
https://m.okjike.com/originalPosts/644257a3094426a059596806?s=eyJ1IjoiNTY3YTUwZDQ2ZWY4OWMxMjAwOGE3NTc1IiwiZCI6MX0%3D&utm_source=wechat_session