
---
alias: [obsidian publish]
share: true
---

# obsidian-github-publisher
总的来说比较好用，用了 mkdocs 这个库来发布
https://github.com/ObsidianPublisher/obsidian-github-publisher

## 我推荐的使用方法
最简单的方法还是通过 netlify 部署

1. 点击[官方文档](https://obsidian-publisher.netlify.app/)中的 netlify deploy <a href="https://app.netlify.com/start/deploy?repository=https://github.com/ObsidianPublisher/publisher-template-netlify"><img src="https://www.netlify.com/img/deploy/button.svg"></a>，会得到一个网站，就是你未来的博客地址，对应生成了一个 github repo
2. 在obsidian中安装 github publisher 插件
3. 在插件 options 中设置一下内容
    1. github configuration > 填写所有信息，包括[token](https://github.com/settings/tokens) 仓库名等，仓库名就是前面 netlify deploy生成的
    2. upload configuration: 建议设置`obsidian path`，而不是`fix path` 这样发布文章后，文件夹结构跟本地的相同
    3. content's conversion: 有时候我们想隐藏私密内容，方法是在text replacer 中添加 `/` 中的内容
    ![[Pasted image 20230322202613.png]]
4. 想要发布的文章的开头添加
```
---
share: true
---
```
5. 执行指令（`ctrl + P`）输入 `publish` ，发布你的文章，提示发布成功后，等十几秒，文章就上传到上述的博客地址中了。
6. 回到第一步生成的 github repo，修改里头的 `mkdocs.yaml` 以便添加你的网站名

## 我提的PR
https://github.com/ObsidianPublisher/publisher-template-netlify/pull/2

- [ ] jieba 未添加，中文搜索不友好
- [ ] vercel 作者不愿意merge

## 当前问题
- 教程的问题: 实在过于简略，没有图文.... 最好有个 youtube 视频教程
- 中文搜索不友好



# 其他项目
> 2023-3-22 不过不太好用
https://github.com/yoursamlan/pubsidian

