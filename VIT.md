# VIT (Vision Transformer)

原本的 CNN 分類器，輸入一張圖片，給出一個向量，總合為 1，數值最高為答案:


![](https://i.imgur.com/dNFU6Np.png)

目前 2020 VIT 才剛放在 arxiv 打敗了目前最好的 ResNet，前提是要有足夠大的訓練集

![](https://i.imgur.com/NrM7hx4.png)

VIT 模型就是 Trasnformer encoder 網路，並沒有太大的區別
![](https://i.imgur.com/pfFTS1U.png)

## 準備訓練集

![](https://i.imgur.com/yYkhtM3.png)


劃分圖片，圖片被分成 9 塊 (patches)，以下是沒有重疊的例子:
![](https://i.imgur.com/jCVi2OD.png)
但也可以每塊都有重疊:
![](https://i.imgur.com/frOHtyF.png)

在畫分的時候，可以設定 stride，以及 patch size 這兩個超參數

## 向量化數據集

把每個彩色圖片的 patch 向量化，把張量轉乘向量

![](https://i.imgur.com/fAhgRjQ.png)

把輸出的向量個別接上相同的全連接層，即共享參數 W, b

![](https://i.imgur.com/Oc8Kew6.png)


![](https://i.imgur.com/btYcEd4.png)

再把向量做位置編碼: 
![](https://i.imgur.com/p5LmFeU.png)

這樣一來每個向量包含特徵以及位置訊息

![](https://i.imgur.com/eRhwVlk.jpg)

## 搭建神經網路

最所有的 patches 前加上一個標籤 [CLS] (可參照 [Bert](/9q1Uc29SQuS7v4Rz-goNpQ))，再加上多頭 self-attention 層 [Self-Attention](/dyYn7HXTTzSrX_6Mn4pHRw)

![](https://i.imgur.com/vgWpwy0.png)

## 採用結果

輸出從 C0~Cn 但我們只要看 C0 即可，可以把它想為從圖片提取的向量，用作分類用途，把 C0 接上分類器

![](https://i.imgur.com/KjHdv42.png)

分類器輸出向量 p, 維度等於分類的種類
![](https://i.imgur.com/UzIbMYu.png)

使用 cross entropy 作為損失函數，求梯度可以更新網路參數
![](https://i.imgur.com/a83Aq1H.png)

## 開始訓練

![](https://i.imgur.com/23xz0PI.png)

## 準確率

1. 使用小數據集，表現比 ResNet 差一點
2. 使用中等數據集，表現根 ResNet 差不多
3. 使用大數據集，表現比 ResNet 好一些

![](https://i.imgur.com/1df9UA2.png)

從結論可以得知，小數據集可以用 ResNet，如果有很大的數據集 1 億張圖片以上則用 VIT 
![](https://i.imgur.com/y9FXvlm.png)

###### tags: `Deep Learning`




