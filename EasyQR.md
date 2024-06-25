## EasyQR
#### 2022 澳門CTF比賽-中學組

```python
import cv2
import numpy as np

with open("flag.txt", "r") as f:
    data = f.read()

w = int(len(data) ** 0.5)
x = np.zeros((w, w), dtype=np.uint8)
for i in range(w):
    for j in range(w):
        x[i, j] = int(data[i * w + j]) * 255

cv2.imwrite("qrcode.jpg", x)
cv2.imshow("x", x)
cv2.waitKey(0)
```
