<img src="https://imgur.com/wzyAqHl.jpg" width="90%" />

在資料不足的情況下，可以透過歪斜，旋轉、縮小、改變色溫等等的方法去擴充資料

<img src="https://imgur.com/Zuhtx8v.jpg" width="90%" />

<img src="https://imgur.com/4ciVlCH.jpg" width="90%" />

實作方法只要想要做處理的發法加入到 transforms 裡面即可
```python
transform_train = transforms.Compose([transforms.Resize((32, 32)), #將圖像轉換為 32*32

transforms.RandomHorizontalFlip(),

transforms.RandomRotation(10),

transforms.RandomAffine(0, shear=10, scale=(0.8, 1.2)),

transforms.ColorJitter(brightness=0.2, contrast=0.2, saturation=0.2),

transforms.ToTensor(),

transforms.Normalize((0.5,), (0.5,))

]) #把灰階從0~255壓縮到0~1
```