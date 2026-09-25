# Kent Beck — Augmented Coding: Beyond the Vibes：中文学习版

原文：<https://kentbeck.com/summaries/augmented-coding-beyond-the-vibes/>

原始长文入口：<https://newsletter.kentbeck.com/p/augmented-coding-beyond-the-vibes>

> 本文是学习导读与结构化摘要，不是逐字翻译。

## 一句话理解

Kent Beck 区分了 **vibe coding** 与 **augmented coding**：AI 可以承担大量代码生成，但工程师仍然对代码质量、复杂度、测试、设计和最终判断负责。

## 1. Vibe Coding 与 Augmented Coding

Vibe Coding 更关注“现在能不能跑”。如果出错，就把错误继续交给 AI，希望下一次生成解决。人可能并不真正关心内部代码。

Augmented Coding 则要求“它不仅能跑，而且代码本身也值得接受”。因此仍然关心实现复杂度、设计、测试覆盖、scope creep、性能和 AI 是否为了过测试而走捷径。

AI 是生成能力的放大器，但不是质量责任的转移对象。

## 2. 为什么 TDD 在 AI 时代反而重要

AI 很擅长让表面结果看起来正确。如果目标只是“测试变绿”，Agent 可能通过改测试、跳过测试、特判样例、增加隐藏复杂度或偷偷改变接口来达成。

因此测试不是答案，而是约束的一部分。更完整的循环是：明确行为 → 写测试 → 确认测试真实失败 → 实现 → 运行测试 → 查看设计与性能 → 决定是否接受。

## 3. 人真正保留的工作

### 判断 scope

AI 很容易顺手多做一些东西。工程师必须判断某个 abstraction、优化或功能是否真的属于当前任务。

### 判断设计漂移

任务做到一半，可能已经偏离最初设计。此时不能因为“已经写了很多”就继续，而要有能力停下来重新设计。

### 不接受“为了通过而通过”

如果 Agent disable test、修改 benchmark、减少检查或绕开边界条件，即使结果变绿，也不代表任务完成。

## 4. AI 改变的是注意力分配

过去很多精力放在语法、API 记忆、boilerplate 和机械实现。AI 可以承担这些工作，于是人的注意力应上移到目标、设计、边界、复杂度、验证与代码审查。

这才是 augmented 的真正含义：不是程序员退出，而是程序员把认知资源放到更高杠杆的位置。

## 5. 与 Harper Reed 的联系

Harper Reed 更强调“如何组织 AI 开发流程”；Kent Beck 更强调“即使 AI 写了大部分代码，什么工程价值不能丢”。

二者共同反对的是：给 AI 一个模糊目标 → AI 生成大量实现 → 能跑 → 接受。

Harper 用 spec / plan 防止早期方向失控，Kent Beck 用设计纪律 / TDD / review 防止执行过程中质量失控。

## 6. 读完后请自己回答

1. Vibe Coding 与 Augmented Coding 的本质区别是什么？
2. 为什么“测试通过”仍不能证明 AI 的实现值得接受？
3. AI 写代码越来越快以后，人为什么反而要更认真 review？
4. 哪些工程判断很难简单交给生成模型？
5. 什么时候应该停止继续修补，而是退回去重新设计？

## 7. 迁移题

回想一次“AI 已经实现了功能，但你后来觉得架构越来越奇怪”的情况。尝试把原因分成：行为问题、代码质量问题、scope creep、architecture drift、测试不足，或者一开始需求就错了。
