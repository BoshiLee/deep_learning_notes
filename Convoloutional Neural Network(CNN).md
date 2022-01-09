### 如何將圖片當輸入
1. 彩色圖片的輸入是將每一個 chanel (RGB) 個別展開成一維向量
<img src="https://imgur.com/aMwunue.jpg" width="90%" />

2. 假設把這一維向量丟到 full connect network 裡面將會是非常龐大的計算量，3 * 10^7 個 weight, 參數太大有可能會 overfitting，如何限制彈性是 CNN 的重點
<img src="https://imgur.com/FYTZGpq.jpg" width="90%" />
* 影像辨識不需要 fully connect
3. 我們不需要看到整張圖片，只需要觀察到一些特徵究可以辨識出圖片的內容就跟人類一樣
<img src="https://imgur.com/OB20Te3.jpg" width="90%" />

### 簡化
1. 可以使用小範圍的圖片給一個神經元，例如 3x3x3 的一個`receptive field`
<img src="https://imgur.com/qTbnJWJ.jpg" width="90%" />

2. 通常一個 receptive filed 都會對應一組神經元 (假設是 64 個)，
接著會動一個 stride 到右邊得到新的 field 且 field 跟 field 之間會重疊，避免特徵出現在 filed 之間而沒偵測到，倘若超出圖片範圍則稱為 padding，通常會補 0，重複以上的方法，最後覆蓋到整張圖上面。
<img src="https://imgur.com/dIa3L6G.jpg" width="90%" />
3. 假設有兩個相同特徵的區域，是否可以共享參數
<img src="https://imgur.com/OfMk91l.jpg" width="90%" />
* 共享的參數我們可以稱作為 `filter`
<img src="https://imgur.com/GAkEwbo.jpg" width="90%" />

4. 加上以上的限制後便是我們常說的 `Convolutional Layer` , 專為影像所設計的
<img src="https://imgur.com/wQoqFTb.jpg" width="90%" />

Convolutional Layer 有一整排的 filter 每個 filter 對應到各個區域 
filter 大小：3x3xChanel (黑白為 chanel=1 彩色 chanel=3)

假設 stride 為 1 圓圈則為通過 `Convolutional Layer`  的結果：
ex: 假設第一個 field * filter 

1| 0  | 0 |
-|:-:|-:| 
0   | 1 |  0 | 
0   | 0 |  1 |  

product 

1| -1  | -1 |
-|:-:|-:| 
-1   | 1 |  -1 | 
-1   | -1 |  1 | 
=> 3

<img src="https://imgur.com/FmGlMtr.jpg" width="90%" />

將圖片都乘上對應的 filter 後會得到 `feature map`
<img src="https://imgur.com/q1FHX5I.jpg" width="90%" />

假設有 64 個 filter 經過這層後會變成 64 個 chanel
<img src="https://imgur.com/7BGPjhE.jpg" width="90%" />

5. Pooling- Max Pooling
在每一個區域中選最大的數字，也有其他的 pooling 方法，區域大小也可以自行決定
<img src="https://imgur.com/E2ZIzze.jpg" width="90%" />
pooling 最主要的優勢是可以減少運算量，但近年也有不用 pooling 的 network

### Network 全貌
做完所有的 convoluation 層後經作 flatten （把影像變成向量）後還是要丟到 fully connect network 去學習 
<img src="https://imgur.com/w2WLCyy.jpg" width="90%" />

