---
title: GEO 排名因子之一：Entity 和主题权重
date: 2026-08-18 10:00:00
tags:
  - GEO
  - SEO
  - Entity
  - Topical Map
  - 内容策略
categories: GEO/SEO
header-img: https://bysocket.com/images/hello-world/header-img.webp
---

最近 building 一些关于 SEO 的 Agent Skills，发现针对一个中大型网站 SEO 的 Entity Definition 和 Topical Map 真的难 Agent Skill 化，只能实现初稿版。因为定义 Entity 和定义主题是一个 Research 的活，不是特别标准。

刚好这个 GEO 时代，对 SEO 要求也在变化了，**不是有流量的词，东扯西扯说有点关系都去蹭 SEO 流量**。

举个例子，你做 AI SaaS，所有 AI 相关的词都可以蹭吗？比如每次新模型发版，相关的词不一定你要蹭。再比如极端一点的，稍微文明一点说——ai girlfriend 相关词，只要你不做这个品方向，也不要碰。

这里就引出做 GEO 优化或 SEO 排名时，注意有个因子就是 **Entity 定义和主题权重**。

## 一、什么是 Entity？作用是什么

什么是 Entity？大白话说，就是先说清楚：你这个网站到底是干什么的。

我一直喜欢把网站比作一本书。假设你走进书店，店员得先知道这本书讲什么，才知道该把它放在哪个书架上，以及什么情况下应该推荐给用户。

- **放书架哪一层，等于 SEO 搜索排名**

- **店员优先推荐你，等于 GEO 推荐排名**

