Đề cho một file `TrivialFTP.pcapng`, sử dụng tool Wireshark để phân tích. Đề bài là `Trivial FTP`, đây là một giao thức để truyền tải các tập tin trong mạng. Nên mình dùng `tftp` để lọc lấy các gói tin tftp. Đọc thêm về [TFTP](https://en.wikipedia.org/wiki/Trivial_File_Transfer_Protocol) để hiểu hơn về giao thức này

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20202159.png)

Follow UDP steam thì thấy vận chuyển file `flag.pdf` mã hoá bằng netsacii. 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20203122.png)

Sử dụng filter `ip.dst == 192.168.25.1` để lọc lấy những gói tin vận chuyển file flag.pdf (vì file này chỉ được chuyển tới địa chỉ 192.168.25.1). Dùng tool tshark để thu thập dữ liệu trong trường data.
```
tshark -nr TrivialFTP.pcapng -Y 'ip.dst == 192.168.25.1' -T fields -e data > data.txt
```
Ở đây mỗi gói udp sẽ được thêm vào 4 byte đầu 
		
		2 bytes opcode. Opcode = 00 03 ở đây khai báo message này là data message.
		2 bytes block number. Khai báo thứ tự của data trong stream.
	
 Ta phải cắt đi 4 byte này. Do sử dụng mã hoá netascii nên ta phải thực hiện bước nữa	

		Chuỗi mã NetASCII: 0D0A chuyển đổi thành mã ASCII: 0A (LF)
		Chuỗi mã NetASCII: 0D00 chuyển đổi thành mã ASCII: 0D (CR)

Mình có viết đoạn script python để giải mã 

```python
with open(r"data.txt",'r') as f:
    data = f.readlines()
fixed_data = ''
for i in data:
    fixed_data += i[8:-1].replace('0d0a','0a').replace('0d00','0d')
with open('flag.pdf','wb') as f:
    f.write(bytes.fromhex(fixed_data))
```

Sau khi chạy ta và mở file pdf ta sẽ thấy được flag

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-07-10%20210901.png)
