DFIR

`Description`

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/09db83c4-f935-4392-8b48-54385adf190a)


[Link download challange](https://drive.google.com/file/d/15nuNqTT96vZSLWqKu0DRn2pPGEmYT6PZ/view?usp=sharing)

`Solution`

Mục tiêu bài này là chúng ta cần tìm Computer Name, thời gian xem video hack cuối cùng, thời gian đăng nhập sai cuối cùng

*Computer Name*

Computer Name nằm ở mục SYSTEM chỉ cần search để lấy path và chúng ta vào registry explorer lấy computer name

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/814d87f5-bc6c-49fe-90bc-ff43cb76581f)


`Computer Name: DESKTOP-AL3DV8F`

*Thời gian xem video hack cuối cùng*

Mở folder bằng Autopsy và vào mục Web history để tìm và lấy dấu thời gian

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/fb6da168-3c8b-4ef7-995d-66df94d410b5)

Nhưng do lệch múi giờ là UTC+7 và UTC nên ta trừ đi 7h

`->21/05/2023-09:04:13`

`Lần đăng nhập thất bại cuối cùng`

Phần này chúng ta cần biết về registry như phần 1 và thông tin này có lưu ở SAM ném lên RegRipper

![image](https://github.com/hoanga2dtk68/KMACTF2023-lan1/assets/110059218/9400027f-b842-4585-9eb6-fbd1093e0293)


Từ file phân tích ra chúng ta có thể thấy lần đăng nhập cuối cùng của user

`09/05/2023-08:17:51`

`Flag: KMACTF{DESKTOP-AL3DV8F_21/05/2023-09:04:13_09/05/2023-08:17:51}`
