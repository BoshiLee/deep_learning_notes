![norm](https://imgur.com/eSLJYA9.jpg)

新的特徵值 Xr = Xr - Xr 在 i 列的平均值 / 標準值

新的特徵值唸作 tilde

可讓所有的特徵值都在 0 上下
![consider](https://imgur.com/vcmnxnQ.jpg)

2.  先在 輸入前作 normalization 接著也可以在 activation function 前或後再做一次 normailztion (z 或者 a 的地方差別都不大)

i. 試算 z tilde 的方法先將其他參數算出來
![](https://imgur.com/puRMjMk.jpg)

ii. 在套入公式
![](https://imgur.com/YAuwE2s.jpg)

3. Batch Normalization, 

在實作上不會將整個 sample 的資料做 normalization 只會對整個 batch 做，比如有 64 比資料在 batch 裡，就只會對那 64 比資料做
![](https://imgur.com/GTtDpb5.jpg)

4. Testing

在實作上不會有一整包的測試資料時，可以用 move average 取代
![](https://imgur.com/BGYH4iq.jpg)

5. 結論

使用 batch normalization 可使 error surface 變得較不崎嶇，使訓練更加容易

延伸的方法：
![](https://imgur.com/KRtf9JX.jpg)