# Trasnformer (台大版)

[![hackmd-github-sync-badge](https://hackmd.io/562UyFDKRLyzWcoucAoX1Q/badge)](https://hackmd.io/562UyFDKRLyzWcoucAoX1Q)


## 應用範圍
Sequence-to-sequence(seq2seq)

輸入是一串向量輸出也是一串向量，例如語音辨識，不能確定每次輸出都是同樣，必須要由機器決定
<img src='https://imgur.com/APlyDH1.jpg' width="90%"/>


ex 聊天機器人：
<img src='https://imgur.com/pE3hhAg.jpg' width="90%"/>


圖像標記：
<img src='https://imgur.com/oeyJtyx.jpg' width="90%"/>

目前 RNN, LSTM, Trasnformer 都是 Seq2Seq

## Transformer 算法過程

1. 使用三個超參數 Wq, Wk, Wv, 將每一個輸入都乘上這三個參數, 得到 Q, K, V


![](https://i.imgur.com/eE6v2pH.png)

2. 得到 Q, K, V 之後將 K 作轉至矩陣得到 A 在對 A 做 softmax 得到 Â, 最後將 Â 乘 V 之後就是單頭的輸出 O


![](https://i.imgur.com/oF53VMB.png)


![](https://i.imgur.com/uKY0WIG.png)

## Multi-head

多頭得算法也是類似，同樣的頭只會對同樣的頭相乘 
ex: 

- qi1 dot ki1 innter vi1 = bi1
- qi2 dot ki2 innter vi2 = bi2
- bi1 concatenating bi2 = O


![](https://i.imgur.com/AaM50jb.png)

## Transformer 動畫

[Transformer: A Novel Neural Network Architecture for Language Understanding](https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html)



![image alt](https://3.bp.blogspot.com/-aZ3zvPiCoXM/WaiKQO7KRnI/AAAAAAAAB_8/7a1CYjp40nUg4lKpW7covGZJQAySxlg8QCLcBGAs/s1600/transform20fps.gif)


## 架構圖

![](https://i.imgur.com/TccY5B2.png)


![](https://i.imgur.com/kgjpRfG.png)


![](https://i.imgur.com/a0jnekO.png)


- Batch norm 對整包資料做 norm, Layer 只有對這個 layer 的所有輸出做 norm


![](https://i.imgur.com/naxLcJA.png)

## Visualization

![](https://i.imgur.com/aO9FWbS.png)

###### tags: `Deep Learning`
