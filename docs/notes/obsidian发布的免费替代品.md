
---
alias: [obsidian publish]
dg-publish: true
share: true
---

# 前言
obsidian官方的发布 16美刀/月还是太贵了... 而且也没办法私有化部署，现在网上也有很多obsidian免费发布的教程，但下面两个我觉得是最好的，它们都提供了 obsidian 插件，容易上手，可以只发布指定的文章，

# digitalgarden-推荐

- [官方文档](https://dg-docs.ole.dev/)
- [B站视频教程](https://www.bilibili.com/video/BV13V4y1c76b) : 推荐

- 下面是两者生成的博客对比
    - [digital-garden](https://digitalgarden-lime.vercel.app/)
    - [github-publish](https://obsidian-github-publish.vercel.app)

- 优点
    - 比 [[#obsidian-github-publisher]] 多了很多可选项和配置主题
    - 支持非常多[特性](https://dg-docs.ole.dev/features/)
- 缺点
    - 是还不支持中文搜索，见[issue](https://github.com/oleeskild/obsidian-digital-garden/issues/219)

# obsidian-github-publisher
最终你可以得到跟[官方文档](https://obsidian-publisher.netlify.app/)类似的网站

它的亮点
- 支持obsidian众多基础语法
- 将你发布的笔记复制到一个新的github仓库并通过 netlify 或者 github page变成网站! （不会修改你本地的文件）
- 通过在meta中设置`share: true`来指定哪些文件要公开，然后通过指令`upload`上传并发布文件
- 相比其他免费发布方案，这个用起来最顺手! 而且设置非常简单!

## 具体教程

最简单的方法还是通过 netlify 部署
1. 点击[官方文档](https://obsidian-publisher.netlify.app/)中的 netlify deploy <a href="https://app.netlify.com/start/deploy?repository=https://github.com/ObsidianPublisher/publisher-template-netlify"><img src="https://www.netlify.com/img/deploy/button.svg"></a>，会得到一个网站，就是你未来的博客地址，对应生成了一个 github repo
2. 在obsidian中安装 github publisher 插件
3. 在插件 options 中设置一下内容
    1. github configuration > 填写所有信息，包括[token](https://github.com/settings/tokens) 仓库名等，仓库名就是前面 netlify deploy生成的
    2. upload configuration: 建议设置`obsidian path`，而不是`fix path` 这样发布文章后，文件夹结构跟本地的相同，本地的内容建议放在根目录的 docs 下
    3. content's conversion: 有时候我们想隐藏私密内容，方法是在text replacer中如图添加一个替换的正则表达式 ，另一边设置为空。这样就不会泄露注释中的内容

![[Pasted image 20230322202613.png]]
4. 想要发布的文章的开头添加
```
---
share: true
---
```
5. 执行指令（`ctrl + P`）输入 `publish` ，发布你的文章，提示发布成功后，等十几秒，文章就上传到上述的博客地址中了。
6. 回到第一步生成的 github repo，修改里头的 `mkdocs.yaml` 以便添加你的网站名

比如我修改后是这个样子（extra social 可以添加你的社交招呼，你可以根据自己的需要修改）
```
site_name: jackiexiao's blog
site_description: jackiexiao's blog
site_url: https://blog.jackiexiao.com
extra:
  social:
    - icon: fontawesome/brands/twitter
      link: https://twitter.com/realjackiexiao
    - icon: fontawesome/brands/github
      link: https://github.com/jackiexiao
    - icon: fontawesome/brands/zhihu
      link: https://www.zhihu.com/people/realjackiexiao
```

## 我提的PR
https://github.com/ObsidianPublisher/publisher-template-netlify/pull/2

- [ ] jieba 未添加，中文搜索不友好
- [ ] vercel 作者不愿意支持，不过netlify也足够用了

## 当前问题 Known issue
- 教程的问题: 实在过于简略，没有图文.... 最好有个 youtube 视频教程
- 中文搜索不友好，即便加了`jieba`

## 支持的obsidian语法
> 目前只支持部分 obsidian 语法，下面展示了展示了常见的情况

#### 脚注
引用文献[^1]  预览之后你可以看到效果

[^1]: 这是一个文献

```
引用文献[^1]， 你也可以[^长脚注]

[^1]: 这是一个文献，注意这里有一个冒号

```
#### admonition / callouts
https://help.obsidian.md/How+to/Use+callouts

```
> [!info]
```

> [!INFO] 这是标题
> Here's a callout block.
> It supports **markdown** and [[Internal link|wikilinks]].

### 高亮
```
==高亮文字==
```

内容==高亮文字==内容
