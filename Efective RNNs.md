# Effective RNNs 

## Stack RNNs


堆疊 LSTM 層，將前面的輸出作為後面的輸出

![](https://i.imgur.com/4uoPIkm.png)

#### 用 kears 搭建:

![](https://i.imgur.com/kRfJ2cw.png)

#### Model Summary: 

![](https://i.imgur.com/sFkCo99.png)

## Bidirectional RNN
Bidirectional 雙向 RNN ，正向以及反向閱讀都可以知道句子的意義，雙向 RNN 便是利用這樣的方式，建構兩條不同方向的 RNN 最後在合併輸出結果到分類器。

![](https://i.imgur.com/t1MIRCe.png)

#### 使用 Keras 搭建 Bidirectional RNN

![](https://i.imgur.com/pKOWxsU.png)


## Pretrained 預訓練

1. 先找一個與問題相似的資料及做預訓練，訓練好後，只保留 embedding 層
![](https://i.imgur.com/n52YEaH.png)

2. 鎖住 Embedding ，在堆疊這次的網路

![](https://i.imgur.com/w0jRbux.png)

## 總結


- 能用 LSTM 就不要用 RNN
- Stack RNN 適合用在數據集較大的問題
- Pretrain 數據集小的話，如果能用預訓練相似的資料，效果也會很好

![](https://i.imgur.com/wHLmGLu.png)


