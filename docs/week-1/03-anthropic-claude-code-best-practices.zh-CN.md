# Anthropic — Claude Code Best Practices：中文学习版

原文：<https://www.anthropic.com/engineering/claude-code-best-practices>

> 本文是学习导读与结构化摘要，不是逐字翻译。文章发布于 2025 年，Claude Code 后续功能持续变化，因此这里更关注工作流原则，而不是固定产品说明。

## 一句话理解

Anthropic 的核心经验可以概括成：**先给 Agent 正确的上下文和边界，再让它探索、计划、编码，并且给它明确的验证反馈。**

## 1. 为什么强调上下文

Coding Agent 必须在真实代码库里工作，它需要知道项目怎么构建、常用命令、核心文件、代码风格、测试方式、Git 约定以及风险边界。

如果每次都重新探索这些信息，会浪费 token 和时间，也增加误判。因此 Anthropic 推荐把稳定项目知识放进类似 `CLAUDE.md` 的项目说明文件。

真正值得学的不是文件名，而是：**把稳定规则与临时任务分开。**

## 2. 权限不是越多越好

Agent 修改文件、执行 shell、操作 GitHub 都会产生真实副作用。因此工具权限应该区分安全可逆的操作、有风险但可审查的操作，以及高风险或不可逆操作。

成熟的 Agent workflow 不是“什么都 allow”，而是明确哪些事情可以默认执行、哪些事情必须停下来确认。

## 3. Explore → Plan → Code → Commit

### Explore

先让 Agent 读相关文件、URL、图片和现有实现，并明确告诉它先不要写代码。目的不是拖慢开发，而是防止“理解 20% 就立即实现 80%”。

### Plan

在已有事实基础上制定方案，回答要改哪些模块、为什么、顺序是什么、如何验证、哪些地方仍不确定。

### Code

计划明确后才开始修改。

### Commit / checkpoint

小步形成 checkpoint，使错误更容易定位，也方便回退。

## 4. TDD 工作流

一个典型流程是：根据期望行为写测试 → 运行并确认失败 → 固定测试 → 实现代码 → 反复运行直到通过 → 独立检查是否只是迎合测试。

关键思想是：**验证机制最好在实现之前就存在。**否则 Agent 既写答案，又自己定义什么算正确，很容易失去约束。

## 5. Context 也会变脏

长会话会不断累积无关文件、旧讨论、错误尝试、失效假设和大量命令输出。上下文越来越大，不等于模型越来越懂项目。

真正长期有效的信息应该写入文件、issue、计划、ADR 或项目 instructions，而不是永远堆在一个聊天窗口里。

## 6. Checklist / Scratchpad

大型任务中，可以把状态写进 Markdown checklist。这样人知道做到哪里，Agent 不容易漏项，会话切换时也更容易恢复。

这与 Harper Reed 的 `todo.md` 有明显共同点：都在把 Agent 的工作状态外部化、持久化。

## 7. Verification

一个强 Agent 必须能看到自己工作的结果，例如 unit test、integration test、typecheck、lint、screenshot、benchmark、log 或 browser automation。

如果 Agent 只能生成，不能观察结果，流程就是“写代码 → 猜测正确 → 结束”。有 feedback loop 后才会变成“写代码 → 执行 → 观察 → 修正 → 再验证”。

## 8. 三篇文章如何汇合

Harper Reed：不要直接 Idea → Code，先 Spec → Plan。

Kent Beck：不要因为 AI 写得快就降低工程标准，保留设计、测试与 review 判断。

Anthropic：不要让 Agent 在错误上下文里盲目执行，先 Explore → Plan → Code → Verify。

共同结构逐渐出现：Understand → Decide → Plan → Execute → Verify → Review / Update。

Week 1 的目标不是宣布这就是最终 SOP，而是开始形成一个判断：**“让模型做”之前，到底还有哪些工作没有完成？**

## 9. 读完后请自己回答

1. 为什么 Anthropic 会建议明确说“先不要写代码”？
2. 项目 instructions 真正解决的是什么问题？
3. 为什么长上下文不等于可靠记忆？
4. 为什么 verification 对 coding agent 如此关键？
5. tool permission 与软件架构有什么共同点？
6. Harper Reed 的 todo 与 Anthropic 的 checklist，本质上是不是同一类东西？

## 10. 迁移题

下一次让 Coding Agent 开始真实任务前，先问三个问题：它现在知道的“事实”够不够？它现在做的“决定”是谁做出的？它完成之后有什么客观信号证明做对了？如果这三个问题答不清楚，通常还没到直接执行的时候。
