# Chapter 8 - Feature Importance

## 1. 本章一句话总结

金融模型不能只看 loss，要知道模型到底依赖哪些特征，以及这些特征在样本外是否稳定。

## 2. 对我的系统的意义

Alpha158 和自定义特征很多，必须知道：

- 哪些特征真的有贡献；
- 哪些只是噪声；
- 哪些只在某几年有效；
- 哪些可能是未来函数或代理变量。

## 3. TODO

- [ ] 做 permutation importance；
- [ ] 做分年份 feature importance；
- [ ] 做分行业/市值组重要性；
- [ ] 检查重要特征是否稳定。
