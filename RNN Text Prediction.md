# RNN Text Prediction

![](https://i.imgur.com/sLApW9F.png)

1. 把每一個字母當作是一個輸入，經過 RNN 後接上 Softmax 輸出一個機率分布的表，輸出機率最高的字母。

2. 再將前面的輸出結果當作輸入，輸出新的字母，直到結束

## 訓練方式

1. 輸入長度設定為 40，所以到 `i`, `a` 為預測的標籤

![](https://i.imgur.com/NudE7Ta.png)

2. 步長設定為 3 ，從 h 開始包含中間的空格,到最後一個空格，藍色 i 為標籤

![](https://i.imgur.com/HiovdTv.png)


3. 訓練的數據為片段加上標籤的配對
![](https://i.imgur.com/iSidZTW.png)


## 搭建網路

![](https://i.imgur.com/cBrGKdD.png)


## 訓練網路

![](https://i.imgur.com/uArABlJ.png)

## 生成文章
先給一段句子 `seed` 給網路，機器會生成下一個字母，再把這段句子丟回網路如此反覆。
![](https://i.imgur.com/B9xYg7O.png)
