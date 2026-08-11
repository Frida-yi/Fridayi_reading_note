# Advances in Financial Machine Learning 读书笔记

> 目标：结合自己的日频截面选股系统，系统学习《Advances in Financial Machine Learning》，把每章内容转化为可落地的研究 checklist、代码实验和系统改造记录。

## 阅读原则

1. 不追求逐字翻译，重点记录：**概念、公式直觉、代码实现、和自己系统的关系**。
2. 每章都要回答三个问题：
   - 这一章讲什么？
   - 对我的截面选股系统有什么用？
   - 我需要修改哪些代码/流程？
3. 不大量摘录原文，避免版权问题；只写自己的理解和必要短句引用。

## 推荐阅读顺序

| 顺序 | 章节 | 主题 | 对我系统的意义 |
|---:|---|---|---|
| 1 | Chapter 3 | Labeling | 标签是否对应真实交易收益 |
| 2 | Chapter 7 | Cross-Validation in Finance | 防止时间泄露和重叠标签污染 |
| 3 | Chapter 4 | Sample Weights | 样本权重、重叠收益、事件重要性 |
| 4 | Chapter 8 | Feature Importance | 判断模型到底靠什么赚钱 |
| 5 | Chapter 10 | Bet Sizing | 模型分数如何转成仓位 |
| 6 | Chapter 11 | The Dangers of Backtesting | 防止回测过拟合 |
| 7 | Chapter 14 | Backtest Statistics | 更严谨地评价策略 |
| 8 | Chapter 2 | Financial Data Structures | 数据重采样、bar 类型 |
| 9 | Chapter 5 | Fractionally Differentiated Features | 保留记忆性的平稳化特征 |
| 10 | Chapter 16 | Machine Learning Asset Allocation | ML 组合配置 |

## 仓库结构

```text
.
├── README.md
├── reading-plan.md          # 阅读计划
└── notes/                   # 分章笔记
```

## 和我的截面选股系统的对应关系

```text
日K数据 → 特征工程 → 标签设计 → 模型训练 → 验证切分 → 排名分数 → 仓位规则 → 实盘交易 → 回测/实盘评估
             ↑          ↑          ↑          ↑          ↑          ↑
             Ch2/5      Ch3        Ch7        Ch8        Ch10       Ch11/14
```
