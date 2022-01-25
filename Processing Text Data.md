1. Tokenization (將文章分割成單字)

<img src='https://imgur.com/ZQuN7O3.jpg' width='80%'>
2. Counting Word Frequencied 計算詞頻

建立一個 hash map 將單字當作 key, 頻率當作 value, 只要出現一次就將單字加入 hash map

<img src='https://imgur.com/nc0cLFD.jpg' width='80%'>

統計過後，依照頻率由高到低排列，再把頻率看為 index，目的是保留常用去掉低頻單字

<img src='https://imgur.com/Abq8eEZ.jpg' width='80%'>

去掉低頻詞可以去除名字，或者拼寫錯誤的單字，也可以減少 one-hot vector 的長度，減低 over fitting

<img src='https://imgur.com/t4DWzDK.jpg' width='80%'>

3. one-hot enconding
<img src='https://imgur.com/P7kJ08c.jpg' width='80%'> 
