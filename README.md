# Vibe Coding Learning

一套面向真实软件工程的 AI Coding 学习仓库。

这里不把 **Vibe Coding** 理解成“会用 Cursor / Claude Code / Codex 写代码”，而是把重点放在：

- 如何把模糊想法变成可验证的软件设计；
- 如何在已有项目（brownfield）中使用 AI，而不是越改越乱；
- 如何比较多个候选方案，而不是过早收敛到一个答案；
- 如何决定 **自研 / 复用 / 借鉴 / 删除**；
- 如何研究一个开源项目，不只停留在 README；
- 如何建立 spec、计划、测试、验证、review 与迭代闭环；
- 如何让 AI 保留执行速度，同时把架构判断权留在人手里。

> 目标：从“让 AI 帮我写代码”进阶到“能够设计、约束、审查和改进 AI 参与的软件工程流程”。

## 学习地图

本仓库按 6 个阶段推进：

1. **AI Coding 基础工作流** — 理解 agent、上下文、计划、实现和验证的基本分工。
2. **Spec-Driven Development** — 学习从 what/why 到 plan/tasks/implementation 的完整链路。
3. **Brownfield Engineering** — 学习如何先理解已有系统，再做修改。
4. **Architecture Exploration** — 学习如何建立候选方案、比较 trade-off、避免局部最优。
5. **Evaluation & Verification** — 用测试、benchmark、review 和 adversarial validation 判断方案是否真的更好。
6. **Real Project Practice** — 把整套方法应用到一个真实项目模块上。

详细计划见 [Learning Roadmap](docs/learning-roadmap.md)。

## 核心资料

优先学习官方/一手资料：

- [GitHub Spec Kit](https://github.com/github/spec-kit)
- [Spec Kit Documentation](https://github.github.com/spec-kit/)
- [Anthropic: Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices)
- [OpenAI: Running Codex safely at OpenAI](https://openai.com/index/running-codex-safely/)
- [AWS SpecShip](https://github.com/aws-samples/sample-specship)
- [Harper Reed: My LLM codegen workflow](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/)
- [Kent Beck: Augmented Coding — Beyond the Vibes](https://kentbeck.com/summaries/augmented-coding-beyond-the-vibes/)

完整资料见 [Resources](docs/resources.md)。

## 不是“收藏链接”

每个资料都应该至少回答：

1. 它解决什么问题？
2. 它的完整工作流是什么？
3. 它依赖哪些假设？
4. 它有哪些失败模式？
5. 哪些能力来自模型，哪些来自流程约束？
6. 哪些部分值得直接使用？
7. 哪些部分只值得借鉴？
8. 哪些部分不适合我的项目？

不要只看 README。对进入核心工作流的项目，继续阅读：

```text
README / Docs
      ↓
API / Config
      ↓
Source
      ↓
Tests
      ↓
Issues / PRs
      ↓
Commit history / evolution
      ↓
Own benchmark
```

使用 [Resource Review Template](templates/resource-review.md) 做记录。

## 推荐学习节奏

默认是 **8 周主线 + 持续实战**，每周约 4–7 小时。

学习不是“读完资料”，每一阶段都要产生一个可复用产物：

- workflow map
- spec
- architecture options
- benchmark
- ADR
- review checklist
- 实际 PR

## 学习原则

- **Outcome before implementation**：先定义结果，再讨论技术。
- **Evidence before preference**：用测试、源码、issue、benchmark，而不是“感觉更优雅”。
- **Explore before converge**：架构早期先展开设计空间，再推荐。
- **Brownfield is not greenfield**：已有代码是约束和证据，不是天然正确的前提。
- **Prefer deletion over layering**：新增一层前先问能否删除旧层。
- **Use mature capabilities deliberately**：先理解依赖已经提供什么，再决定是否自研。
- **Verification is part of implementation**：代码能运行不等于任务完成。
