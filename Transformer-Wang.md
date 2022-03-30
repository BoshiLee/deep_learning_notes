# Transformer

[![hackmd-github-sync-badge](https://hackmd.io/Ztsn8y-HRR-6WMUXAZzH4A/badge)](https://hackmd.io/Ztsn8y-HRR-6WMUXAZzH4A)

![](https://i.imgur.com/TadEDUM.png)

Transformer 只有 attention 以及全連接層

再看一下如何計算 α (Wk, Wq 是參數要經過訓練)

![](https://i.imgur.com/b4uGt2t.png)


![](https://i.imgur.com/MRioGZc.png)

## 移除 RNN 的 seq2seq

- Key 向量與 Value 向量
![](https://i.imgur.com/tpEZO6N.png)

- Query 向量

![](https://i.imgur.com/xtwT5l8.png)

- 計算權重

轉置 k 與 q 向量相乘再取 softmax

![](https://i.imgur.com/IBFtV30.png)

- 計算 context

V 乘上權重 α

![](https://i.imgur.com/SVMA8D4.png)


- 利用產生的 contenxt 接上全連接層分類器，產生下一個單字

![](https://i.imgur.com/AevcEdV.png)

可以看出 transformer 是利用 C 作為特徵向量

## Attention Layer

- Input
輸入原文 X
翻譯的文字 X'
- Parameters
Wq, Wk, Wv
![](https://i.imgur.com/qAreUib.png)


## Self-Attention

- Input
兩個都一樣是X
- Parameters
- Wq, Wk, Wv

### 計算步驟:

1. 先把 x 映射到 Q, K, V

![](https://i.imgur.com/VenKWCQ.png)
![](https://i.imgur.com/KLcJDkG.png)

2. 計算 α 

α1 依賴 q1 以及所有 k 

![](https://i.imgur.com/F3uPfJL.png)

以此類推

![](https://i.imgur.com/6kU9MSu.png)

3. 計算 c

將對應輸入所有的 α 與 v 相乘後得到 c，假設是 x1 的，就要先計算出所有的 α 再將每個輸入的 v 相乘後再相加
![](https://i.imgur.com/q3HsVdg.png)


![](https://i.imgur.com/khUX2w6.png)

## Self-Attention Layer

![](https://i.imgur.com/4WVNlz6.png)

## Summary

![](https://i.imgur.com/TabK1su.png)
