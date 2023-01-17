# Waiting xor you
---
- Đề bài cho một file Python
![](https://www.bing.com/images/blob?bcid=r-75NVDlaCMF7g)
~~~python  
    
def xor(a: bytes, b: bytes):
    return bytes([a[i % len(a)] ^ b[i % len(b)] for i in range(max(len(a), len(b)))])


flag = b"KCSC{???????????????????????????}"
key = b"??????"
print(xor(flag, key))
#b'>0\x0c,\x1a+:=\x100(5*,\x08*(2<=\x11!> E!\x006Q3VP"'

~~~

~~~py
def xor(a: bytes, b: bytes):
    return bytes([a[i % len(a)] ^ b[i % len(b)] for i in range(max(len(a), len(b)))])


flag = b"KCSC{???????????????????????????}"
key = b"??????"

x = b'>0\x0c,\x1a+:=\x100(5*,\x08*(2<=\x11!> E!\x006Q3VP"'

print(xor(flag,x))
#b'us_oa\x14\x05\x02/\x0f\x17\n\x15\x137\x15\x17\r\x03\x02.\x1e\x01\x1fz\x1e?\tn\x0cio_'
~~~
~~~py

def xor(a: bytes, b: bytes):
    return bytes([a[i % len(a)] ^ b[i % len(b)] for i in range(max(len(a), len(b)))])


flag = b"KCSC{???????????????????????????}"
key = b"us_oaf"

x = b'>0\x0c,\x1a+:=\x100(5*,\x08*(2<=\x11!> E!\x006Q3VP"'

print(xor(flag,x))
#b'us_oa\x14\x05\x02/\x0f\x17\n\x15\x137\x15\x17\r\x03\x02.\x1e\x01\x1fz\x1e?\tn\x0cio_'
~~~
~~~

def xor(a: bytes, b: bytes):
    return bytes([a[i % len(a)] ^ b[i % len(b)] for i in range(max(len(a), len(b)))])


flag = b"KCSC{???????????????????????????}"
key = b"us_oaf"

x = b'>0\x0c,\x1a+:=\x100(5*,\x08*(2<=\x11!> E!\x006Q3VP"'

print(xor(x,key))
#b'KCSC{MONO_IS__WEITINNN_F0R_Y0U##}'
~~~