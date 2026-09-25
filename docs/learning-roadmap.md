# 8 周学习路线

目标不是“学会某个 AI 编程工具”，而是建立一套可以迁移到真实项目的 AI 软件工程方法。

## Week 1 — 从 Vibe Coding 到工程化 AI Coding
学习：
- Harper Reed：My LLM Codegen Workflow
- Kent Beck：Augmented Coding — Beyond the Vibes
- Anthropic：Claude Code Best Practices

重点问题：
- 为什么直接 prompt → code 容易失败？
- 为什么 plan / spec 需要与执行分离？
- 哪些判断应该由人保留？

产出：画出你当前真实开发流程，标出人做判断、AI 做执行、以及最容易失控的位置。

## Week 2 — Spec-Driven Development
学习：
- GitHub Spec Kit README
- Spec Kit: What is SDD?
- Spec Kit Quickstart
- Agentic SDD reference

不要只看文档：继续看 `templates/`、command prompts，以及 `specify → plan → tasks → implement → converge` 之间传递了什么信息。

产出：为一个小功能手动写 `spec.md`、`plan.md`、`tasks.md`，再用 AI 实现并记录 spec 是否真的约束了实现。

## Week 3 — Existing Project / Brownfield
学习：
- Spec Kit existing-project 思路
- AWS SpecShip 的 RECON
- Anthropic 关于先探索代码再实现的实践

重点：
- “尊重现有架构”什么时候是对的？
- “当前架构”什么时候只是历史偶然？
- 如何识别 preserved behavior？
- 如何先 reverse-engineer 再设计？

产出：对一个真实仓库做 Current System Map：modules、data flow、contracts、tests、known constraints、historical baggage、assumptions。

## Week 4 — Architecture Exploration
目标：训练“不要看到第一个可行方案就开始实现”。

对一个架构问题至少提出 4 个非同质方案：
1. 延续现有方案；
2. 使用成熟依赖；
3. 引入另一项目；
4. 自研 / 删除该层。

每个方案必须包含：核心机制、成立前提、优点、缺点、failure modes、维护成本、迁移成本、证据。

产出：完成一份 `architecture-study.md`。

## Week 5 — 如何研究开源项目
顺序：
1. README / Docs
2. API / config
3. Architecture docs
4. Source
5. Tests
6. Issues
7. PRs
8. Commit history / changelog
9. 自己跑 benchmark

实战建议：挑一个正在依赖的核心项目，例如 Docling，研究它最初解决什么问题、架构如何形成、哪些能力已存在但项目没使用、哪些 issue 暴露真实限制、哪些版本发生过 regression。

产出：使用 `templates/resource-review.md` 完成一份完整项目研究。

## Week 6 — Testing / Eval / Verification
学习：
- SpecShip BUILD / VALIDATE
- TDD 与 regression test
- adversarial validation
- benchmark design

重点区分：unit test、integration test、UI/behavior test、benchmark、LLM eval、architecture comparison。

产出：为一个 AI 功能建立最小 benchmark：ground truth、metrics、baseline、candidate、failure cases。

## Week 7 — Agent Workflow & Guardrails
研究：
- project instructions
- AGENTS.md / agent-specific instructions
- skill / workflow / orchestration
- approval boundary
- execution isolation
- reviewer independence

产出：写出自己的 `AI_ENGINEERING_RULES.md v1`，控制在 1–2 页。

## Week 8 — Real Project Capstone
选一个真实模块，不做 toy project。

完整执行：
1. Outcome
2. Reality / current system
3. Capability map
4. Landscape research
5. Candidate architectures
6. Premise challenge
7. Target architecture
8. Migration plan
9. Implementation
10. Evaluation
11. Review
12. Cleanup

最终产出：
- Architecture Study
- ADR
- benchmark
- implementation PR
- postmortem
- “哪些原判断错了？”

## 8 周之后
之后不再“按课程学”，而是把每个真实项目当成训练场：

```text
Question
→ Options
→ Evidence
→ Decision
→ Implementation
→ Eval
→ What changed my mind?
```
