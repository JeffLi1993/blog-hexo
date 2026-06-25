---
title: 从 0 到 1 构建一个复杂 Agent Skill？一张表就够了
date: 2026-06-25 12:00:00
header_img: https://bysocket.com/images/agent-skill-table/header-img.webp
tags:
  - Agent
  - AI
categories:
  - AI
---

最近写了个几个复杂 Agent Skill，还在细细打磨中，除了 SEO Audit Agent Skill

[github.com/JeffLi1993/seo-audit-skill](http://github.com/JeffLi1993/seo-audit-skill) 已经开源。其他还在 v0.1 版本打磨中

![image.png](https://bysocket.com/images/agent-skill-table/01-header.webp)

但其实搞 Agent Skill 真没那么玄乎。拆开来看就三层：

- **SKILL.md** 告诉模型什么时候用、按什么步骤走

- **scripts/** 模型搞不定的，交给脚本

- **references/ + assets/** 稳定参考 + 静态资源，用到才加载

简单任务一个 SKILL.md 搞定，有时候也不需要 Agent Skill，**不要为了 Skill 而 Skill。**

但复杂任务呢？比如让 AI 自动生成一份洞察月报：数据库字段要对、图表 logo 色号不能错、结论要站得住。你光靠 Markdown 指令去控，控不住的。模型会编数据、搞错格式、画出来的图表颜色跟品牌色差十万八千里。

重点不是写更多指令。重点就一个：**你哪些步骤让模型上，哪些步骤用脚本锁死。**

## 一、模型 vs 脚本：什么时候让谁上

先记住两句话：

**模型擅长的**：理解自然语言、归纳总结、写通顺的文字、判断异常、应对边界情况。

**模型搞不定的**：精确计算、格式一致性、公司品牌规范、结构化数据查询、图表样式。这些模型会**幻觉。**它猜一个觉得合理的答案，但那个答案不对。

| 场景 | 模型做 | 脚本做 |
| --- | --- | --- |
| 写一段报告分析文字 | ✅ 能做，而且做得不错 | 没必要 |
| 从数据库拉上个月销售数据 | ❌ 可能编数据、编字段名 | ✅ 一行 SQL，100% 准确 |
| 生成一张带公司 logo 和品牌色的图表 | ❌ 颜色、字体、布局几乎必错 | ✅ matplotlib/ECharts 模板，次次一致 |
| 判断数据有没有异常波动 | ⚠️ 能做但不稳定 | ✅ 阈值规则，可复现 |

**核心判断标准：**

**凡是看了不满意会让你重做的东西，用脚本锁死。凡是换一种说法也行的东西，交给模型**

**别老想着让模型什么都能干，真不现实**

![图 01：模型 vs 脚本 决策分岔](https://bysocket.com/images/agent-skill-table/02-model-vs-script.jpg)

## 二、一张表格，拆清楚

以「生成符合公司规范的月度经营分析报告」为例，拆五步。每一步标清楚：谁做、要求什么、有什么 Know-how。

| 步骤 | 执行方式 | 要求 | Know-how & 规则 | 产出物 |
| --- | --- | --- | --- | --- |
| 1. 拉取原始数据 | **纯脚本** | 接口地址、字段名、时间范围精确到不能出错；数据量大做分页；出错得报明确错误码 | SQL/API 脚本放 `scripts/`；连接配置从环境变量读，别写死在脚本里 | 结构化数据文件 |
| 2. 指标计算与异常检测 | **模型 + 脚本** | 脚本干所有算数活——环比、同比、达成率；模型只读结果，找值得关注的波动，用自然语言解释 | 计算逻辑写死在脚本里，别让模型推公式；阈值规则放 `references/thresholds.md`；模型出解读，不出原始数据 | 指标结果表 + 异常清单 |
| 3. 图表生成 | **纯脚本** | 品牌色、字体、logo 位置、图表类型全锁死；标题格式、坐标轴刻度、数据标签全固定 | 图表模板放 `assets/`；品牌规范放 `references/brand-guide.md`；一张图表一个脚本，方便单独调 | PNG/SVG |
| 4. 报告撰写与排版 | **模型 + 脚本** | 模型写文字——语气、结构、结论；脚本套模板、插图表、统一格式 | 报告模板放 `assets/report-template.docx`；写作规范放 `references/writing-guide.md`；**脚本管渲染，不管内容** | 完整报告 |
| 5. 质量审核 | **纯模型** | 通读报告，检查数字是否前后一致、图表和文字对不对应、有没有空白或格式错乱、结论能不能站住 | 检查清单放 `references/qc-checklist.md`，逐项核对；发现问题标到审核记录里，别改报告源文件 | 审核记录 + 修订建议 |

你就是个蒸馏员：

![图 02：五步流水线](https://bysocket.com/images/agent-skill-table/03-pipeline.jpg)

## 三、第五步为什么全交给模型

这一步别搞脚本。模型的强项就是读东西、挑毛病。

让它通读脚本产出的报告，对着检查清单一条一条过。这恰好是脚本干不了的事。脚本能检查格式，但检查不出：你这个结论跟前面第三页的数据对不上。

## 四、references/ 放什么

记住一个原则：**稳定、不太变、复杂到模型做参考才能做对的东西**

全塞 `references/`：

- SQL 查询模板

- API 接口文档

- 指标计算公式

- 品牌规范（颜色值、字体、logo 规格）

- 写作规范（报告结构、每段要求、不能说的话题）

- 质量检查清单

- 常见错误及修正

- 等等

模型不是一次性全加载，用到才读。

所以 **SKILL.md 里必须写清楚触发条件**。

比如当需要判断异常阈值时，读 `references/thresholds.md`。

**别甩一句 see references for details，那等于没写**

![图 03：references 按需加载](https://bysocket.com/images/agent-skill-table/04-references.jpg)

## 五、小结

别闷头往 SKILL.md 堆 Markdown。

复杂 Agent Skill 的核心就一件事：拆**步骤，然后给每一步分配合适的执行者。**

- 模型干推理和表达

- 脚本干计算和渲染

- references 存规则和模板

一张表格说清楚。表有了，写 SKILL.md 和脚本都只是执行。

![图 04：三合一总结](https://bysocket.com/images/agent-skill-table/05-summary.jpg)

最后把这个表格，告诉 CodeX 或 CC 按照

[agentskills.io](http://agentskills.io) 官方 Skill 标准从 0 到 1 创建这个 Skill 即可。
