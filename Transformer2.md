# Transformer-2

[![hackmd-github-sync-badge](https://hackmd.io/sthGPe18TSeByN31P_Q1Gw/badge)](https://hackmd.io/sthGPe18TSeByN31P_Q1Gw)

## Single-Head Self-Attention

一個輸入序列，一個輸出序列，3 個參數

![](https://i.imgur.com/tFw8d9u.png)
 
## Multi-Head self-attention

使用 l 個 self-attention, 總共有 3 * l 個參數

![](https://i.imgur.com/YClDL9F.png)

把每個單頭的 C 堆疊起來就是多頭的輸出



![](https://i.imgur.com/FB4RJZg.png)


## Mulit Head Attention

把每個單頭的 C 堆疊起來就是多頭的輸出

![](https://i.imgur.com/gOVaNKL.png)

## Stacked Self-Attention Layers

把每一個頭的 C 個別連接到同一個全連接乘上同一個參數 Wu 得到 u

![](https://i.imgur.com/PKNX6Z1.png)

依自己的需求搭建多層神經網路

![](https://i.imgur.com/1JKcJsN.png)

## 搭建 encoder 模型
![](https://i.imgur.com/i9SQ2q2.png)

1. 定義一個 block 為 self-attention 加上全連階層
2. 堆疊 6 個 block
3. 輸入和輸出都是一樣大

## 搭建 decoder 模型

![](https://i.imgur.com/QuooX7n.png)

一個 block 裡面有
1. 輸入目標語言的 self-attention 層 + encoder 的 6x Block 輸出
2. Attention 層
3. 全連接層
![](https://i.imgur.com/9JlkaSy.png)

m = 句子長度
t = 已生成目標語言的數量

## 完整的網路

decoder 的每一層都會接到原輸入 (encoder) U 的矩陣，以及上一個 block 的輸出

![](https://i.imgur.com/T42Jysw.png)


**左邊+右邊**就是完整的 `Transformer`

## Transformer 概要

1. 從 Single Head 到 Mutile Head 
    - 每個單頭都有自己的 self-attention 也都有各自的輸出 C
    - 多個 Single-Head 的輸出堆疊起來就是 multi-head

![](https://i.imgur.com/eZXXPrN.png)

2. Encoder of Transformer  就是 6 個 `Block` (多頭 self-attention + 全連接)

![](https://i.imgur.com/nfUNYWB.png)

3. Decoder of Transformer 就是 6 個 `Block` (多頭 self-attention + 多頭 attention + 全連接)

![](https://i.imgur.com/sNa9iX1.png)

## Summary

![](https://i.imgur.com/h2kBcRa.png)
