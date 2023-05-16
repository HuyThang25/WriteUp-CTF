![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-05-15%20223428.png)

Đề bài cho ta một file dump của ổ đĩa `evidence.vhdx`. Sử dụng FTK Imager để xem các file bên trong ổ đĩa. Theo thói quen tìm file evtx chứa powershell đã chạy và thấy nó trong đường dẫn `C:\Windows\System32\winevt\logs\Microsoft-Windows-PowerShell%4Operational.evtx`

Lưu script vào một file là `script.ps1`. Và Chạy đoạn script sau:
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
