#  Forensics tổng quan

## File Forensics (File Formats)

 File Signature
A typical file signature is something which defines the nature of a file and also tells us about the specific features of the particular file. This is also called as the file header or sometimes as the checksum.
Chunks are nothing but fragments of information used by different multimedia formats like PNG, MP3 etc. Each chunk has its own header. The header usually describes the type and size of the chunk.


## Network Forensics
Là một nhánh của điều tra số liên quan đến việc theo dõi, giám sát, phân tích lưu lượng mạng máy tính nhằm phục vụ cho việc thu thập thông tin, sự kiện liên quan,để phát hiện sự bất thường, các dấu hiệu xâm nhập trên môi trường mạng.
Các công cụ phổ biến :
- Wireshark, Network Miner bắt và phân tích gói tin với giao diện đồ họa
- Tcpdump phân tích gói tin với giao diện console
- p0f dùng để phát hiện hệ điều hành, console trên nền Linux
- netcat, debug kết nối, đóng vai trò cả client và server, console trên windows và linux
- Snort, opensource phát hiện xâm nhập
- Nmap, tcpxtract, ssldump, nslookup, maxmind... và rất nhiều công cụ khác
## Memory Forensics

Là phương thức điều tra máy tính bằng việc sử dụng kiến trúc quản lý bộ nhớ trong máy tính để ánh xạ, trích xuất các tập tin đang thực thi và cư trú trong bộ nhớ RAM tại thời điểm hệ thống đang hoạt động, sau đó tiến hành phân tích làm rõ các hành vi đang xảy ra trên hệ thống.
Các công cụ phổ biến:
- Volatility là một framework với rất nhiều plugins được dùng để phân tích và tìm kiếm thông tin từ chứng cứ thu được. Các plugins được viết để phân tích điều tra bộ nhớ theo kiến trúc của hệ điều hành windows.


## Disk Forensics
Là việc thu thập, phân tích dữ liệu được lưu trữ trên phương tiện lưu trữ vật lý, từ đó trích xuất các dữ liệu ẩn, khôi phục các tập tin bị xóa, qua đó xác định người đã tạo ra những thay đổi dữ liệu trên thiết bị được phân tích, cũng như tìm kiếm những bằng chứng liên quan đến hoạt động xâm nhập, gian lận…

# Steganography
Là nghệ thuật và khoa học về việc giấu thông điệp, hình ảnh, hoặc dữ liệu trong một thông điệp khác, hỉnh ảnh khác hoặc dữ liệu khác. Thông thường, thông điệp ẩn sẽ được ẩn dấu trong một ảnh, một bài viết, một đoạn văn bản, hay thậm chí là một danh sách mua sắm. 
Một số kỹ thuật phổ biến:
- Dấu
