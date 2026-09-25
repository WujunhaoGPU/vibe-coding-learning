# Design Workflow

这不是“唯一正确的软件设计法”，而是一套用于防止 AI 与人一起过早陷入局部最优的研究框架。

## 1. Outcome
先写成功结果，不写技术。

错误：
> 用 Docling 做论文解析。

更好：
> 将科研 PDF 尽可能完整、准确、高效地转为 AI 可理解的信息，并让关键科研结论可回到原文验证。

## 2. Reality Model
研究真实输入和失败类型，而不是只研究代码：
- 用户是谁？
- 输入有哪些变体？
- 哪些错误最致命？
- 哪些信息允许缺失，哪些绝不能错？

## 3. Capability Map
只写系统必须具备的能力，不写实现：
- ingestion
- parsing
- structure reconstruction
- chunk/context planning
- AI reasoning
- verification
- presentation

## 4. Current System
再看当前代码，并区分：
- required contract
- useful capability
- implementation detail
- technical debt
- historical accident

## 5. Landscape Research
针对每个能力建立候选空间：

```text
Reuse existing dependency?
Use another project?
Adapt an algorithm?
Build ourselves?
Remove the layer?
```

## 6. Candidate Architectures
至少 3 个真正不同的候选方案。
在推荐前先 steelman 每一个候选方案。

## 7. Premise Challenge
列出隐藏前提，例如：
- 当前 abstraction 必须保留
- 一定需要 chunk
- 每个模块只能一个 parser
- 修改越小风险越低

逐条问：
- 为什么？
- 有什么证据？
- 如果删除会怎样？

## 8. Target Architecture
画出理想目标，不考虑迁移便利。

## 9. Gap / Migration
分析 Current → Target。
迁移层必须有删除条件，避免临时兼容层永久化。

## 10. Eval
在实现之前定义：
- baseline
- metrics
- ground truth
- failure cases
- acceptance threshold

## 11. Implementation
再交给 coding agent。

## 12. Verification & Cleanup
- tests
- benchmark
- review
- architecture alignment
- 删除被替代的旧路径

## AI 使用模式要区分

### Architecture Mode
默认：
> 当前架构只是候选，不具有天然正确性。

### Implementation Mode
默认：
> 已完成架构决策，在现有 contract 下可靠实现。

不要用 Implementation Mode 回答 Architecture Question。
