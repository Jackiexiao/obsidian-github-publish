---
share: true
alias: [macOS, mac, macbook]
---
## faq
### 如何解决屏保landscape 过多
https://www.reddit.com/r/MacOS/comments/16t0dai/i_just_downloaded_way_too_many_gb_of_wallpapers/

### 磁盘空间占用

* 系统设置里头的 storage 来查看
* 用 OmniDiskSweeper 可以看到每个文件夹的具体大小
- 腾讯 lemon 

### finder中打开终端

最容易记忆的方式是，拖动文件夹到终端，如果是 cmd + 拖动会直接 cd

只能说特别麻烦（除非你设置一个新的快捷键

下面这个只能在文件夹上右键操作

![[Pasted image 20231111221016.png]]

### 自动切换输入法
https://sspai.com/post/77870 这里列举了大量已有的应用
- switchkey 不推荐！不好用

最终选择 input source pro ，看来未来可能付费（目前不用），效果也好一些
https://inputsource.pro/zh-CN
2023-11-11 感觉很好用，我喜欢！
这种官网界面很简洁，爱了 以后也要做类似的页面

### 录屏自带无声
用 loopback； 安装上稍微有点麻烦（需要重启电脑两次），但按照它的指示和教程一步步来就行
教程： https://www.youtube.com/watch?v=-aTCbnc-0Dk

然后录屏的时候选择你设置的虚拟音频来源（这个虚拟音频来源于你在 loopback中的设置）就行

Omi 录屏专家 好像也可以，我没测试

### 常见问题
OmniDiskSweeper: 查看磁盘空间占用
Buhocleaner:  （破解版）

option command + V 是剪贴（还是 command c 选择文件

卡死按 command option + esc 键
或者原地等待30秒，会自动重启好像...

### 跟window共享文件

https://support.apple.com/en-sg/guide/mac-help/mchlp1657/mac

smb://10.0.33.28

然后 window 浏览器访问
```
\\10.0.33.28
```
输入用户名和密码就可以了

注意这玩意是有点不安全的


## 写作ing

一直以来都很想要有一个MacBook，因为经常看到其他程序原油在使用MacBook，而且别人说程序员特别适合用MacBook，然后这次生日女朋友给我买了个MacBook特别的开心，但是丑晕倒是转卖不得过程真的特别的酸甜苦辣，但最后还是觉得真的像一度觉得很后悔

希望我这篇文章能够帮助你（尤其是程序员）判断你是否需要购买MacBook以及，如果你购买MacBook你应该怎么设置？

我现在讲一下对我来说真香的几个点

第一个是语音输入，它是系统自带的，按键盘上的一个按钮马上就可以在任何地方语音转文字，这篇文章就是通过语音识别写出来的，这对我来说真的很香，因为我平时都是直接键盘打字，但是键盘打字的效率常常比语音输入要低得多， 按住按钮随时都可以写文章的感觉真的非常的爽。当然你也可以选择用搜狗语音输入，集成的也很不错

MacBook的续航是真的要比windows好太多

macbook的编程体验真的挺好的，尽管windows有 wsl2能够当linux用，但我觉得用起来体验真的没有很好，wsl2有很多坑，说起来都是泪，macbook本身的就是unix系统，所以很多情况下使用起来跟linux差不多

macbook 跟 iphone 无缝衔接的感觉真的很爽！icloud，照片，复制粘贴

MacBook下面有很多非常精品的软件， 而且有些软件目前还是独占的，就比如说Raycast Rewind Warp Bob，这些软件配合mac的系统，用起来真的非常非常丝滑。

mac的系统本身也非常的优秀，就比如说他有一个Spotlight就command +空格就可以呼出一个命令行，它几乎可以做任何你用电脑频繁操作的事情。 然后他安装的软件几乎都没有什么广告，而且隐私相关的都需要你进行授权，不会像windows那样会携带全家桶，安装一堆乱七八糟的软件。它的触控板用过的人都说爽，它的四指切换全屏软件非常丝滑

我一开始不是很明白MacBook上面为什么会有个command还有个Control键，这两个的那不是重复的吗？后来才明白，这对于程序员来说真的非常友好，比如说windowns里头 Control + C有两个重复的功能，有时候是复制，有时候是终止程序，但是在Mac book里头你Command + C 是复制，但是Control+ C就是终止程序，它可以把两种功能区分开来，类似的例子 command + A是全选，control + a 是终端跳转到命令的开头， 避免windows里头各种快捷键冲突问题

说完正香的点，接下来来说说windows转macbook我的心酸往事，windows转macbook真的很麻烦，你几乎要重新学习一个新的操作系统的使用方法，而且他很多情况下跟windows完全不同，光是快捷键就可以够你学很久了，更别说你要迁移一大堆软件的设置到MacBook里头。 我感觉到自己陆陆续续花了一个月的时间，才渐渐熟悉macbook的使用， 这个时候才感觉到macbook的真香。

