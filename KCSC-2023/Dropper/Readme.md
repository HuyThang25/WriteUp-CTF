![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-15%20223428.png)

Đề bài cho ta một file dump của ổ đĩa `evidence.vhdx`. Sử dụng FTK Imager để xem các file bên trong ổ đĩa. Tìm thấy file `twenty.ps1` trong đường dẫn `C:\Users\Public\ChromeUpdate\readme.txt`. 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-17%20001600.png)

Đây là một file MSCF (là một định dạng file nén được phát triển bởi Microsoft). Ta có thể giải nén nó bằng tool 7z.

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-17%20001241.png)

Sau khi giải nén ta được một đoạn script sau:

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-17%20001802.png)

Đây là một đoạn script được mã hoá bằng một vài thuật toán : base64, aes. Để xem ta chỉ cần thay `IEX` thành `echo`. Sau chạy ta thấy nó lại là 1 đoạn mã khác và có vẻ như nó được mà hoá nhiều lần nên ta viết script cho nhanh. Lưu script vào một file là `script.ps1`. Và Chạy đoạn script sau:
```
(Get-Content -Path "script.ps1") | ForEach-Object { $_ -replace "IEX\(", "echo(" } | Set-Content -Path "script.ps1"
(Get-Content -Path "script.ps1") | ForEach-Object { $_ -replace "Invoke-Expression\(", "echo(" } | Set-Content -Path "script.ps1"
.\script.ps1 > .\script.ps1
cat .\script.ps1
```

Cho đến khi ra powershell sau:

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-16%20201505.png)

Decode chuỗi base64 phía trên bằng [Cyberchef](https://cyberchef.org/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)), ta sẽ được một file ảnh:

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-16%20202001.png) 

Mở file ảnh ta sẽ có flag

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-16%20202317.png)
