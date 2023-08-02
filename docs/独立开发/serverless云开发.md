---
alias: [微服务, faas, function as service, 容器即服务, 函数即服务]
share: true
---

# serverless云开发

分成两大类
- 容器即服务（例如Google Cloud Run，Fly.io）
- 函数即服务（例如 AWS Lambda、Cloudflare Workers、Fastly Compute @ Edge、Suborbital, vercel ）

- serverless function 比 docker 还要方便（都不需要构建 docker 了），由于不需要直接接触"服务器"，所以也不用运维
- ==强烈推荐== 阅读并复习这个文章，解决了我的一堆问题 https://www.phodal.com/blog/serverless-architecutre-cons-and-pros/
- 新手入门（通俗易懂，解释 why! 就是用了 serverless 简直不需要运维 - [现在很火的Serverless是什么，能干什么？（1/4）有哪些东西和Serverless做同样的事_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1KG411w7fb)  

# faq
### 0.1 使用serverless应该注意的参数

Serverless服务提供商会限制函数的并发执行数


### 0.2 降低冷启动时间的方法

看下面这两篇就够了
https://aws.amazon.com/cn/blogs/china/4-solutions-to-reduce-the-cold-start-time-of-aws-lambda/
https://www.alibabacloud.com/help/zh/function-compute/latest/best-practice-for-reducing-the-cold-start-latency

python / nodejs / ruby 冷启动时间比较少，相关依赖（比如 requirements.txt）一般都会有缓存的，不会占用很多时间。

- 减少代码包的大小能减少下载时间。
- 选择脚本语言: 对于 python/nodejs 大部分冷启动都在 50ms 内
- 预留实例（比如 onnx 模型一般就要预留至少几个实例吧，用户多的时候再启动多个）

当然，除了上述文章提到的通用问题，你自己写的代码的启动时间也是一个重要的优化点（比如加载 onnx 模型....）

### 0.3 能对接数据库吗?

可以，也能对接 COS 之类的 持久化存储


