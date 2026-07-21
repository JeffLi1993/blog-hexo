---
title: 无聊蒸馏自己：长文转爆款社媒帖子 Agent Skill 开源
date: 2026-07-22 05:00:00
header_img: https://bysocket.com/images/content-repurposing-agent-skill/01-case-overview.png
tags:
  - Agent Skill
  - 内容分发
  - AI Agent
categories:
  - Agent Skill
---

> 首先这里特别感谢 ChenChang x.com/changchen_cc 在 WorkShop 中分享 KOL Marketing 中分享了下这个 Viral Content。感谢启发 ～

## 一、先看效果

**Agent Skill GitHub 地址：**

[https://github.com/JeffLi1993/content-repurposing-skills](https://github.com/JeffLi1993/content-repurposing-skills)

实操一个案例：

![image.png](https://bysocket.com/images/content-repurposing-agent-skill/01-case-overview.png)

文章：[https://bysocket.com/seo-link-building-conversion-data/](https://bysocket.com/seo-link-building-conversion-data/)

如上图，等会，给出下面两个结果挺好的：

#### 结果一：

![7cee846a3c92c5a357a6f0817170001b.png](https://bysocket.com/images/content-repurposing-agent-skill/02-result-one.png)

#### 结果二：

![1eae309609520f5444098687d3910821.png](https://bysocket.com/images/content-repurposing-agent-skill/03-result-two.png)

我们选个 Post 2，后会建议你配图方案

![6345b32b34453f06b458a384b74c3a6c.png](https://bysocket.com/images/content-repurposing-agent-skill/04-image-options.png)

你选个配图方案后。将配图 + 文案 自动发布即可！！！

## 二、为什么做这个

做内容的人都知道，写完一篇长文只是开始。真正吃时间的是**分发。**

把一篇 3000 字的博客，拆成适合 LinkedIn、X、小红书的短帖子，还得每个平台调语气、换结构、想 Hook、配图。

我自己做了大半年内容分发，总结下来就两个字：**重复**。

**Agent Skill GitHub 地址：**

[https://github.com/JeffLi1993/content-repurposing-skills](https://github.com/JeffLi1993/content-repurposing-skills)

每次都是同一套动作：

- 从长文里挑出 2-3 个核心观点

- 针对不同平台改写开头（领英要专业叙事，X 要短平快）

- 想一个能让人停下来的 Hook

- 加互动引导和 CTA

- 配一张能传达核心信息的图

80% 的工作是策略性的重复劳动，20% 是对具体内容的判断。

上次做 seo-audit-skill，我用的是 **Script + LLM 双层架构，**脚本跑确定性检查，LLM 做语义判断。

但内容分发这件事不一样：没有 API 可以调，没有 HTML 可以解析，核心全是**策略知识。**什么样的 Hook 能拿到注意力，怎么从一篇文章里提取不同角度，怎么让三篇帖子互不重复又各有分工。

所以这次的思路是：**把策略知识蒸馏成 Prompt，让 Agent 按我的方法论执行。**

![](https://bysocket.com/images/content-repurposing-agent-skill/05-strategy-distill.png)

## 三、它能干什么

给它一篇长文（博客、研究报告、案例分析、产品指南都行），它会输出**3 篇差异化的社媒帖子**，覆盖 LinkedIn 和 X 两个平台。

每篇帖子包含：

- **ICP 推断**：自动判断目标读者是谁（具体到角色、痛点、认知阶段）

- **Hook**：从 5 个候选里评分选出最强的开头

- **Value Content**：源内容支撑的价值主体，不是泛泛总结

- **互动引导**：让读者想评论的问题设计

- **软 CTA**：不硬推，自然过渡到行动

- **置顶/首评 CTA**：带转化链接的评论区内容

**Agent Skill GitHub 地址：**

[https://github.com/JeffLi1993/content-repurposing-skills](https://github.com/JeffLi1993/content-repurposing-skills)

三篇帖子不是同一篇文章的三种改写，而是一个**内容组合**：

| 帖子 | 主要职责 | 典型角度 |
| --- | --- | --- |
| Post 1 | Attention（拿注意力） | 反直觉观点、信念颠覆 |
| Post 2 | Engagement（拿互动） | 框架、清单、决策规则 |
| Post 3 | Conversion（拿转化） | 故事、案例、资源桥接 |

选完帖子后，还会推荐 3 种配图方案，选一个直接生成。

支持中英文。中文模式有专门的**去 AI 化写作规则**——不是翻译英文帖子，而是用中文社媒的原生节奏重写。

## 四、怎么用

两种方式：

### 方式 1：CLI 安装

```bash
npx skills add JeffLi1993/content-repurposing-skills --skill long-blog-to-viral-social-posts
```

### 方式 2：插件安装

```plaintext
/plugin marketplace add JeffLi1993/content-repurposing-skills
/plugin install long-blog-to-viral-social-posts
```

装好后直接对话：

```plaintext
把这篇文章转成 3 条社媒帖子：https://your-blog-url.com/post
```

它会自动抓取内容、清洗、提取、生成。你选一条帖子，它再推荐配图方案，选完直接出图。

## 五、核心设计思路

这个 Skill 和 seo-audit 最大的区别：**没有一行脚本，全靠策略知识蒸馏。**

![](https://bysocket.com/images/content-repurposing-agent-skill/06-no-script.png)

seo-audit 的逻辑是"能用代码确认的就不让 LLM 猜" - robots.txt 存不存在，跑个 HTTP 请求就知道了。但内容分发没有这种确定性检查，核心全是决策：从哪个角度切、Hook 怎么写、三篇帖子怎么分工。

所以我做的事情是：**把自己手动做了上百次内容分发的经验，编码成一套可执行的工作流。**

具体来说，蒸馏了这几层知识：

**1. 原子提取框架**

长文不是拿来总结的，是拿来拆的。我定义了 9 类"内容原子"——Claims、Data、Insights、Frameworks、Stories、Proof、Quotes、Objections、Resources。Agent 先把长文拆成这些原子，再从中组合帖子。

**2. 组合策略**

三篇帖子不能用同一个原子、同一个 Hook 家族、同一种互动机制。这是我反复踩坑总结出来的：如果三条帖子只是换了开头，读者一眼就看出来是同一篇文章的三种包装。

**3. 70/20/10 评分模型**

每篇帖子用 100 分制打分：Attention 占 70（Hook 25 + 观点 15 + 洞察 15 + 模式打断 15），Engagement 占 20，Conversion 占 10。低于 80 分的自动修订。这个权重分配是我观察了大量爆款帖子后总结的——社媒上，注意力就是一切的前提。

**4. Hook 生成流程**

不是直接写一个 Hook，而是先生成 5 个候选，从不同的 Hook 家族里选，然后按张力、好奇缺口、简洁度、ICP 相关性、证据匹配度打分，选最强的那个。

**5. 中文去 AI 化规则**

中文社媒帖子最怕的就是"翻译腔"和"AI 味"。我专门写了一套规则：用中文原生节奏重建句序，不直译英文连接词；保留作者第一人称经验；具体事实优先于抽象判断；干掉重复的二元对比、假洞察标记、讲课式铺垫。

整个 Skill 就是一份 SKILL.md + 两份参考文档（Hook 模板库和平台规则），没有脚本依赖。纯粹靠把策略知识写得足够精确、足够结构化，让 Agent 能按步骤执行。

## 六、项目结构

```plaintext
content-repurposing-skills/
└── long-blog-to-viral-social-posts/
    ├── SKILL.md                          # Skill 定义 + 12步工作流
    └── references/
        ├── hook-templates.md             # Hook 模板库（按家族分类）
        └── platform-rules.md             # LinkedIn / X 平台规则
```

**Agent Skill GitHub 地址：** 

[https://github.com/JeffLi1993/content-repurposing-skills](https://github.com/JeffLi1993/content-repurposing-skills)

## 欢迎交流

这个工具是我自己做内容分发时的效率产物，希望能帮到同样在做内容的朋友。

**如果你：**

- 经常写长文但没精力做分发 - 直接用

- 觉得生成的帖子哪里不对 - 提 Issue

- 有更好的 Hook 模板或平台规则补充 - 提 PR

**开源 + 免费，期待你的反馈！**

**Agent Skill GitHub 地址：** 

[https://github.com/JeffLi1993/content-repurposing-skills](https://github.com/JeffLi1993/content-repurposing-skills)

## 最后说两句

上次 seo-audit-skill 我说的是先手动跑几十个网站，才知道哪些检查该用脚本、哪些该用 LLM。

这次也一样。这个 Skill 里的每一条规则：

原子怎么提取、Hook 怎么评分、三篇帖子怎么分工

都不是我拍脑袋想出来的，是手动做了上百次内容分发，一条条总结出来的。

**蒸馏自己，就是把隐性经验变成显性规则，再把显性规则编码成可执行的工作流。**

这件事 AI 替代不了你。它能执行你的策略，但策略本身得你自己先趟出来。

没有下过苦功夫的人，写不出精确的 Prompt；没有反复踩过坑的人，不知道哪些环节需要约束、哪些地方需要留白。

所以我的建议还是那句话：**先自己做，做到能教别人，再让 AI 帮你规模化。**

![](https://bysocket.com/images/content-repurposing-agent-skill/07-closing.png)

希望这个工具能帮你省点分发的时间，把精力放在写出更好的内容上 🚀

**Agent Skill GitHub 地址：** 

[https://github.com/JeffLi1993/content-repurposing-skills](https://github.com/JeffLi1993/content-repurposing-skills)
