---
alias: [obsidian publish]
share: true
comments: true
---
# obsidian发布的免费替代品

# 前言
obsidian官方的发布 8美刀/月还是太贵了... 而且也没办法私有化部署，现在网上也有很多obsidian免费发布的教程，但下面两个我觉得是最好的，它们都提供了 obsidian 插件，容易上手，可以只发布指定的文章，

# tldr
当前我的选择： 
- obsidian-github-publisher

why
- SEO
- mkdocs 我比较熟悉，可以自定义
- 安装插件很容易，发布文章也很容易（share:true，然后运行一个 Publish的指令就行）

这个方法实际上存在一堆问题, 见 [[#已知问题 Known issue]]
- 可以通过在 仓库首页 `github.com/[yourname]/[your_repo]` 把 .com 换成 .dev 的方式维护 repo，比如手动删除文章然后 commit
- 文章只要能发布就行，要求不高 lol
- 考虑到发布的时候经常有各种效果问题，建议你手动把项目下载下来，在本地`mkdocs serve`调试成你想要的博客效果
- 养成习惯，自己设置标题（mkdocs 不会自动把文件名当作标题）为了一致性，你可以把 obsidian - apperance - inline title 给关闭掉
- 标题的最好方式： 永远只有一个 header 1 ，而且那个 header 1 就是标题/ 文件名，其他都是 header2 起步。这样就可以关闭在 mkdocs 中关闭 "fix_header"
- todo 不知道为什么显示了两次title，不过 whatever 不管了，可能跟 heading 有关

没有采用单独为博客新建个本地仓库的原因
- 附件照片需要自己手动复制
- 需要手动维护两个仓库


ps: 我要使用 mkdocs-material 带的评论功能需要在 meta 中加上 `comments: true
`

# 官方发布的优缺点
一个使用官方发布的仓库: https://publish.obsidian.md/chinesehelp/

更新时间: 2023-4-23

- 优点
   - 完全兼容 obsidian 的语法
   - 使用起来非常方便
   - SEO
   - 支持各种自定义主题
- 缺点
    - 很贵，8美刀/月
    - 只能搜索 page + heading，无法全文搜索
    - 没有评论功能

# digitalgarden-推荐

- [官方文档](https://dg-docs.ole.dev/)
- [官方github仓库](https://github.com/oleeskild/obsidian-digital-garden)
- [B站视频教程](https://www.bilibili.com/video/BV13V4y1c76b) : 推荐

- 下面是两者生成的博客对比
    - [digital-garden](https://digitalgarden-lime.vercel.app/)
    - [github-publish](https://obsidian-github-publish.vercel.app)

## 1 优点
- 比 [[#obsidian-github-publisher]] 多了很多可选项和配置主题
- 支持非常多[特性](https://dg-docs.ole.dev/features/)
- 基本支持obsidian全部语法，甚至 `%% %%` 注释的内容也会删除

## 2 使用注意点
- 对于中文，应该关闭设置中的 `Slugify Note URL` 因为它会删除中文字符，见 [doc](https://dg-docs.ole.dev/getting-started/05-other-settings/#slugify-note-url)

## 3 已知问题 Known issue
- [ ] 博客网站的问题-seo没有做好，另外没办法加入评论功能，没评论，就没动力
- [ ] 不支持中文搜索 [讨论见 issue](https://github.com/oleeskild/obsidian-digital-garden/issues/219)
- [ ] 纯链接例如: https://baidu.com 会被解析为纯文本而不是 链接
- [ ] 左侧目录无法默认展开（不过这是个小问题）
- [ ] 对`[[#标题]]`的解析存在一些问题
- [ ] SEO 做的不太好，google 基本搜索不到
- [ ] 一次性更新一百个文件会生成100个commit，不过 vercel 只会大概 build 几次（不会build 一百次）见 [issue](https://github.com/oleeskild/obsidian-digital-garden/issues/211)
- [ ] 网站字体偏大，多层级文件夹需要自己手动展开
- [ ] 没有评论功能

# obsidian-github-publisher
https://github.com/ObsidianPublisher/obsidian-github-publisher

最终你可以得到跟[官方文档](https://obsidian-publisher.netlify.app/)类似的网站

它的亮点
- 支持obsidian众多基础语法
- 将你发布的笔记复制到一个新的github仓库并通过 netlify 或者 github page变成网站! （不会修改你本地的文件）
- 通过在meta中设置`share: true`来指定哪些文件要公开，然后通过指令`upload`上传并发布文件

## 1 优点
- 基于 python + mkdocs，你可以方便的自定义
- 静态网站，SEO友好

## 2 已知问题 Known issue
- [ ] 不支持中文搜索，作者拒绝 vercel + jieba 的 [PR](https://github.com/ObsidianPublisher/publisher-template-netlify/pull/2) ==你需要采用我的模板==
- [ ] 如果含有header1会被错误解析（第一个标题会被当作页面的标题 orz），这个可能是 fix_heading 带来的问题，见： https://obsidian-publisher.netlify.app/template/configuration/#hooks
- [ ] vercel 每天只能build100次
- [ ] 不支持 obsidian 的很多语法（可以在我的 roam link 中修改并支持，或者改进那个作者的库）
    - [ ] 不支持图片尺寸语法 如`[[image.png|200]]`
    - [ ] 不支持高亮语法
- [ ] 官方教程写的不太好，使用 chatgpt i18n 给她自动做翻译
- [ ] 实际使用过程中总有各种bug.... 例如无法删除已发布的内容... 例如文件夹改变之后，文章地址并没有跟着变，而是多了一个副本....
- [ ] mkdocs 默认模板并不太好看

## 3 具体教程

最简单的方法还是通过 netlify 部署
1. 点击[官方文档](https://obsidian-publisher.netlify.app/)中的 netlify deploy <a href="https://app.netlify.com/start/deploy?repository=https://github.com/ObsidianPublisher/publisher-template-netlify"><img src="https://www.netlify.com/img/deploy/button.svg"></a>，会得到一个网站，就是你未来的博客地址，对应生成了一个 github repo
2. 在obsidian中安装 github publisher 插件
3. 在插件 options 中设置一下内容
    1. github configuration > 填写所有信息，包括[token](https://github.com/settings/tokens) 仓库名等，仓库名就是前面 netlify deploy生成的
    2. upload configuration: 建议设置`obsidian path`，而不是`fix path` 这样发布文章后，文件夹结构跟本地的相同，本地的内容建议放在根目录的 docs 下
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


# 其他
如果不想折腾，真的，弄个 wordpress 站点就挺好的....