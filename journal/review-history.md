# Review 修订记录

[REVIEW.md](../REVIEW.md) 是连续主稿。`notes/` 保存各段证明的展开版本，[reading-log.md](reading-log.md) 记录阅读时遇到的问题和推导过程。本页只记主要修订及其来源。

## 主要修订

| 日期 | 内容 | 相关文件 |
| --- | --- | --- |
| 2026-07-13 | 收录原论文，核对书目信息、文件哈希和页数；开始记录系统模型。 | Git 提交 `c696172`；[原文记录](../doc/README.md) |
| 2026-07-15 | 整理 admissible、partial correctness 和 total correctness；重写 Lemma 2。 | Git 提交 `96f351c`；[模型](../notes/problem-and-system-model.md)、[Lemma 2](../notes/initial-bivalence.md) |
| 2026-07-15 | 补写 Lemma 3，分别处理两个事件属于不同进程和同一进程的情况。 | [阅读记录](reading-log.md)、[Lemma 3](../notes/critical-event-extension.md) |
| 2026-07-18 | 补完第 379–380 页的无限执行构造，并把已有内容合为一篇完整 Review。 | [统一 Review](../REVIEW.md)、[无限执行](../notes/infinite-admissible-run.md) |

## 原文对应位置

| 主稿内容 | 原论文印刷页 | 展开笔记 |
| --- | --- | --- |
| 问题、结论与模型 | 374–377 | [问题与系统模型](../notes/problem-and-system-model.md) |
| 二价定义与 Lemma 2 | 378 | [初始二价配置](../notes/initial-bivalence.md) |
| Lemma 3、图 2 和图 3 | 378–379 | [关键事件延后](../notes/critical-event-extension.md) |
| 无限非决定执行 | 379–380 | [无限 admissible 非决定执行](../notes/infinite-admissible-run.md) |

## 来源说明

FLP 定理、系统模型和证明均来自 Fischer、Lynch、Paterson 1985 年的论文，本仓库中的中文文字是阅读整理，不是原始结果。

仓库文字的修改者以 Git 记录为准，现有提交中的作者标识为 `f1re-fly` 和 `f1ref1y`。整理统一稿时使用 Codex 辅助核对第 378–380 页、调整结构和检查链接；数学内容仍以原论文及上表页码为准。

以后若修改实质内容，在上表补上改动和对应材料；单纯的措辞或排版调整不用记录。