![书店类比 — Entity 是书的身份证](https://bysocket.com/images/geo-entity-topical-weight/01-bookstore-entity.png)

比如，做一个网站是教人做菜的，也会介绍各种厨具。但**同样是做菜，教普通人在家做饭、教食堂做大锅菜、教酒店厨师做菜，定位就很不一样**。

如果你的网站主要教家常菜，那就要把身份说清楚：这是一个教普通人在家做好日常饭菜的网站。介绍厨具，也围绕这个用途展开。

这就是 Entity 定义要做的事：**让这个店员（AI 模型）明白，你这本书讲什么、适合谁**。这样，当有人问 "下班后做什么菜简单又好吃" 时，它才更容易想到你这本书。

因为 AI 和 SEO 实现的底层机制，是离散数学领域的 Knowledge Graph，是 2012 年 Google 提出的，所以先定义好 SEO Entity（决定边界）。

那记住 Entity 其根本目的是：**让网站的内容符合 SEO 和 AI 的实体识别机制**

**决定了 SEO & GEO 后续执行当中，决定了网站主题的选择边界**

## 二、如何 Research & 定义 Entity？

**整个流程就简单了，先研究真实业务，再定义市场身份，最后明确 SEO 或 GEO 内容边界**

具体来讲可以在品类定位模糊时，第一步可以**参考竞品对应的首页定义和其产品、功能、use case 页面**

下一步，**具体看自己的产品文档、客服反馈、用户访谈等等作为一手信息为依据**

总结后用这四个问题**定义主 Entity**：**我是谁、我提供什么、我服务谁、我不覆盖什么。**去分别明确实体与主品类、产品与能力及功能、目标用户与使用场景，以及应排除的方向

![Entity 四问框架 — 锁定网站身份](https://bysocket.com/images/geo-entity-topical-weight/02-entity-four-questions.png)

其中，注意排除项重点识别看似相关、却会误导定位或模糊业务身份的方向

其中，也注意不能因为搜索量高就纳入

以早期 AI 产品 **heygen** 为例：

- **我是谁：** heygen，一款 AI Marketing Video 工具，帮助品牌制作营销视频

- **我提供什么：** 将商品链接或素材转成视频，支持脚本生成、AI 配音、自动字幕和多尺寸导出

- **我服务谁：** 电商品牌、广告投手和小型营销团队，用于新品推广、社媒广告和广告素材测试

- **我不覆盖什么：** 电影级视频制作、通用专业剪辑、广告投放管理，以及与营销无关的 AI 视频创作

对，这个**定义也需要随着品牌做大，一起升级**！升级过程中，如果**存在真实子产品时，类似主 Entity，才建立子 Entity**。

比如 Ahrefs 早期定位 - SEO Tools，现在定位 - AI Marketing Platform。如下图

2022 年：

![image.png](https://bysocket.com/images/geo-entity-topical-weight/03-ahrefs-2022.png)

2026 年：

![image.png](https://bysocket.com/images/geo-entity-topical-weight/04-ahrefs-2026.png)

## 三、主题跟 Entity 的关系

上面的 Entity 定义好后，其实 Topical Map 已经有了部分了。如图所示：

![image.png](https://bysocket.com/images/geo-entity-topical-weight/05-topical-map.png)

这里就可以定义出主题和子主题，比如 heygen 这个例子：

ai marketing video

- product url to ads video

- product image/assets to video

- video hook/script generator

- …

这里主题和子主题构成了，这个站（Entity）的主题地图（Topical Map），是我们站后续的内容规划路线图。

其核心功能是将网站上的内容按照主题和子主题的层次结构和按内容优先级创作

那 Topical Map 和 Entity 的关系是什么？

**Topical Map 是根据上面 Entity 的边界，决定长期覆盖哪些主题。就像一本书的书名和大纲的关系，书名=Entity，大纲=Topical Map**

上面说了 Entity 其根本目的是：**让网站的内容符合 SEO 和 AI 的实体识别机制**

那 Topical Map 的根本目的是什么？

**它是在满足用户体验的前提下，向 SEO 和 AI 表明，你的内容全面涵盖了该实体的所有方面**

## 四、如何 Research 更多主题

这里很多人会有个疑惑，感觉子主题很少。其实不是的，第二个难点就是这里的 Research 相关主题。跟 Keyword Research 难度差不多吧，大步骤分两步：

- 主题收集

- 主题评估

### 4.1 主题收集

外部的话，可以通过：

- **ChatGPT 等 AI 工具**：根据已经明确的 Entity，推荐相关主题和子主题

- **Ahrefs**：通过相关关键词拓展，也可以查看竞品覆盖了哪些主题

- **Wikipedia**：查看对应主题的介绍、目录和关联词条，寻找子主题。比如围绕视频制作，可以找到脚本、开场 Hook、字幕、剪辑等

- **Google 下拉框、People Also Ask、Reddit、Quora 等**：看看用户实际在搜什么、问什么、讨论什么

- **AnswerThePublic**：围绕一个主题，进一步收集用户可能会问的问题

![all categories-best ai video generator-en-us-23-07-2026.png](https://bysocket.com/images/geo-entity-topical-weight/06-answerthepublic.png)

内部的话，可以来自：

- **产品文档、帮助中心**：产品能解决哪些问题，哪些功能需要解释

- **用户访谈**：用户想完成什么，实际操作时卡在哪里

- **客户反馈、客服工单、在线聊天记录**：哪些问题反复出现，哪些地方容易让人误解

- **客户邮件、售前咨询邮件**：客户购买前会问什么，使用后又有哪些疑问

- **销售沟通记录、产品演示记录**：客户最关心哪些能力，会拿你和谁比较，为什么买或不买

- **站内搜索记录**：用户进入网站后，还在主动找哪些信息

- **用户社群里的讨论**：用户分享了哪些用法、需求和解决办法

- **退订、退款和流失原因**：用户有哪些期待没有被满足

- **团队的实操经验和客户案例**：有哪些亲自解决过的问题、踩过的坑和验证过的方法

**先把这些主题收集起来，作为候选池**。后面进行下一步主题评估。

### 4.2 主题评估

这块很简单根据 Entity 的定位和边界，判断哪些值得做、哪些不该做。可以按照「商业价值」x「品牌相关度」去筛选确定：

其中「品牌相关度」可以通过 Entity 定义完后让 AI 给你建议，自然也要人工 Review 下

其中「商业价值」可以参考 Ahrefs 等平台，对于主题的 Traffic Value 值和其下长尾词数量+总流量。如下图：

![image.png](https://bysocket.com/images/geo-entity-topical-weight/07-traffic-value-1.png)

![image.png](https://bysocket.com/images/geo-entity-topical-weight/08-traffic-value-2.png)

## 五、小结

![端稳自己的菜 — 不是所有流量都是你的菜](https://bysocket.com/images/geo-entity-topical-weight/09-own-your-dish.png)

**这里做 SEO 和 GEO，第一件事不是找词，是先搞清楚"你是谁"**

**Entity 定义就是给你的网站发一张身份证，告诉搜索引擎和 AI：我是干这个的，别把不相干的流量往我这儿塞**

**定义清楚边界之后，Topical Map 才有骨架，内容才知道往哪长，不会东一榔头西一棒子**

**说到底，Entity 是书名，Topical Map 是大纲，内容是正文。书名起歪了，后面写得再多也是废纸**

最后记住一句话：**不是所有流量都是你的菜，先把自己这盘菜端稳了，再谈上桌**

sources:

- Joker 年更最新文章 - 「SEO 的下一次进化：内容，外链，品牌，到底需要进化成什么」

  [https://mp.weixin.qq.com/s/ESPeoAGt5TToZrXqVItDyw](https://mp.weixin.qq.com/s/ESPeoAGt5TToZrXqVItDyw)

- Ahrefs 好文章「How to Build an SEO Topical Map (With Template)」

  [https://ahrefs.com/blog/seo-topical-map/](https://ahrefs.com/blog/seo-topical-map/)
