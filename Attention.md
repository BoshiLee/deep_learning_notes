# Attention

原本的 Seq2Seq 在輸入超過 20 個字的時候，表現就會越來越差

![](https://i.imgur.com/wTm1j1N.png)

加入了 Attension 後再超過 20 個字表現也不會變差

![](https://i.imgur.com/hVYZvfs.png)

* [BLEU Score](https://zh.wikipedia.org/zh-tw/%E9%9B%99%E8%AA%9E%E6%9B%BF%E6%8F%9B%E8%A9%95%E6%B8%AC?msclkid=a0953856afcd11ec85b5d3f7c1e89d0a)

## Attention 的性質

![](https://i.imgur.com/M4fjSCc.png)

* 會往回看之前的狀態，這樣就不會忘記
* 可以告訴 decoder 應該注意哪些特徵
* 會多很多計算

## 計算權重

每一個狀態都有對應的 α, m 個狀態就有 m 個 α

![](https://i.imgur.com/UnUmJnf.png)

方法 1. 
![](https://i.imgur.com/TAJ8qdg.png)

矩陣 w 與 v 都是要經過訓練的參數

![](https://i.imgur.com/NtyTy33.png)

再把所有權重經過 softmax

方法 2. 目前較為常用，並且被 transformer 採用，transformer 模型是目前 NLP 的 state of art

![](https://i.imgur.com/w5byHrQ.png)

輸入還是 (hi, s0)

1. 先求出 ki 與 q0, Wk、Wq 都是需要訓練的
2. 算出 ki 與 q0 的內積
3. 再把所有權重經過 softmax


算出所有權重 α 回到上一頁，與 rnn 的每一個狀態 h 求和得到 c0 (context vector)

![](https://i.imgur.com/oEnXXal.png)

往下到 decode，原本求 s1 的方式在左上

![](https://i.imgur.com/6yPITKQ.png)

現在多了 context ，再把它做合併得到 s1

![](https://i.imgur.com/WoKjXHQ.png)

新的輸出產生 s1 再往回重新計算 h1~hm 與 s1 的新 α (注意不能使用舊的 α )，將所有權種 α 相加得到 c1, c1 再去 decoder 計算 s2 如此往復，直到節結束。

![](https://i.imgur.com/g2UIof8.png)

## 視覺化 Attention

顏色較深代表關聯性越強

![](https://i.imgur.com/FgOAI3D.png)


## 總結

![](https://i.imgur.com/ApWYsJY.png)


## 課程資訊

[Youtube](https://www.youtube.com/watch?v=XhWdv7ghmQQ&list=PLvOO0btloRnuTUGN4XqO85eKPeFSZsEqK&index=8)

[Github](https://github.com/wangshusen/DeepLearning/tree/master/LectureNotes)