### 0.4 哪家厂家好?
- 容器服务的对比
    - [各家云上 Kubernetes 服务对比 | 桔子小窝](https://maoxian.de/2019/06/1576.html) 
    - [UCloud、青云、腾讯云、阿里云、华为云、网易云、京东云等云厂商容器服务哪家强？ - 知乎](https://www.zhihu.com/question/296578061) 
    - log
        - 2022-12-10 暂时选择 腾讯云，因为比较便宜；后续可以考虑 google cloud 或者 阿里云，因为还能支持GPU训练

# summary
- 是什么
    - FaaS + BaaS
        - FaaS: Function 函数即服务（相当于不用自己用 FastApi 搭建框架了，你只需要提供函数，是不是贼方便）
        - BaaS
            - 比如一般是 代码配套下面的几个东西
                - 云数据库
                - 云存储
                - 前端网页托管
            - 不跟代码放在一台服务器上的原因
                - 安全性，一个服务崩溃或者被攻击，数据还在，数据不用担心被攻击的事情（因为直接用阿里云的数据库）
                - 省钱，可以按需买存储
                - 流量
    - Serverless应用并非不需要服务器作为计算资源，正确的理解是应用开发人员无需关注计算资源的获取和运维，由平台来按需分配计算资源，并保证应用执行的SLA。
    - 我们可以看到容器技术（LXC, CGroup等）非常适合用于提供Serverless的计算环境。每次系统接收到事件，动态启动容器来执行业务逻辑即可。这也是为什么有人戏称 “Serverless” Is Basically CGI In Containers
    - 无服务器方案中仍然有服务器，但它们已从应用开发中抽离了出来。云提供商负责置备、维护和扩展服务器基础架构等例行工作。开发人员可以简单地将代码打包到容器中进行部署。
    - 部署之后，无服务器应用即可响应需求，并根据需要自动扩容。公共云提供商的无服务器产品通常通过一种事件驱动执行模型来按需计量。因此，当无服务器功能闲置时，不会产生费用。
# tutorial
- [Serverless 2.0，鸡蛋还是银弹？-阿里云开发者社区](https://developer.aliyun.com/article/782142) 
- [GitHub - phodal/serverless: Serverless 架构应用开发指南 - Serverless Architecture Application Development Guide with Serverless Framework.](https://github.com/phodal/serverless)  但这个很久没更新了（2019年)
## 1 产品类型
- google 云给了非常详细，直观的产品方案: [应用托管方案  |  Hosting Options  |  Google Cloud](https://cloud.google.com/hosting-options?hl=zh-cn) 
- 函数计算 FC 
- SAE 
- 面向容器编排的 Serverless Kubernetes
    - 全托管：Master 节点和 Worker 节点完全由云来管理，只提供 API 来调用，一般按照实际的 CPU 和内存使用来计费
    - 半托管：Master 节点由云来管理，自行购买 Worker 节点。可以修改部分 Master 节点的配置，所有容器在自己的机器上运行
    - 全独立：Master 节点和 Worker 节点都由用户管理，云只负责节点的初始化和小部分维护工作。可以修改几乎所有 Master 的配置，整个集群完全独立
- 面向容器实例的 ECI 等 
# 厂家列表
https://laf.run/ laf 云开发
https://webify.cloudbase.net/ 腾讯云 weblify

- 也可以选择自建 [k8s](k8s.md) ,但是比较麻烦，不推荐自建，原因见:
    - 单单是安装 k8s 就挺麻烦了...
        - 从效率和人力成本上看，**托管K8S集群完胜自建Kubernetes集群**  
        - 集群的安装，补丁以及常规版本升级在运维工作中属于体力活。在**规模不大的时候，使用人工实现需要花费不少时间**准备环境测试验证，且易错。如果**集群体量不够大的话，开发自动化运维脚本又浪费人力成本**。云计算厂商的托管K8S集群将提供专业、稳定的技术运维服务，和几乎为零的人力成本。  
    - [阿里云 Kubernetes vs. 自建 Kubernetes_容器服务Swarm版（已停止服务）（隐藏）否-阿里云帮助中心](https://help.aliyun.com/document_detail/69575.html?spm=a2c6h.12873639.article-detail.25.4de5155bvycymp)
    - [不要自建Kubernetes-阿里云开发者社区](https://developer.aliyun.com/article/693754) 
- 阿里云 serverless
    - 完整的容器托管服务列表: [阿里容器托管方案有哪些-云原生 - 阿里云](https://www.aliyun.com/tg/aliware/4814332.html)
    - 全托管模式: SAE [Serverless 应用引擎SAE_应用托管服务_零代码改造上云_容器与中间件-阿里云](https://www.aliyun.com/product/aliware/sae) 
        - 也是按量付费
- 华为云
    - 华为云托管
        - 容器全托管模式: [云托管 - 华为开发者联盟](https://developer.huawei.com/consumer/cn/agconnect/cloud-hosting/) 
        - 要实名认证.... 暂时跳过
- AWS
    - [Aliases]
        - Amazon Web Services  
        - 亚马逊云
    - [Amazon ECS 容器管理_ECS软件容器管理服务-AWS云服务](https://aws.amazon.com/cn/ecs/) 
        - 它说它有香港的服务器: [AWS Fargate 现已在香港区域推出](https://aws.amazon.com/cn/about-aws/whats-new/2019/08/aws-fargate-now-available-hong-kong-region/)
        - 但是! （ps 切换服务器的方式是 在右上角选择区域，然后域名也会跟着变成 "ap-southeast...aws....com" 之类的） 然后创建集群这个操作我也不是太懂
            - ![](local://C:/Users/jackiexiao/remnote/remnote-633a838ba408e8d2d2f34451/files/d0fuzBV8c60Zd0-HeOgA89i-h7KdOHrpOsbdhdCd3G8LqoUWVwp6xx0cekK7Nrxub8LPv8MRjHHfekeMZc40c9xVPPiGRZDxOJhBpjSRt6IqFQvxW1rh8h6ZtPhf54hf.png) 
    - 国内的aws: cn 结尾，但建议还是用海外版的...
    - 
    - 全托管服务
        - [AWS Fargate容器部署_无需管理服务器与集群的容器服务-AWS云服务](https://aws.amazon.com/cn/fargate/?c=ser&sec=srv) 
    - EKS 容器编排服务
        - [Amazon EKS - Amazon Web Services](https://www.amazonaws.cn/eks/) 
- Azure上的AKS
    - Microsoft 云服务
- Google - GCP
    - 各种产品的对比见: [google 云给了非常详细，直观的产品方案: 应用托管方案  |  Hosting Options  |  Google Cloud ](serverless使用指南/产品类型/google 云给了非常详细，直观的产品方案_ 应用托管方案  _  Hosting Options  _  Google Cloud.md) 
    - Kubernetes Engine
    - App Engine
        - [App Engine 应用平台  |  Google Cloud](https://cloud.google.com/appengine?hl=zh-cn)  基于应用（限制几个语言，这里 python 是支持的）的托管
    - Cloud Run
        - [Cloud Run：只需数秒即可将容器部署到生产环境中  |  Google Cloud](https://cloud.google.com/run?hl=zh-cn) 基于容器的全托管 
# 案例
- uniapp + unicloud serverless 全栈开发