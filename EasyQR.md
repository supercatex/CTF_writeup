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

```python
from qreader import QReader
import cv2

qreader = QReader()
image = cv2.cvtColor(cv2.imread("qrcode.jpg"), cv2.COLOR_BGR2RGB)

decoded_text = qreader.detect_and_decode(image=image)
print(decoded_text)

# Zero Width Characters
# https://mayadevbe.me/posts/projects/zw_steg/
# https://330k.github.io/misc_tools/unicode_steganography.html

```
