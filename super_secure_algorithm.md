## super_secure_algorithm
#### MOCSCTF 2023 Training

```python
with open("output.txt", "rb") as f:
    enc = f.read()

def decrypt(enc):
    f = lambda x: x ^ 2 + 2 * x - 20
    for c in enc:
        for i in range(256):
            if f(i) == c:
                print(chr(i), end="")
                break

decrypt(enc)
```
