# Review 修订记录

[REVIEW.md](../REVIEW.md) 是连续主稿。`notes/` 保存各段证明的展开版本，[reading-log.md](reading-log.md) 记录阅读时遇到的问题和推导过程。本页只记主要修订及其来源。

## 主要修订

| 日期 | 内容 | 相关文件 |
| --- | --- | --- |
| 2026-07-13 | 收录原论文，核对书目信息、文件哈希和页数；开始记录系统模型。 | Git 提交 `c696172`；[原文记录](../doc/README.md) |
| 2026-07-15 | 整理 admissible、partial correctness 和 total correctness；重写 Lemma 2。 | Git 提交 `96f351c`；[模型](../notes/problem-and-system-model.md)、[Lemma 2](../notes/initial-bivalence.md) |
| 2026-07-15 | 补写 Lemma 3，分别处理两个事件属于不同进程和同一进程的情况。 | [阅读记录](reading-log.md)、[Lemma 3](../notes/critical-event-extension.md) |
| 2026-07-18 | 补完第 379–380 页的无限执行构造，并把已有内容合为一篇完整 Review。 | [统一 Review](../REVIEW.md)、[无限执行](../notes/infinite-admissible-run.md) |
| 2026-07-23 | 集中完成七项复查：主定理量词、Lemma 1、证明依赖、Lemma 2 的有限前缀、Lemma 3 的配置集合与同进程分支、轮内二价性、消息公平性；同时压缩主稿中的概括性措辞。 | [阅读记录](reading-log.md)、[量词与证明依赖](../notes/quantifiers-and-proof-map.md)、[交换引理](../notes/commutativity.md) |
| 2026-07-23 | 补充 FLP 之后的三条边界线索：partial synchrony、随机化共识和 failure detector。 | [统一 Review](../REVIEW.md)、[相关研究边界](../notes/related-research-boundaries.md) |
| 2026-07-24 | 把主稿改为可独立阅读的版本：删除正文中的仓库跳转和页码链接，补全 Lemma 3 的中间推导，并直接插入两张关键事件关系图和一张公平调度图。 | [统一 Review](../REVIEW.md) |

## 原文对应位置

| 主稿内容 | 原论文印刷页 | 展开笔记 |
| --- | --- | --- |
| 问题、结论与模型 | 374–377 | [问题与系统模型](../notes/problem-and-system-model.md) |
| Lemma 1 与证明依赖 | 377–378 | [交换引理](../notes/commutativity.md)、[量词与证明依赖](../notes/quantifiers-and-proof-map.md) |
| 二价定义与 Lemma 2 | 378 | [初始二价配置](../notes/initial-bivalence.md) |
| Lemma 3、图 2 和图 3 | 378–379 | [关键事件延后](../notes/critical-event-extension.md) |
| 无限非决定执行 | 379–380 | [无限 admissible 非决定执行](../notes/infinite-admissible-run.md) |
| 结论边界与后续研究 | DLS 1988、Ben-Or 1983、Chandra-Toueg 1996 | [相关研究边界](../notes/related-research-boundaries.md) |

## 来源说明

FLP 定理、系统模型和证明均来自 Fischer、Lynch、Paterson 1985 年的论文，本仓库中的中文文字是阅读整理，不是原始结果。

仓库文字的修改者以 Git 记录为准，现有提交中的作者标识为 `f1re-fly` 和 `f1ref1y`。整理统一稿时使用 Codex 辅助核对第 378–380 页、调整结构和检查链接；数学内容仍以原论文及上表页码为准。

以后若修改实质内容，在上表补上改动和对应材料；单纯的措辞或排版调整不用记录。
