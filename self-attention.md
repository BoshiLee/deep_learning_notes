# Self-Attention

[![hackmd-github-sync-badge](https://hackmd.io/dyYn7HXTTzSrX_6Mn4pHRw/badge)](https://hackmd.io/dyYn7HXTTzSrX_6Mn4pHRw)

這篇的教學改用 RNN 取代原論文的 LSTM 讓理解比較容易，但概念是一樣的

![](https://i.imgur.com/QCJDf3O.png)

Self-Attention 用在單個 RNN 上，取代原本紀錄狀態的公式

![](https://i.imgur.com/lUF4udD.png)

c1 = h0

![](https://i.imgur.com/8UfSAoP.png)

c2 要計算出 α

* α 的算法
![](https://i.imgur.com/w5byHrQ.png)

## 新狀態的計算整個流程

- 計算出 α
![](https://i.imgur.com/JjiwUoj.png)
- 得到新的 c
![](https://i.imgur.com/hH9G47Z.png)
- 再算出新的狀態 h
![](https://i.imgur.com/yqRvMCB.png)


## 總結:

1. self-attention 可以用在所有類型的 rnn 上
2. 關注在有用的單字上

![](https://i.imgur.com/i7t3wsy.png)
