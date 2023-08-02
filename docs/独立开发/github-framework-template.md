---
alias: [template, scaffold, 仓库模板, 模板购买, buy-template, Boilerplates]
share: true
comments: true
---
# github-framework-template
[[awesome]]
[[awesome-indie-tools-独立开发者工具|独立开发者工具]]

# graph
[[codecov]]

# todo
有没有 awesome template 或者 scaffold


# 购买模板的网站
https://themeforest.net/
https://www.templatemonster.com/


# 按场景分类
## 1 github通用
- [README-generator](https://github.com/kefranabg/readme-md-generator)
- [gitignore 查询模板](https://www.toptal.com/developers/gitignore)
- [gitattributes模板集](https://github.com/alexkaratarakis/gitattributes)

## 2 搭建文档网站
https://docusaurus.io/docs (这里做了一堆文档类开源工具的比较， docusaurus 相比 mkdocs 的好处在于支持更好的搜索，以及 React） 另外多了版本号跟语种（这个mkdocs也许可以设置）

## 3 小程序

# 按语言分类
## 1 javascript
### 模板网站
https://www.creative-tim.com/
https://vercel.com/templates/next.js
https://tailwindui.com/templates (比较贵99美元）
mui store material-ui 也有一些付费模板（支持多语种，light/dark mode 等等超级多高级功能，买这些就很方便）

### 模板生成
> 根据你的需求生成项目的脚手架 

- [superplate类似refine，似乎更好用一点](https://github.com/pankod/superplate) ==推荐== 可以看到现在很多最佳实践
- [refine: 根据你的需求生成各类react框架+ui+crud模板 11k stars](https://refine.dev/) 非常适合作为项目通用脚手架

### nextjs
- [nextjs最佳实践的模板3.2k stars](https://github.com/steven-tey/precedent): auth/prisma orm/tailwindcss radix
- [nextjs+electron 2.2k stars](https://github.com/saltyshiomix/nextron)
- [nextjs企业级模板3.4k stars](https://github.com/Blazity/next-enterprise)
- [完整的pwa支持示例-包含教程](https://github.com/shadowwalker/next-pwa)
- **推荐** mui+i18n  https://github.com/SimonsMeldzers/inin-estate
    
#### 初学者模板
- [非常简单的多语种+pwa+mui项目-100stars](https://github.com/kiri-art/stable-diffusion-react-nextjs-mui-pwa)
- [nextjs官方极简pwa](https://github.com/vercel/next.js/tree/canary/examples/progressive-web-app)
- [pwa+mui的极简todolist](https://github.com/ooade/NextSimpleStarter)
- [mui官方提供的nextjs 简单template](https://github.com/mui/material-ui/tree/master/examples/material-next-ts)

#### 博客模板
https://statichunt.com/themes/nextjs-hydrogen

#### 其他
[电商网站+nextjs](https://github.com/sadmann7/skateshop)
- https://github.com/kiri-art/stable-diffusion-react-nextjs-mui-pwa
- https://github.com/HPouyanmehr/theBag 
-  https://github.com/hiriski/coursespace-landing-page

## 2 python
- https://github.com/rochacbruno/python-project-template
- https://github.com/waynerv/cookiecutter-pypackage
    - 对应的[说明文章](https://www.waynerv.com/posts/ultimate-python-open-source-project-template/)
    - 是在这个[项目](https://github.com/audreyfeldroy/cookiecutter-pypackage)上的"改进"版本
- https://github.com/pyscaffold/pyscaffold  这个看起来 star 最多
- https://github.com/eugeneyan/python-collab-template

### 2.1 fastapi
- https://github.com/twocucao/tifa
- https://github.com/rochacbruno/fastapi-project-template


### 2.2 django
https://github.com/SinghShreyansh/BlogWeb-React-Django
https://github.com/tech-jamara/DjangoReactPortfolio
+vercel
https://vercel.com/templates/python/django-hello-world

+react+websocket+chat-app
https://justdjango.com/blog/chat-app-django-channels

## 3 go
- [go-练手开源项目](go-练手开源项目.md) 这个也很适合
- 基础的项目模板，建议所有 go 项目在此基础上开发
- [https://github.com/golang-standards/project-layout](https://github.com/golang-standards/project-layout)
- 这个还有中文的 [README](https://github.com/golang-standards/project-layout/blob/master/README_zh.md) 厉害了
- [https://github.com/golang-templates/seed](https://github.com/golang-templates/seed)
- [go-podinfo](go-podinfo.md): mini的Go微服务模板 很值得借鉴
- 更多的模板可以在这里找到
- [https://github.com/yinggaozhen/awesome-go-cn#%E9%A1%B9%E7%9B%AE%E5%B8%83%E5%B1%80](https://github.com/yinggaozhen/awesome-go-cn#%E9%A1%B9%E7%9B%AE%E5%B8%83%E5%B1%80)

## 4 cpp
- 哪个文档多到时就看哪个
- [GitHub - filipdutescu/modern-cpp-template: A template for modern C++ projects using CMake, Clang-Format, CI, unit testing and more, with support for downstream inclusion.](https://github.com/filipdutescu/modern-cpp-template) 
    - 1.1k star
- [GitHub - TheLartians/ModernCppStarter: 🚀 Kick-start your C++! A template for modern C++ projects using CMake, CI, code coverage, clang-format, reproducible dependency management and much more.](https://github.com/TheLartians/ModernCppStarter)
    - 3k star 
    - 推荐从这个看起
- [GitHub - cpp-best-practices/gui_starter_template: A template CMake project to get you started with C++ and tooling](https://github.com/cpp-best-practices/gui_starter_template/)
    - 2.1k star
- 推荐阅读
    - [GitHub - rigtorp/awesome-modern-cpp: A collection of resources on modern C++](https://github.com/rigtorp/awesome-modern-cpp) 
- [GitHub - xyz1001/cppiniter: 初始化一个C++项目](https://github.com/xyz1001/cppiniter)
    - 一个很简单的脚手架
- javascript / typescript
- [https://github.com/zce/caz](https://github.com/zce/caz) 

## 5 python + cpp + pybind11
- [GitHub - pybind/cmake_example: Example pybind11 module built with a CMake-based build system](https://github.com/pybind/cmake_example) 
- [GitHub - mapbox/python-cpp-skel: Skeleton for bindings to C++ libraries for Python using pybind11](https://github.com/mapbox/python-cpp-skel) 