最后跟大家分享一下，我在折腾MacBook过程中遇到了一些常见的问题以及解决方案，最后会给大家分享一下非常推荐给个人/程序员安装的一些实用效率软件


# 真香！一个程序员windows转mac的心路历程

从windows迁移到MacBook一定要看教程， 这两个系统的差异性实在太大了，你需要折腾很久，才能让获得非常舒适的使用体验，B站上已经有很多， 这里分享一些我自己的经验

首先是浏览器，我真的非常推荐使用chrome。如果你登录的帐号的话，他几乎无缝的把所有设置切换到macbook

其次是 vim 中英文切换，我使用的是 Squirrel， 它可以在写代码的时候无缝的在vim中英文中切换，教程可以在哔哩哔哩上查找

初次使用MacBook真的需要安装很多软件才能让 windows的用户觉得“不别扭”， 否则我觉得你是无论如何无法适应macbook，会觉得它特别难用， 其中 [better365](https://www.better365.cn/) 的软件几乎都是必装的。

# 实用软件

- raycast 代替 spotlight 代替 Rectangle(自定义分屏多窗）+剪贴板
- [linear mouse](https://linearmouse.app/zh-CN/) 让鼠标变的好用，同时解决触控板滑动问题（mac的鼠标不装这个插件的话非常难用）
- rewind 回忆一切你曾经操作过的东西

- IINA 堪比Windows系统的 PotPlayer，天生就是一个现代的 macOS 应用程序，从它的框架到用户界面

更多推荐：
https://juejin.cn/post/7017276179304415262

程序员
- homebrew
- xcode
- visual studio code
- cursor: 集成了 chatgpt 的 vscode (可以自定义 apikey)
- warp 贼好用的终端
- Apifox = Postman + Swagger + Mock + JMeter
- Dash是一个API文档浏览器，使用户可以使用离线功能即时搜索无数API。
Parallels Desktop mac上访问windows（但我决定使用另一个电脑...）

十个必装软件
- IINA(视频播放软件）  https://iina.io/
- 剪映（视频剪辑工具）  
- Snipaste(多功能截图）  
- [Easydict](https://github.com/tisfeng/Easydict) 查词软件，Bob 的免费版本，快捷键 option + d/a

better365.cn 出品系列（全都很好用）
- [键指如飞](https://www.better365.cn/FlyKey.html)（查询当前软件的所有快捷键）   类似软件： [cheatsheet](https://www.mediaatelier.com/CheatSheet/)
- 它家很多很好用的软件！！比如 解压软件 超级右键 自动切换输入法 iBar(针对刘海屏菜单栏拓展) 之类的 这里就不一一列出了

我还未使用的
- Omi录屏专家  


#### clashX
翻墙软件

对于终端翻墙，需要设置
```
export http_proxy=http://127.0.0.1:7890 export https_proxy=http://127.0.0.1:7890 export all_proxy=socks5://127.0.0.1:7891
```

保存上面内容在 `~/.zshrc` 中即可


#### homebrew
类似 apt install 的工具

使用官网的方式安装，记得
```
==> Next steps:
- Add Homebrew to your PATH in /Users/$USER/.zprofile:
    echo 'eval $(/opt/homebrew/bin/brew shellenv)' >> /Users/$USER/.zprofile
    eval $(/opt/homebrew/bin/brew shellenv)
```

#### vim 中英文切换

下载m1的im-select
chmod 777 im-select
然后在 finder 访达 中右键打开，选择打开（才不会有 milicious 恶意软件的报错）
然后 ./im-select
com.sogou.inputmethod.sogou.pinyin

## cheatsheet最常用的快捷键
> 如果我有段时间没用，看这个最好
https://support.apple.com/zh-cn/HT201236
 setting touchpad 中查看各种手势的用法（到那个地方复习就行了）

个人最常用
cmd shift / : 打开帮助（可以搜索快捷键！！）

cmd shift c : vscode 中打开terminal

Fn 切换输入法.... keyboard 设置里头有
fn + q 快速笔记
cmd+K: 清除终端屏幕（cmd L 是逐行清除..）
cmd+f3: 桌面
cmd + q : 退出
cmd + h: 隐藏
cmd +m: 最小化（似乎跟 h 的不同在于必须手动重新点击？）
control + 左右 快速切换桌面 （如果想通过 ctrl +1/2/3 来切换，见[文章](https://www.zhihu.com/question/21079800)
**Control-Command-空格键**：显示字符检视器，你可以从中选择[表情符号和其他符号](https://support.apple.com/zh-cn/guide/mac-help/mchlp1560/mac)
**Control-Command-F**：全屏使用 App（如果 App 支持）。
**Shift-Command-5**：在 [macOS Mojave 或更高版本](https://support.apple.com/zh-cn/HT201260)中，拍摄截屏或录制屏幕。也可以使用 Shift-Command-3 或 Shift-Command-4 来拍摄截屏。[进一步了解截屏](https://support.apple.com/zh-cn/HT201361)。
control + 空格 : 切换输入法
双击control（貌似需要设置，进入 语音输入）

cmd + d （学名:复制） == 复制 + 粘贴
cmd + c（学名:拷贝） == ctrl + c
cmd + c 以及 cmd + option + v 实现剪切功能（要不就直接拖动）

## trick
keyboard->text_input->text replacement 可以设置常见短语来替换，比如设置 `aphone` -> `你的手机号码`，电脑输入完成按空格或继续输入其他字符就替换，按enter就正常输入`aphone`

## macbook 上手指南
最佳快速入门教程-半小时: https://www.bilibili.com/video/BV1PF411E7LG/
详细入门教程-几小时: https://www.bilibili.com/video/BV1Kd4y1v7ij

程序坞、dock栏
访达: 文件浏览器
option -> alt
command -> ctrl 
那 control -> ???

## 购买指北
最终结论: 程序员ios开发，性价比最高的选择:  m1 + 16g + 256g ，闲鱼5900买到

### mac mini 还是 macbook air
mac mini（无屏幕电脑） 闲鱼只需要3000，macbook air 闲鱼 4500 （拼多多5000）左右。考虑到我偶尔会带出门，还是 air 吧

### m1 还是 intel
- m1 续航比 Intel 好很多，现在2023，很多软件也适配了
- 对于开发iOS应用来说，M1和Intel处理器没有太大区别。只有一点，就是现在M1支持macOS直接运行iOS程序，如果你需要测试这个功能，那只能用M1。开发macOS同样也都可以，clang在编译时可以配置输出多架构的binary，所以开发和上架不用担心

### m1 还是 m2
m2 看起来性能提升没有很多，还是m1

### 8G 还是 16G
- 90%的用户 8G 就够了
- 但对于我，16G 更好

理由: 
- 感觉上 16g 还是对的，因为我会开多个 electron 应用 + xcode，这些应用加上跑程序会比较占用内存（偶尔需要本地调试）
- 有几点要解释一下。首先是因为arm和x86的差异很大，内存大小逻辑不能照搬，如果按照正常的性能比较，m1的8g基本相当于x86下的16g 16要比32还强。这主要是得益于三倍以上的内存带宽以及cpu gpu共享内存等。因此，除非是在非常极限的多任务处理或者是8k视频这样的超高性能需求任务下，否则8和16的实际使用差距可以基本忽略不计
- 不开虚拟机的同学8g绝对够用了。mac的硬盘速度+内存虚拟化+压缩算法，8g也很能打的

### 256 G 还是 512G
- 256 外挂硬盘就可以


# faq

## 终端翻墙
https://github.com/Qingquan-Li/blog/issues/131
    
## mail 的设置
我现在的所有邮件都通过系统自带的 mail 邮箱来接收了，这里记录一下常见的问题

QQ 邮箱： 需要使用授权码，不是“正常”的密码，具体网络上查一下
如果报错，可能要在 macOS mail 中删除 QQ 邮箱帐号，再重新添加
###  macos下Mail.app发邮件出现无法将一封邮件移到邮箱的解决方法
https://danteng.org/macos-mail-app-imap-append-failed/

### 腾讯企业邮箱设置
mail 设置 -> add acount -> 选择其他邮箱 -> 填入你的帐号密码，接着会提示让你填入下面的信息：

IMAP协议
    接收邮件服务器：imap.exmail.qq.com
    发送邮件服务器：smtp.exmail.qq.com

如果IMAP协议没有开，需要到腾讯企业邮件中的“客户端设置”中开启

## os 获取包名
osascript -e 'id of app "Finder"'

将`Finder`替换成你的应用程序名字

## 三指拖动远距离怎么办
- 三指触发拖动后，留两指保持状态，直接用另一个手的单指负责移动，适合距离超远定位要求又特别精确

## U盘格式问题
- FAT32 优先推荐: 是到目前为止最被广泛认可、且最易用的文件系统格式之一。但是，FAT32也有一个非常致命的缺点就是不能存储单个文件容量大于4GB的文件，所以如果想要用这种格式存放高清电影几乎是不可能的。如果你需要存储单个文件容量大于4GB的文件，也可以选择将其格式化成 exFAT 文件系统，
- exFAT 但这种文件系统对于一些老系统兼容性不好，并且在一些优盘上速度很慢很慢。所以，对于一般用途来说，FAT32仍然是优盘文件系统首选。
