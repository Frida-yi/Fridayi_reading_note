# Chapter 3 - Labeling

## 1. 本章一句话总结

标签不是随便定义未来收益，而是要和真实交易方式、持仓周期、止盈止损、交易成本一致。

## 2. 我当前系统需要重点检查

| 问题 | 检查点 |
|---|---|
| 开盘交易 | label 是否从可交易价格开始计算？ |
| 未来收益 | 是 close-to-close、open-to-open，还是 open-to-close？ |
| 持仓周期 | label horizon 是否和真实调仓周期一致？ |
| 成本 | label 或回测是否扣除了手续费、滑点、冲击成本？ |
| 重叠样本 | 预测未来 N 日收益时，相邻样本是否高度重叠？ |

## 3. 对截面选股的初步想法

如果每日开盘按模型排名调仓，一个更贴近实盘的 label 可能是：

```text
label_t = future_exit_price / next_open_price - 1 - cost
```

而不是简单使用：

```text
close_{t+N} / close_t - 1
```

## 4. TODO

- [ ] 梳理当前 label 公式；
- [ ] 检查信号生成时间和成交时间；
- [ ] 做 close-to-close vs open-to-open vs open-to-vwap 的对照实验；
- [ ] 检查未来 N 日收益的 overlap 问题。

## 5. 3.3 Computing Dynamic Thresholds

1. 对于 3 分类任务的 label，对于不同的股票，或者同一只股票的不同时期，应该以过去收益标准差的指数加权平均作为波动率预期；然后以这个波动率预期为锚点，未来收益超过某个正向阈值则标为 1，低于某个负向阈值则标为 -1，否则标为 0。
