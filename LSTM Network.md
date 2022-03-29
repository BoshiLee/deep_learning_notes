# LSTM Network

LSTM 也是一種循環神經網路，但比 RNN 複雜很多

![](https://i.imgur.com/dKUvV4B.png)

LSTM 有一個傳輸帶，可以將過去的狀態傳輸到後面的狀態，利用傳輸帶避免梯度消失

![](https://i.imgur.com/rwlik3j.png)

## LSTM 內部架構

![](https://i.imgur.com/PgsX2DI.png)

![](https://i.imgur.com/IER0TA0.png)



## 使用 keras 搭建 LSTM Network

![](https://i.imgur.com/W5bOB5Q.png)

![](https://i.imgur.com/UofV3Z4.png)


## LSTM Dropout

dorpout 對 lstm 沒有顯著的效果，原因是 overfitting 的原因在於 embedding 層 (320000 個參數) 而不在 lstm 層 (8320 個參數)

![](https://i.imgur.com/k48GvCz.png)

## 總結

LSTM 總是比 RNN 的效果要好，所以想用 RNN 的時候，就直接用 LSTM

![](https://i.imgur.com/zbX5Jzn.png)

###### tags: `Keras`

