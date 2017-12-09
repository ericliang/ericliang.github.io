---
layout: default
title: ""
description: "eric liang's curriculum vitae"
---

## 梁宇鹏 Eric Liang

10年 IM 即时通讯经验，丰富的大规模分布式系统经验，擅长互联网架构设计、技术管理，对2B/2C产品业务都有一定的理解。

[EGO](https://ego.geekbang.org) 北京分会学习委员 公众号&知乎专栏：[一乐来了](https://zhuanlan.zhihu.com/yilecoming) 网站：[ericliang.info](http://ericliang.info) Github: [github.com/ericliang](https://github.com/ericliang)

---

### 履历

* 2017.04 - 至今 环信（C轮）云通讯事业部总经理

	负责云通讯事业部，带领产品、研发、运营、支持、实施团队等部门，以完成 IM 产品线的营收平衡目标。

* 2015.06 - 2017.04 环信（B轮）IM技术总监

	负责IM研发和运维团队，重新设计并实现新的IM协议，也是基于同步思想的二进制通讯协议，解决了原有协议的低效和消息丢失问题。同时解决了运维节点规模增加到3000+节点后的快速迭代和运维保障问题。

	并在随后的时间内，进行相关的服务性能优化和架构调整，服务SLA可用性做到普通集群99.9%，重点集群保障做到99.99%，服务器TCO成本降低50%。

	技术演讲：[GMTC：一个跨平台的云服务SDK需要什么]()，[SDCC：Erlang在大规模分布式系统中的应用]()

* 2014.10 - 2015.06 环信（A轮）Erlang 首席架构师

	优化后台架构设计，并作为两位Erlang工程师之一，改造IM服务EJabberd，保证了随后的并发量按月翻番期间的服务保障。整体长连在半年后从一万达到千万，此次改造相关的也已经在[QCon演讲：指数级增长业务下的架构演化](http://www.infoq.com/cn/presentations/service-structure-transformation-under-the-exponential-growth-service)

---

* 2014.02 - 2014.10 微博（Nasdaq:WB）技术经理

	主导微博平台的全链路优化工作，通过基础测速和数据统计，量化分析性能瓶颈，旨在提高移动客户端对微博接口的访问速度。当前已经完成Feed服务的多机房架构设计。

	负责文件服务平台的规划设计，此平台将整合包括TFS、S3和图床等多个存储引擎，提供自适应的高速文件存储服务。目前正在进行文件的上传加速优化。

* 2013.06 - 2014.02 微博（Nasdaq:WB）技术经理

	带领一个小型异地开发团队，与多个产品线与研发部门协作，按期完成内容推送系统Castalia的开发与上线，实现了性能的百倍提升并顺利完成新老系统的无故障迁移，已在[QCon2013演讲](www.infoq.com/cn/presentations/high-performance-services-practice-based-on-cell-architecture)

	主持平台研发部的技术评审，从架构设计到性能优化多个方面为项目提供建议和指导；

	负责策划和组织公司黑客马拉松活动和部门技术研讨会，在新技术应用、流程改进等方面进行积极探索和实践；

* 2011.04 - 2013.06 微博（Nasdaq:WB）Java 通讯技术专家

	负责优化IM系统核心服务Openfire，通过模型研究以及量化分析对系统进行升级改造，整体容量达到千万级；

	负责研究面向移动网络的协议WeSync，通过总结业界经验，进行增量同步协议的设计与实现，同时主导新通讯服务的架构设计工作；

---

* 2010.04 - 2011.04 创业公司 Erlang 项目经理

	负责整个IM团队，包括服务端、客户端和运维（共5人），并进行服务端架构设计与开发工作。此服务基于开源软件EJabberd开发，并通过RabbitMQ进行内部消息的订阅与发布，可支撑十万级别同时在线；

	项目期间，重构了Ejabberd与RabbitMQ的网关，并已将代码补丁提交到社区。


* 2007.08 - 2010.04 慧聪网（HK8292）C/C++/Erlang 服务端高级工程师

	负责IM系统服务端开发和维护，解决多个内存泄露问题，将系统MTBF时间由一天提高到一百天以上。考虑到不同语言间的互操作性问题，相关服务均使用SOAP协议与外部系统通信。此服务基于开源软件Jabberd2开发，对基础组件的修改也已经提交到社区。

	将分词技术与人工智能理论结合，使用Erlang实现了客服问答专家系统，并采用BP神经网络思想进行知识库的进化。

---

### 开源

* [RabbitMQ-XMPP](http://www.rabbitmq.com/devtools.html#miscellaneous) Erlang 代码贡献者 重构和Bug修复，[fork](https://github.com/ericliang/rabbitmq-xmpp)
* [Ejabberd](http://www.ejabberd.im/) Erlang 代码贡献者 更改数据库连接池策略，增加多池支持（包括配置）
* [Yaws](http://yaws.hyber.org/) Erlang 代码贡献者 添加SOAP服务配置文件支持
* [Jabberd2](http://codex.xiaoka.com/wiki/jabberd2:start) C 代码贡献者 优化公共组件list的数据结构

### 教育

* 2003.09-2007.07 北京理工大学 学士学位 软件工程专业

### 其他

* 应用层组播平台 C++ 优秀毕业设计Top10%，国家自然科学基金项目，设计并实现了应用层组播协议，合作者高建敏
