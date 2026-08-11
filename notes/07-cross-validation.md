# Chapter 7 - Cross-Validation in Finance

## 1. 本章一句话总结

金融数据不能随便 KFold，时间顺序、标签重叠和信息泄露会让验证结果虚高。

## 2. 我当前系统需要重点检查

| 问题 | 检查点 |
|---|---|
| 随机切分 | 是否用了随机 train/test split？ |
| 时间泄露 | 训练集是否看到验证集未来信息？ |
| 重叠标签 | 未来 N 日 label 是否导致训练/验证事件重叠？ |
| embargo | 验证集前后是否需要留空窗口？ |

## 3. 初步改进方案

```text
按年份 walk-forward：
训练集: 过去若干年
验证集: 后续一段
测试集: 再后续一段

如果 label horizon = N：
训练集和验证集边界至少 purge N 个交易日。
```

## 4. TODO

- [ ] 记录当前数据切分方式；
- [ ] 实现 walk-forward split；
- [ ] 根据 label horizon 加 purge；
- [ ] 加 embargo 参数。
