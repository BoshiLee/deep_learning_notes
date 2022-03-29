# Seq2Seq 模型

多對多的問題，輸入和輸出的長度不固定

## Data

[小規模資料庫](http://www.manythings.org/anki/)

![](https://i.imgur.com/n17LpJ5.png)

## 將字母或單字做 Tokenization

將要翻譯的語言以及目標的語言都要做 Tokenization

![](https://i.imgur.com/oQHzXCi.png)

因每種語言都要自己的單字或者字元
![](https://i.imgur.com/yECUrgM.png)


![](https://i.imgur.com/65BzURV.png)

## 建立原語言以及目標語言的字典

![](https://i.imgur.com/pEcGIgA.png)

![](https://i.imgur.com/5mANELF.png)

將每一個字母轉成一個向量，這樣一個完整的句子就是一個矩陣
![](https://i.imgur.com/geCQLqz.png)

## 建立 Model

Encoder 提取輸入的特徵概括了一整個句子，輸出成 (h, c) 狀態
Decoder 就是類似一個文本生成器 [RNN Text Prediction](/hAkjWNXYRuCykOc-K1KepQ)，跟 RNN 的區別是一開始的狀態，一個是全靈向量，這邊的是上個 Encoder 的輸出結果。

![](https://i.imgur.com/ndcG9mB.png)

利用反向傳播更新 encoder 以及 decoder
![](https://i.imgur.com/4o8g4ym.png)

![](https://i.imgur.com/alw4ZDe.png)
- encoder 是一個英文句子的 one-hotencode 輸入，再輸入到一個或多個 LSTM 層，再將最終狀態當作 decoder lstm 的輸入
- decoder 輸入德語的上半句
- 全連接做下一個字母的預測


## 總結:

![](https://i.imgur.com/Rai10eF.png)

## 優化網路的方案:

![](https://i.imgur.com/840A3Md.png)
