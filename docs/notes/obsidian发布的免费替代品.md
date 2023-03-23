
---
alias: [obsidian publish]
dg-publish: true
share: true
---

` 中的内容

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
