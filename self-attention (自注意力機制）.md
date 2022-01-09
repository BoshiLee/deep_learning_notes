### 前言
假設網路在每次輸的向量都不一樣，舉例來說語音、文字、圖（graph) 等等都是向量
<img src="https://imgur.com/JMHJn1L.jpg" width="90%"/>

輸出也有可能有以下幾種
n=> n
n=> 1
n=> n'
<img src="https://imgur.com/W6loGEG.jpg" width="90%"/>

這是 focuc 在 n=>n 的問題上，也就是 sequence labeling

如果使用 fully-connect network 來解決的話詞性標記的話，有可能會遇到以下問題

<img src="https://imgur.com/L4R40E6.jpg" width="90%"/>

前面的 saw 是 v. 後面的則是 n.

一種解決方法是將前後文給串起來，但可能沒辦法完全解決問題

<img src="https://imgur.com/EYB0U96.jpg" width="90%"/>

### self-attention
self-attention 是考慮了一整個 sequence 後做出的結果，在輸入給 fully connectnetwork

<img src="https://imgur.com/9K5KmGe.jpg" width="90%"/>

中間那層輸出就是經過 self-attention 對每一個向量考慮後的資訊

在 self-attention 裡的 module ，就是要出一個向量跟其他向量的關聯性

<img src="https://imgur.com/9QtUp44.jpg" width="90%"/>

計算 a 可以將兩個向量相乘上各自的 w 後的結果在用 dot 計算出

<img src="https://imgur.com/fHNVvDw.jpg" width="90%"/>

計算關聯性的方式

<img src="https://imgur.com/OgTbx9n.jpg" width="90%"/>

再把結果經過一個 activate function, 範例是使用 soft-max 也可以使用其他的 function

<img src="https://imgur.com/9EUmNa1.jpg" width="90%"/>

最後要抽取出關聯性的分數，可以使用原始的向量乘上Ｗv 再乘上 a' 得到最後的結果 b

<img src="https://imgur.com/6kJx4Sp.jpg" width="90%"/>

Q, K, V 的算法

<img src="https://imgur.com/io0VXal.jpg" width="90%"/>


<img src="https://imgur.com/OHiDapK.jpg" width="90%"/>

整個架構，輸入為 I, 輸出為 O
 
<img src="https://imgur.com/RmoWzQf.jpg" width="90%"/>

### Multi head 
如果想要求更多的相關性的話，就要有更多組的 q, k, v, 在做 slef attention 的時候同組的會一起做

<img src="https://imgur.com/iLNkxdS.jpg" width="90%"/>

加上 sequence position ，在有些情境來說位置可能是有用的

<img src="https://imgur.com/b6IKYUq.jpg" width="90%"/>
