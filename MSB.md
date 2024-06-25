## MSB
#### picoCTF2023

```python
import cv2
import numpy as np

img = cv2.imread("Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png")
h, w, c = img.shape

img1 = np.zeros((h, w, c))
img2 = np.zeros((h, w, c))
with open("ninja.txt", "w") as f:
    for i in range(h):
        for j in range(w):
            for k in range(c - 1, -1, -1):
                if img[i, j, k] >= 128:
                    img1[i, j, k] = img[i, j, k] - 128
                    img2[i, j, k] = 128
                    f.write("1")
                else:
                    img1[i, j, k] = img[i, j, k]
                    f.write("0")

cv2.imwrite("ninja-org.jpg", img1)
cv2.imwrite("ninja-noise.jpg", img2)
```
