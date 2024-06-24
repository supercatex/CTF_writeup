## crypto-xor2

```
with open("cipher", "rb") as f:
    cipher = f.read()

m = []
# for i in range(26): m.append(ord('A') + i)
for i in range(26): m.append(ord('a') + i)
# for i in range(10): m.append(ord('0') + i)

for k1 in m:
    for k2 in m:
        for k3 in m:
            for k4 in m:
                key = chr(k1) + chr(k2) + chr(k3) + chr(k4)
                flag = ""
                for i, c in enumerate(cipher):
                    flag += chr(c ^ ord(key[i % 4]))

                if "flag" in flag:
                    print(key, ":", flag)
```
