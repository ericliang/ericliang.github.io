---
layout: post
title: "故障之后"
description: ""
category: 
tags: []
---

阿里、携程接力两天的服务故障，沸腾了整个码农界。

看热闹都不怕事儿大。光纤被挖，引得异地双活被嘲讽，逼着支付宝最后有人出来打保票，年底我们一定搞完异地双活；线上服务被删更是报复论、Bug论频频，还出现了异司双活的崇拜，携程只是道了个歉，但是各种开人、睡人的小道消息也没停下。

热闹之余，人民群众也没闲着，纷纷忆苦思甜，言必称曾经。

这个说，“曾经我把数据库truncate了，老大当时不给解决方案只给目标，修了一晚上，期间各种惊心动魄，第二天恢复了竟然没人发现”。

那个说，“曾经有个新员工，没分清线上环境和测试环境，把线上数据库Rebuild了，导致某网站下线几小时”。（注：此次携程下线8个小时，据公开资料显示，其每宕机一秒会损失人民币5000元）

。。。

就像说起苦日子，都是自己小时候家里穷，你说你吃过糠我就说挖过树皮。事实上，大多数互联网服务都是7x24的，线上问题肯定是天天有。@TimYang 更是写过一篇[黑天鹅](http://timyang.net/service/black-swan-of-service/)来表达这种见怪不怪。

这些苦又有什么可说呢？只是用来在自己遇到问题的某一天，聊以自慰么？

**我们经常说，“吃一堑，长一智”，而我在每个团队里都在说的是，“真正聪明的人，可以从别人的问题里学到东西”。在我看来，更重要的其实在后面，后来又发生了什么？**

依携程现在流言四出的状况，公关已然疯掉，明确的事故报告是很难了。但这不妨碍我们思考，要是发生在自己身上会发生什么？如果分析出来原因是程序Bug，如果原因是人为操作失误，如果是故意操作，结果会有区别么？我会在文后回答这个问题。

![Follow the leaders http://www.huffingtonpost.com/2014/03/03/isaac-cordal_n_4876935.html](/assets/pics/follow-the-leaders-by-Isaac-Cordal.jpg)

@左耳朵耗子 说得很直接

“技术上出故障是必然的。能否体现一个公司是技术公司，重要看这几点：1）故障的恢复是否有技术含量，2）公司对故障的处理方式，如果是通过加更多的流程，或是通过加更多的权限管控，或是通过处罚犯错误的人，或是上升到员工意识形态上，而不是去用更好的技术来解决，那么这个公司不会是个技术公司。”

但是遗憾的是，增加流程基本上算是大多数国产公司的首选，来个层层审批，更有甚者，来个线下审批什么的，让你一夜回到有纸办公的原始社会。

**说一个前几天的故事。**

我们服务升级，灰度部署一台机器后，把一个存储集群搞挂了。这件事的直接原因，是改了一行代码，没有压测就上了线。

服务最后通过降级扶住了，但是大家还是各出了一身汗，于是开会总结。总结的目的肯定是，如何避免同类事情的再次发生？有人提建议说，增加产品经理来做最后一级上线审批吧？

我当然是拒绝的。

为什么？我当然也知道增加审批的好处。首先，后续措施如果是加流程，那其实在暗示整个事情的发生受累于流程缺失，其他原因可以不再深究。

其次，再加一道审批，说明以后也不怕出问题了，因为最大的责任总会落在最后一个人身上，即使后面还是问题不断。

最后一点，对领导更有交待，如果你只是说Fix了一个服务的Bug，总有可能显得对问题不太上心，听起来也不太可靠。比较而言，增加流程就让人放心多了。

但是，我们聚在一起是为了做事，而不是为逃避责任不是吗？但是但是，人又是懒惰的。Larry Wall说，“好的程序员有三个宝贵品德，懒惰、没耐心和骄傲”。这话经过了一个又一个优秀的程序员的验证。

**你要做事，又很懒惰。那除了让事情更快更好地完成，似乎别无他法。**

加流程让事情更快了么？明显没有。每次服务上线多一层沟通，沟通意味着要协商另一个人的时间，然后你向他解释当前的情况。如果对方再不了解背景，那就足以让你崩溃死机了。

加流程让事情更好了么？没有。它对真正问题毫无益处，不幸的是，它还让整件事情变得更坏了。问题的根本原因在加流程的掩盖下蒙混过关，然后蠢蠢欲动在未来的某一天重新爆发。到了那时候，你依然需要分析整个事情，不同的是已经有了惯例，而这个惯例又会带来新的流程。

**这就像纸尿裤。一个小孩尿了裤子，可以给他穿上纸尿裤。但是，健康成年人有穿的么？更危险的还在于，你不知道什么时候可以脱下来，因为是别人给你穿的，别人才不管你什么时候可以自禁了。**

这也是很多公司为什么流程越来越重的原因，取消一个流程比增加一个流程要难得多。如果你能证明不需要一个流程也许在最开始就可以通过证明不增加它了。

回到总结会，我们又继续讨论了下去。经过复盘确认，当时的情况是，压测环境创建耗时费力，开发进度一再推迟下，经过团队讨论觉得没有问题，于是就跳过了压测步骤。

为什么可以跳过？因为整个技术团队都讨论了，评估这个压测可以不做（为什么我后文会讲）。这也是我拒绝产品经理审核的一个原因，因为他肯定没有技术了解整个服务，而风险管控最大的依据在于技术团队的评估。如果技术评估没有风险，他再来也是不会对结果有所改变的。

为什么决定这个压测不做了呢？因为我们两个负责人（本来也只有两个人），其中看了一眼文档（你没有看错），然后跟对方说似乎有个性能改进。另一个听到对方这么说，于是也看了一眼文档，下意识觉得那肯定是妥妥的了嘛。

**这是什么鬼？思维惰性导致的循环依赖啊。实际上，只要再看一眼源代码，就知道不应该做这个改动了。但是两个人都没有去看，真是群愚的又一个例子。**

选择不做压测，还有个原因，压测过程迟迟不能开展，而服务又着急上线。压测进展慢，因为压测没有计划，且在功能回归之后才进行。压测环境部署没有自动化，全部服务部署一次需要近十个小时，再跑完压测基本需要额外一天。而服务着急上线，是因为服务交付日期延迟了一周又一周。归根到底，整个团队研发效率的低下，已经导致完整流程跑不完了。

所以最后会议的决定变成了：

1. 确定压测步骤的必要性，再少的代码改动都不可以绕过；
2. 明确上线责任，而不是让责任继续分散，开发人员自己需要对新版本性能负责；
3. 提前制定压测计划，在服务开发完后立即进行压测，与功能测试同时进行；
4. 自动化压测环境部署，我们在云上构建服务，主机初始化和服务部署都使用脚本或管理工具自动化；

**就在本文截稿之时，经过运维同事的努力，我们从零完整部署基准压测环境（支持100w同时在线）的时间，已经缩短到两小时以内。整个压测回归可以在三个小时内搞定。压测再也不是一个负担了。**

当然研发效率的提高也在改进中，这是一个更大的话题稍后有机会再展开。

从这方面看，我们算一个技术公司么？我觉得是的，因为这样的公司里，不管遇到什么问题，技术的总会归技术。因为我们都相信，技术问题都可以通过技术解决。这句话也是对开始问题的回复。

所以亲爱的兄弟姐妹们，那个故障之后，你们得到的是流程还是技术改进呢？你们还好么？

![http://www.photoree.com/photos/permalink/2384434-61417564@N00](/assets/pics/sailing-in-schooner.jpg)

如果有一天，你忽然发现，增加了太多流程，却依然做不好服务。请不要忘记，我们欢迎你。
