# Chapter 5 - Fractionally Differentiated Features

## 5.6 Stationarity with Maximum Memory Preservation

1. 金融数据往往具有极高的信噪比，直接注入价格信息会导致模型根本无法学习，所以大多数研究工作使用一阶差分（收益率）代替价格信息进行学习。
2. 本章提出，一阶差分在让数据更平滑、容易学习的同时，会损失很多信息。所以可以使用介于不差分和一阶差分之间的分数阶差分来处理数据。
3. 具体做法是：使用 Fixed-Width Window Fracdiff 算法进行模拟差分操作；对于不同的差分 \(d\) 值，找到能使 ADF 检验通过的最小 \(d\) 值，那将会是本数据集最优的差分阶数；此处有一个经验值 \(d = .35\)。
