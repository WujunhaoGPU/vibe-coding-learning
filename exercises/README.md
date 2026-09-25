# Exercises

## Exercise 1 — Reverse engineer your own workflow
画出你当前使用 AI 写一个真实功能时的流程。

至少标记：
- 需求从哪来
- AI 什么时候读 repo
- 什么时候做 research
- 什么时候定架构
- 什么时候开始编码
- 谁负责 test
- 谁判断 done

最后指出 3 个最容易“直接开始写代码”的位置。

## Exercise 2 — Four-option architecture study
选择一个真实技术决策。

强制产生至少四个候选：
1. 当前方案继续演化
2. 直接采用成熟依赖
3. 换另一成熟项目
4. 自研 / 删除该层

禁止在完成四个方案的 steelman 前推荐。

## Exercise 3 — Read a dependency like an engineer
选择一个正在使用的核心依赖。

完成：
- docs
- source
- tests
- 10 个 relevant issues
- 5 个 important PR/commits
- 版本演化
- failure taxonomy

写一份 Resource Review。

## Exercise 4 — Brownfield recon
选择一个已有模块。

输出：
- current architecture
- behavior contracts
- data flow
- tests
- assumptions
- technical debt
- “如果从零设计会不会仍然这样做？”

## Exercise 5 — Benchmark before migration
选择一个你想替换的组件，先不要替换。

建立：
- baseline
- candidate A
- candidate B
- dataset
- metrics
- failure cases

跑结果后再决定。

## Capstone
对一个真实功能完整执行：

`Recon → Research → Options → Architecture → Plan → Build → Validate → Cleanup`

最终必须附一份 postmortem：
- 哪些原假设错误？
- 哪个候选方案被高估？
- 哪个 failure mode 事前没想到？
- 下一次设计流程要改变什么？
