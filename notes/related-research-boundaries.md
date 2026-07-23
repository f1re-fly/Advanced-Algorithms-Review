# 相关研究边界：FLP 之后改变了什么

Dwork、Lynch、Stockmeyer 在 1988 年的 JACM 论文中提出 partial synchrony。它位于同步系统和完全异步系统之间：系统可能确实存在消息延迟上界和进程相对速度上界，但协议事先不知道这些上界；或者上界已知，但只保证在某个未知的全局稳定时间之后成立。

这条路线没有反驳 FLP。FLP 的调度器可以永远把某些消息拖到任意晚，只要最后仍满足 admissibility；partial synchrony 则限制了这种“永远没有可用时间界”的能力。DLS 的做法可以理解为把安全性和终止性分开看：安全性要能抗住异步前缀，终止性则依赖系统后来进入足够稳定的阶段。

## 引入随机性：概率 1 终止

Ben-Or 的 1983 年 PODC extended abstract 直接把 FLP 放在背景中讨论：完全异步协议无法用确定性方式容忍一个未通知的进程死亡，但可以使用随机选择得到概率式进展。其 crash-failure 共识协议在多数进程持续运行时，以概率 1 达成一致；Byzantine 版本要求更强的进程数量条件，并且作者明确说明这些协议并不追求效率。

这条路线改变的是“确定性协议”这个前提。FLP 的二价构造针对确定性后继：给定配置和事件，后继配置唯一。随机化以后，同一局部步骤可能进入不同概率分支，调度器即使很强，也不能把所有随机结果都固定成同一条确定性路径。结果通常不再是“每条公平执行都在有限步内必然终止”，而是“在规定的 adversary 模型下，以概率 1 终止”。

## 增加故障信息：failure detectors

Chandra 和 Toueg 的 failure detector 模型把“进程是否失败”的信息抽象成一个可能出错的外部提示。1996 年 JACM 论文按 completeness 和 accuracy 描述 detector 的性质，并说明即使 detector 会犯无限多次错误，只要满足合适的最终性质，也能在异步 crash-failure 系统中解决 consensus。随后 Chandra、Hadzilacos、Toueg 进一步研究了解 consensus 所需的最弱 failure detector；在多数正确进程的环境下，论文刻画了足够且必要的失败信息。

## 可放入主稿的判断

FLP 的结论边界可以概括为：只要保持完全异步、确定性、至多一个停止故障、无额外失败提示，并要求所有 admissible runs 都终止，就无法解决共识。后续三条典型路线分别改动其中一个支点：

- partial synchrony 增加最终可用的时间结构；
- randomized consensus 放弃确定性进展；
- failure detectors 增加关于故障的最终稳定提示。

- Cynthia Dwork, Nancy Lynch, and Larry Stockmeyer. “Consensus in the Presence of Partial Synchrony.” *Journal of the ACM* 35(2), 1988, 288-323. MIT PDF: <https://groups.csail.mit.edu/tds/papers/Lynch/jacm88.pdf>；DOI: <https://doi.org/10.1145/42282.42283>。
- Michael Ben-Or. “Another Advantage of Free Choice: Completely Asynchronous Agreement Protocols.” PODC 1983 extended abstract, 27-30. HTML transcription with original PDF link: <https://ying-zhang.cn/dist/1983-ben-or.html>；DOI: <https://doi.org/10.1145/800221.806707>。
- Tushar Deepak Chandra and Sam Toueg. “Unreliable Failure Detectors for Reliable Distributed Systems.” Cornell technical report TR95-1535, 1995; JACM version 1996. Cornell record: <https://hdl.handle.net/1813/7192>；DOI: <https://doi.org/10.1145/226643.226647>。
- Tushar Deepak Chandra, Vassos Hadzilacos, and Sam Toueg. “The Weakest Failure Detector for Solving Consensus.” Cornell technical report TR94-1426, 1994; JACM version 1996. Cornell record: <https://hdl.handle.net/1813/6208>；DOI: <https://doi.org/10.1145/234533.234549>。
