`Descryption`

[Link tải challange](https://drive.google.com/file/d/1NviejQAGKBE45m6L260WrZ6_I9icJz1-/view?usp=sharing)

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/c9681743-1073-4473-9f40-e998a8e5302e)

`Solution`

Bài này thật ra theo thói quen bật log Powershell Operational lên đọc thì có 1 đoạn mã tấn công đồng thời chứa luôn flag cần tìm

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/d109b47a-256e-4883-bdaa-77976aae25bc)

Giờ chúng ta cần 3 thứ phải tìm đó là PID của powershell.exe chạy script tấn công, tên user bao gồm cả tên miền nếu có, ngày giờ tấn công

`Get-Date.ToString()`

Phần này là phần có lẽ đơn giản nhất khi có ngay trên log

`5/22/2023 5:09:58 PM`

`PID`

Phần này vào xem log Sercurity để xem nó đã sinh ra PID là bao nhiêu, cái nào sinh ra powershell và căn cứ vào thời gian tấn công là 5h09p chiều

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/ef85f573-b88f-4702-aef7-5e1b8854914e)


phần new process id: 0x1030 chuyển sang decimal là 4144

`Account name-Account domain`

Có ngay ở phần log 4688 bên trên thì lấy được account name: long, account domain: KMA

Tiến hành thay các thông số vào và chạy để lấy flag

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/5cee02d1-dc30-4903-a311-4383ec257bad)

`Flag: KMACTF{0da4ab044b8e929ec9c75bc44d24777e}`
