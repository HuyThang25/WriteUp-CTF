Code decrypt
```python
from Crypto.Cipher import AES
from Crypto.Util.Padding import pad
import sys
from Crypto.Util.Padding import unpad

for i in range(1,len(sys.argv)):
    input_file = sys.argv[i]
    with open(input_file,'rb') as f:
        read = f.read()
    length_iv= int.from_bytes(read[:4], "little")
    iv = read[4:length_iv+4]
    data = read[length_iv+4:]
    key = '7h3_k3y_70_unl0ck_4ll_7h3_f1l35!'
    key = key.encode('UTF-8')
    cipher = AES.new(key, AES.MODE_CBC, iv)
    plaintext = cipher.decrypt(data)
    plaintext = unpad(plaintext, AES.block_size)
    output_file =input_file[:-4]
    with open(output_file,'wb') as f:
        f.write(plaintext)
```