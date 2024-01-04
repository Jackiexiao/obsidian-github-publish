---
aliases:
  - nuxt
share: true
---
# vue
## graph
[[react还是vue]]
[[尚硅谷]]
## 我选择的技术栈

- 语言： typescript
- 前端框架： vue3
- 编译打包： vite
- 全栈 / SSR 服务器渲染网页 / SSG 静态网站生成： nuxt 3 
    - 不过好像 gennia 并不需要 服务器来渲染网页，直接让客户端自己弄就行
    - 这样的话，可以避免部署一个前端网站还需要后台部署个 node js
- UI: daisyUI + tailwindcss + nuxt UI  (nuxtUI 是基于 tailwindcss 的）
    - https://www.antdv.com/components/overview-cn
- 文档: vitepress
- 数据库： postgresql
- [[ORM]](Object-Relational Mapping)： prisma
- 错误报告： Sentry （有没有国内的）[vue接入sentry](https://cn.vuejs.org/guide/best-practices/production-deployment.html#tracking-runtime-errors)
- [ ] zod复用前后端的校验?
- [ ] 部署: Docker  /  vercel 
- 状态管理库： Pinia 符合直觉的 vue.js 状态管理库 （vuex 替代品， 类似 redux）
- awesome合集： 
    - https://github.com/vuejs/awesome-vue
    - https://github.com/nuxt/awesome
- 告警： sweetalert2
- [ ] vue资讯： ？
- [ ] 前后端连接？ axios 还是 tRPC 还是？
- [ ] [[#template]] : 
    - 官方的 https://nuxt.new/
    - https://github.com/viandwi24/nuxt3-awesome-starter
    - nuxt + daisyUI https://github.com/OSSPhilippines/nuxtwind-daisy
- 测试： 使用 [Vitest](https://github.com/vitest-dev/vitest) 进行单元测试, [Cypress](https://cypress.io/) 进行 E2E 测试
- 小程序： uniApp
- 配合 [Electron](https://www.electronjs.org/) 或 [Tauri](https://tauri.studio/en/) 构建桌面应用
- 配合 [Ionic Vue](https://ionicframework.com/docs/vue/overview) 构建移动端应用
    - 感觉官方没有推荐这几个了? Capacitor /  NativeScript / UniApp
- 使用 [Quasar](https://quasar.dev/) 用同一套代码同时开发桌面端和移动端应用
- 资讯：
    - [vue周报](https://www.bilibili.com/video/BV1Vg4y1r7si/)
## tutorial
- nuxt 3 + vue3 + vite  daisyUI  + tailwindcss 的中文官网
- [vue视频教程](https://www.bilibili.com/video/BV1Za4y1r7KE/) ， [[vue3视频配套笔记]] [[vue3-simple精简笔记]]
    - 2024-01-02 元旦假期快速看了一遍（基本看完，只剩几个小节）
- nuxt3 视频教程 （如果不需要 服务端渲染，完全可以不用 nuxt!!）
    - 两个小时的[crash Course](https://www.bilibili.com/video/BV1Fw411N771) 推荐
        - github.com/iamshaunjp/nuxt-3-tutorial
    - [tiktok clone](https://www.bilibili.com/video/BV14M411575a)  英文视频
    - [bilibili clone](https://www.bilibili.com/video/BV1u84y1R7d1) 黑马程序员的
- [学习路线图](https://roadmap.sh/vue)
- [awesome-vue](https://github.com/vuejs/awesome-vue)
- [尚硅谷：2023版前端学习路线图](https://www.bilibili.com/read/cv5650633)

再次感慨，看视频比看官方文档学习快多了，直观多了，前提是有个好的老师

## template / scaffold
> 合集： https://github.com/vuejs/awesome-vue?tab=readme-ov-file#scaffold
> 合集： https://themeselection.com/vuejs-boilerplate/

官方出品： https://github.com/vuejs/create-vue
项目初始化 1.4k stars:  https://github.com/viandwi24/nuxt3-awesome-starter
vuesion 2.7k https://github.com/vuesion/vuesion
[twitter clone](https://github.com/insidewebdev/twitter-clone) prisma + tailwindcss + nuxt
[nuxt3 tailwindcss starter](https://github.com/Createitv/nuxt3-tailwind-starter)


（不再推荐了，更建议用 nuxt 3）vitesse 8.3k :  https://github.com/antfu/vitesse/blob/main/README.zh-CN.md
v3 后台管理 3.1k stars: https://github.com/un-pany/v3-admin-vite/blob/main/README.zh-CN.md

### 付费模板
国内个人站支付模板
https://oncepay.aiyeshi.cn/

### 放弃使用的
感觉不太好用的？ UI 库 vuetify 38.5k  https://github.com/vuetifyjs/vuetify   Vue 组件库

## components
auth + supabase UI  用户登录组件
https://github.com/nuxtbase/auth-ui-vue

## cheatsheet 
```sh
# 已经默认使用 vite了
npm create vue@latest
npm i vue-router
npm i pinia
```

## tools
音频插件： https://github.com/vueuse/sound  可以用来做交互的音效
grpc 相关： https://anileladag.medium.com/stream-data-to-vuejs-client-using-net-grpc-4b6afcdc7ada

uuid 轻量级替代： nanoid
## 术语
HMR： 热重载
原始对象： 例如 `{a: 12}`
响应式对象： 例如 `reactive({a:12})`

## 理解 nuxt
- 为什么使用 nuxt？ 
    - 因为有 SSR(server side render) 的功能，还有很多更“贴心”的语法（贴心到不想直接写vue）
- 为什么用 NuxtLink 
    - 而不直接 a href='/about' 因为前者能起到“单页面”的功效，切换速度更快，后面再次点击时不会重复请求，而且还有“选中”的css
- useFetch 会尽量避免重复请求，默认行为就是缓存，除非你显式要求他不缓存
    - 所以当你不传入 key 的时候，就算在不同的 `[id].vue` 界面，它都不会重新请求
- nuxi 是独立的 cli 库，跟 nuxt 非同一个库，它主要是命令行功能
### cheatsheet
```
useFetch
definePageMeta
throw createError({statusCode: 404, statusMessage: 'xxx'})
clearError({redirect: '/'})
useHead && <Head><Title><Meta name="">
defineEventHandler
```

## 特殊语法-初期不好理解的语法-反直觉语法
[[vue3-simple精简笔记]]

- 响应式
    - 理解： 就是你改这个值，它会调用一个内部特殊函数，更新对应的 web 上显示的值
- 字典的简写语法
    - `return  { a, b  }`  == `return { a: a,  b :b }` 简写语法
- 冒号的作用
    - `:key="g.id"` 这里冒号的作用相当于把 `g.id`  当作 js 来解析，而不是字符串，准确的说，好像是 `v-bind:key` 的简写
- ref/reactive/store ==不能直接赋值给其他变量== 会丢失响应式
    -  原因是只拷贝了值，但是会丢了”响应式“的功能，需要用 toRef / storeToRefs 函数 （之所以用 storeToRefs 是因为只关注数据，不会吧 store 的方法也包装）
    - 非指针赋值（reactive 的拷贝）
    - `person = reactive({name:'jackie'})`  然后 `name = person.name` , 修改 `name='zoie'` 这个时候 `person.name` 是不更新的！！ 这个跟 python 的指针不一样，这里不是指针. 
    - 正确做法是 `let {name, age} = toRefs(person)` 这个时候才类似指针
        - 注意这个现象只出现在 reactive 这种对象里头
        - 或者用 `name = toRef(person, 'name')`
- 计算属性不是函数，所以用的时候不用加函数的括号，而且是只读的（除非你传入 get() 和 set 函数
- watch
    - 最常用的情况， 监视 ref 基本属性（不是对象，也不用写.value） 或者 reactive 对象属性（用函数的写法）
    - watch 监视Ref 对象的地址值（对于 Ref 默认浅度监视）
        - 而不是 对象里头具体某个属性（这跟我想的不太一样），也就是对象里头某个属性发生变化，watch 是不会出发的，==整个对象发生变化，new/old value 是不一样的==
        - 深度监视需要：  `watch(obj, ()=>{}, {deep: true})`
            - 但是这种方式虽然属性变了，但是“ 地址” 不变，导致你在 log 的时候看到的 newValue 和 OldValue 值是一样的
    - watch 监视 reactive 默认开启”深度监视“！ 不过跟 newValue 和 oldValue 是一样的
    - watch 监视嵌套的具体值（需要写成函数形式）ps: 不是基本类型其实也能直接 watch 但有[诡异现象](https://www.bilibili.com/video/BV1Za4y1r7KE?t=992.0&p=20)，还是用函数形式吧
        -  `watch(()=>person.name, function)` ==这个时候 new/old value 是不一样的==
        -  另外，只要监视的是一个对象，不是基本类型，要写 `watch(...., {deep: true}` 否则默认只检查浅对象变化
- watchEffect: 相当于**自动**解决依赖的 watch，相当于 智能的 react useEffect ?
- reactive 定义的对象不能整体修改 / 更新 reactive 整体对象
    - 必须 `Object.assign(person, {name:'zoie'}` 不够这个其实是 一个个属性替换
- getter： 能返回一个值的函数
    - 如果写在 pinia getters 函数中，”函数名“其实就是一个值... 所以不用加括号（没想到吧）
- 局部css / 局部 id
    - 局部 id 用 ref ， id 默认是全局的，也就是 `<h1 id='title1'>` 改为 `<h1 ref='title1'>`
    - 局部css 加 `scoped` 关键字，例如 `<style scoped>`
- defineProps(['prop_a', 'prop_b'])  可以在 template 中直接用，没想到吧，vue 有很多内置简化的写法，但是在代码中用的话，就需要 props = defineProps..
- define xxx 在 Vue 中可以不用引入，已经默认引入了
- `debugger;`, 类似于python的 `import pdb;pdb.set_trace()`
- 生命周期
    - 周期
        - create(setup解决了) -> mount -> update -> destroy
        - onBeforeMount(()=>{})  /  onMounted
        - 更新onUpdate 
        - 销毁 onUnmounted / onBeforeUnmount
    - 先 Mount 子 再 mount 父亲
- 自定义 Hooks
    - 其实很像类class ... 把一堆相关的数据和函数集合在一起，比如狗相关的数据和操作方法。函数式编程里头的class，或者类似 mixin
- 多次解构语法 + 重命名
    - `let {data:{content: title}} = await axios.get(xxx)` 相当于 result = xx, title = result.data.content
- reactive 内部定义的 ref 在访问其 value 的时候不需要 `.value` . **反直觉**，不知道为啥要这么设计..
- pinia 
    - 直观理解：其实就是定义一个 class 把数据和对应处理数据的函数包起来
    - 使用 `countStore.$patch({a:1, b:2})` 的好处是一次”批量“变更多个属性，性能更好
    - `$subscribe` 就像 watch 函数一样，用来监控 store 内容的变化，触发新工作
- 存储 ref/proxy/reactive 对象
    - 保存： 直接 `localStorage.setItem()` 不行，会存成 `Object..` 需要 `JSON.stringify(xx)`
    - 读取： `alist = JSON.parse(localStorage.getItem('xx') as string) || []`
        - 后面的 `|| []` 是为了防止解析出来是空， `as string` 可以把 null 转为 空值。这样的写法就比 if else 简洁多了
## 类型定义举例

接口后缀是 "Inter"
```js
///////////
// 定义
export interface PersonInter {
    id: string
    age?: int
}

export type Persons = Array<PersonInfer>
// 下面这个也可以
//export type Persons = PersonInfer[]

///////////
// 使用

import {type PersonInter, type Persons} from '@/types'
import {withDefaults} from 'vue'

let persons_list =  reactive<Persons>(xxx)
// defineProps<{alist:Persons}>(['alist'])
withDefaults(defineProps<{alist?:Persons}>(), {list: [{id:'xx'}]})
```

## faq

### 二维大地图性能问题

我要用 二维数组 来改地图，还是通过一个字典，id 是座标来改地图？ 后者速度会更快吗？

嵌入很深的 reactive 对象，有性能问题吗？ （比如我全局只用一个 reactive 狗头）

### 看B站视频加速插件 chrome
![[Pasted image 20231230215738.png]]

### Other

### vscode 插件
除了最官方的几个，推荐下 
- vue vscode snippet 
    - 举个例子： `vbase-3-ts-setup`

### chrome 插件
https://chromewebstore.google.com/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd

### 困扰....
好像中文搜索 vue 比 react 更容易出垃圾信息

### 支持小程序吗
现在基本就这个选择了
熟悉VUE就uniapp
熟悉RN就taro

### 新闻来源
https://www.bilibili.com/video/BV19N4y1U7K2/