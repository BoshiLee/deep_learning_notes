# Simple RNN

![](https://i.imgur.com/qhnScBi.png)

ht 的結果是新輸入的狀態加上舊的狀態乘上 A ，之後用激活函數 tanh 讓 ht 的每一個元素都是 1 ~ -1 之間

參數 A 可以透過學習求得
激活函數的作用於 normalization 使得結果不會太大 (Nan) 或接近 0

參數的數量:

`x + ht-1 = h`

![](https://i.imgur.com/A5KADFg.png)

## 用 simple RNN 訓練 IMDB Review Preditction

![](https://i.imgur.com/xUVLVsy.png)

1. Word Embedding: 將詞向量映射到 X，X 的維度由使用者決定，用 cross validation 驗證
2. Simple RNN Layer: 輸入的是 X 輸出的是 h，h 的維度也由使用者決定，用 cross validation 驗證

3. 輸出結果為 ht 代表前面所有輸入的特徵，最後在接上一個分類器
![](https://i.imgur.com/43nyqyR.png)

## 設置超參數: 

![](https://i.imgur.com/bOkm2CU.png)

* vocabulary : 辭典的詞彙數量
* emdedding : 嵌入層的維度
* word_num : 每個電影的評論最大單字數，不到 500 用 zeor padding, 超過則截掉
* state_dim : 狀態向量的維度
* return_sequences: 是否要輸出每一個循環的狀態，否則只輸出最後的狀態

## 模型概要:
![](https://i.imgur.com/qOWVfjj.png)

![](https://i.imgur.com/AjMSXYW.png)

## 訓練模型:

優化器 RMS
損失函數 binary corss entropy

![](https://i.imgur.com/GkekkJI.png)

## 測試模型: 

![](https://i.imgur.com/WELNjG7.png)

## 結論:

驗證結果比單純的全連接層效果好
RNN 適用於較短的句子分析，較長的句子在後面會遺忘掉前面的單字



參考資料:

[RNN模型与NLP应用(3/9)：Simple RNN模型](https://youtu.be/Cc4ENs6BHQw)

[Simple RNN 的文件](https://keras.io/api/layers/recurrent_layers/simple_rnn/?msclkid=6a50b4b6af0611ec807dba22221ac254)

###### tags: `Keras` `Deep Learning`