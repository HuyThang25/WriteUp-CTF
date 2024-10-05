```python
from Crypto.Cipher import AES
from Crypto.Util.Padding import pad
import sys
from Crypto.Util.Padding import unpad
import base64

def R64decode(cipher):
    cipher = cipher[::-1]
    cipher = cipher.replace("_","E").replace("-","C")
    plain = base64.b64decode(cipher)
    return cipher
key = '87db61d8626cfea8e091d71753d913116f53e49804ff6eb5b7eb69ef5a521ab8'
key = bytes.fromhex(key)
with open("filename",'r') as fname:
    with open("body",'r') as fbody:

        list_file_name = fname.readlines()
        list_body = fbody.readlines()
        for i in range(len(list_file_name)):
            file_name = list_file_name[i].strip('\n')
            body = list_body[i].strip('\n')
            encrypt_data = R64decode(body)

            iv = encrypt_data[:16]
            data = encrypt_data[16:]
            
            cipher = AES.new(key, AES.MODE_CBC, iv)
            plaintext = cipher.decrypt(data.decode("utf-8"))
            output_file = R64decode(file_name).decode('utf8')
            with open(output_file,'wb') as f:
                f.write(plaintext)
```
