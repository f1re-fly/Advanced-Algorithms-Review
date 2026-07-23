# 主定理的量词与证明依赖

## 先把命题写开

对任意满足 partial correctness 的确定性共识协议 `P`，都存在一个从 `P` 的某个初始配置出发的 admissible run `R`，使 `R` 中没有进程决定。

```text
∀ P，∃ R：R admissible，并且 R 不决定。
```

## 反证中用了哪些假设

| 假设 | 实际出现的位置 |
| --- | --- |
| 确定性 | 保证配置和 event 唯一决定后继，也支撑不可区分性论证。 |
| Nontriviality | 在 Lemma 2 中保证两种决定值都能出现。 |
| Agreement | 已有进程决定后，配置只能是对应的单价；这在 Lemma 3 和最后的非决定性论证中使用。 |
| 一个故障下的 termination | Lemma 2 和 Lemma 3 都会暂时让某个进程不运行，并据此取得有限 deciding schedule。 |
| 完全异步 | 调度器可以把当前可执行事件延后，不受固定时限约束。 |
| 可靠消息与 admissibility | 最后的反例不能靠丢消息或饿死多个进程完成，必须另证公平性。 |

## 证明依赖

```text
Lemma 1：互不相交的进程步骤可交换
        │
        ↓
Lemma 3：指定事件可在保持二价时执行 ──┐
                                      ├→ 公平调度器的无限轮转构造
Lemma 2：存在初始二价配置 ─────────────┘
                                             │
                                             ↓
                                  admissible 且永不决定的 run
                                             │
                                             ↓
                                   否定 total correctness
```
