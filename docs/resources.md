# Resources

资料按“学习价值”而不是工具热度组织。

## A. 核心方法论

### GitHub Spec Kit
- Repo: https://github.com/github/spec-kit
- Docs: https://github.github.com/spec-kit/
- SDD: https://github.com/github/spec-kit/blob/main/docs/concepts/sdd.md
- Quickstart: https://github.com/github/spec-kit/blob/main/docs/quickstart.md
- Agentic SDD: https://github.com/github/spec-kit/blob/main/docs/reference/agentic-sdd.md

重点学习：
- what/why 与 how 的分离
- Specify → Plan → Tasks → Implement → Converge
- clarification/checklist/analyze 作为质量门
- greenfield / creative exploration / brownfield 的区别
- templates 和 prompts 如何约束 agent

不要只读 README：重点阅读 `templates/`、命令定义和 existing-project 相关实现。

### Anthropic — Claude Code Best Practices
https://www.anthropic.com/engineering/claude-code-best-practices

重点：
- explore → plan → code
- tests / verification
- context management
- project instructions
- agent 执行纪律

### Kent Beck — Augmented Coding: Beyond the Vibes
https://kentbeck.com/summaries/augmented-coding-beyond-the-vibes/

重点：
- AI 提速与软件设计纪律如何共存
- 人应该保留哪些判断
- 什么时候应该停止生成，重新设计

### Harper Reed — My LLM Codegen Workflow
https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/

重点：
- brainstorm → spec → plan → implementation
- 为什么先形成文本 artifact 再编码

## B. Brownfield / 完整工程流程

### AWS SpecShip
Repo: https://github.com/aws-samples/sample-specship

重点：
- RECON → PLAN → BUILD → VALIDATE → SHIP
- brownfield reverse engineering
- preserved behavior
- sprint contract
- TDD
- independent/adversarial validation
- recovery loop

注意：这是实验性 sample，适合作为完整 workflow 的实现案例，而不是权威标准。

## C. OpenAI / Coding Agent 治理

### Running Codex safely at OpenAI
https://openai.com/index/running-codex-safely/

重点：
- agent boundary
- permissions
- human approval
- telemetry / auditability
- 高风险操作与低风险操作的不同控制方式

## D. 下一批值得研究的对象

这些不是“默认推荐”，而是候选研究对象：
- AGENTS.md 生态
- OpenSpec / SpecDD / SpecD 等 SDD 变体
- obra/superpowers
- gstack
- Aider / Continue / Cline / Roo / Kiro
- SWE-bench / coding agent evaluation
- 各模型厂商关于 agent/tool-use/context engineering 的工程文章

加入本仓库前，应使用 `templates/resource-review.md` 做一次筛选。

## 资料分级

### Tier 1 — 必学
满足至少两项：
- 官方或一手作者
- 给出完整方法而非 tips
- 有源码 / 模板 / tests 可研究
- 能直接改变真实工程流程

### Tier 2 — 深入研究
优秀的开源 workflow / skill / case study。

### Tier 3 — 观点补充
博客、论坛、个人经验。

### Tier 4 — 参考
工具教程、入门视频、零散 prompt 技巧。

不要让 Tier 4 占据主要学习时间。
