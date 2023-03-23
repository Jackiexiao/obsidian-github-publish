---
alias: [aimodel]
share: true
---

# 成功的案例

### 2023-3-22 小红书博主
2023-3-23: 这个小红书博主的效果比较好，他正在逐步实验过程中
![[Pasted image 20230323144413.png|200]]
https://www.xiaohongshu.com/user/profile/635a7009000000001802df29?xhsshare=CopyLink&appuid=62b0ae90000000001b02a39d&apptime=1679465893


### 2023-3-16 火的案例

![[Pasted image 20230320113313.png|100]] ![[Pasted image 20230320113346.png|100]]

![[Pasted image 20230320113330.png|250]]


# 实验记录


## 1.传统ai模特
### 实验1.1: 使用 zmo.ai
https://www.zmo.ai/aimodels/: 感觉不好用，提交照片容易报错，生成效果也不好

![[Pasted image 20230323142805.png|100]] ![[Pasted image 20230323142749.png|105]]

### 实验2.2: 使用 阿里AI模特 等
> todo

https://yc.alibaba.com/#/targetFace 听说阿里的ai模特只能处理简单款式
https://vue.ai/products/on-model-imagery/

## 2. stable diffusion
### 实验1.1 塑料假人微调模型: 失败
放在塑料假人身上的7张照片，训练标签: A plaster model wearing a brassiere. 用 leonardo.ai 训练，最终效果很糟糕

### 实验1.2 局部重绘: 失败

自己穿衣服拍照 然后局部重绘，重绘衣服之外的所有东西

只能说大部分效果很奇怪，很难生成比较好的，下面这几个是copy了其他照片的 prompt + mask抠图结果，很像是直接P图...  内衣颜色很诡异，而且由于光线原因非常不自然

![[Snipaste_2023-03-20_11-39-16.png|100]] ![[Pasted image 20230320232226.png|100]] ![[Pasted image 20230320232245.png|100]] 

### 实验1.3 微调模型+upscale: 少量成功

- 部分还原款式，但时常错误
- 有色差
- 有概率生成跟训练集一样的结果（只有bra）
- 生成照片的姿势跟训练集中的姿势很像
- 初始生成，人很丑.... 五官有问题，但是 Upscale 可以修复

训练数据， prompt: A brassiere
![[Pasted image 20230323174355.png]]

A brassiere, girl, shoulder length messy blonde hair, heterochromia brown and grey, happy, shopping, Full body Beautiful girl, sweat leggs, sexypose, clean detailed faces, intracate clothing, analogous colors, glowing shadows, beautiful gradient, depth of field, clean image, high quality, high detail, high definition,cute face, big braest, slim waist, nice hips, ttato in the left arm, A brassiere

upscale 前

![[Pasted image 20230323173401.png]]

upscale 后

![[Pasted image 20230323181141.png|200]] ![[Pasted image 20230323181123.png|200]] ![[Pasted image 20230323181035.png|200]]
![[eb62082a71fd38a863422d0505bf513.png|200]] ![[Pasted image 20230323181213.png|200]]

### lora + ControlNet + inpaint

> todo 参考 [[#2023-3-22 小红书博主]] 

> [!todo] 2023-3-23 目前没有本地调试的机器，对这块也不太熟悉，先观望

stable diffusion 生成逼真模特
ControlNet 提供精确的姿势控制
Inpaint 让衣服道具和背景无缝衔接

