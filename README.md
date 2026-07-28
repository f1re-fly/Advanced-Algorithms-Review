# Advanced-Algorithms-Review

本仓库是对 *Impossibility of Distributed Consensus with One Faulty Process* 的课程 review。最终交付以一份可独立阅读的统一主稿为核心；专题笔记保留证明底稿，阅读日志和修订记录用于追踪研究过程。

## 直接阅读

- [FLP 不可能性定理：论文梳理与证明评述](REVIEW.md) — 完整、连续的主稿
- [Review 修订记录](journal/review-history.md) — 内容变化、来源映射和协作说明

## 论证底稿

- [问题与系统模型](notes/problem-and-system-model.md)
- [主定理的量词与证明依赖](notes/quantifiers-and-proof-map.md)
- [交换引理（Lemma 1）](notes/commutativity.md)
- [初始二价配置（Lemma 2）](notes/initial-bivalence.md)
- [关键事件延后（Lemma 3）](notes/critical-event-extension.md)
- [无限 admissible 非决定执行](notes/infinite-admissible-run.md)
- [初始即停止进程：原文的正向对照](notes/initially-dead-processes.md)
- [相关研究边界：FLP 之后改变了什么](notes/related-research-boundaries.md)
- [提交问题与模型边界](notes/commit-and-model-boundary.md)

## 原始材料与研究过程

- [FLP 原论文](doc/fischer-lynch-paterson-1985-flp.pdf)
- [论文来源与完整性检查](doc/README.md)
- [研究边界](journal/scope.md)
- [阅读记录](journal/reading-log.md)

## 完成范围

主稿覆盖论文的问题定义、系统模型、Lemma 1–3、无限 admissible 非决定执行、原文 Theorem 2 的正向对照，以及 partial synchrony、随机化和 failure detector 三条后续边界。仓库内的原论文副本已核对页数、哈希与页面完整性。最终主稿采用纯文字论证，不使用图片或流程图。
