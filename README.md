# Kiểm thử sử dụng JMeter
- Trang web kiểm thử: http://localhost/team19.thoitrangstore.com/
. Kết quả kiểm thử
#Phiên kiểm thử 1: result2.jtl – Kịch bản hợp lệ
![image](https://github.com/user-attachments/assets/9529d7a6-3b29-402e-986f-cc86c9e196eb)

 
- Thời gian kiểm thử: Khoảng 1 phút
- Số lượng yêu cầu: 250
- Tỷ lệ thành công: 200 yêu cầu thành công (80%)
- Lỗi gặp phải: 50 yêu cầu không thành công (404 Not Found)
Thống kê hiệu năng:
Thông số	Giá trị trung bình
Thời gian phản hồi	28.06 ms
Độ trễ trung bình	12.67 ms
Dung lượng phản hồi trung bình	~40.8 KB
Số luồng hoạt động	1–2 luồng
Nhận xét:
- Phần lớn yêu cầu được xử lý thành công.
- Một số lỗi 404 Not Found xuất hiện ở bước Xem Sản Phẩm, cho thấy trang sản phẩm chưa tồn tại hoặc đường dẫn sai.
 
Phiên kiểm thử 2: result.jtl – Kịch bản bị lỗi cấu hình
![image](https://github.com/user-attachments/assets/a70de92c-ae58-40e2-8da0-37f41abed364)

 
- Thời gian kiểm thử: Khoảng 1 phút
- Số lượng yêu cầu: 250
- Tỷ lệ thành công: 0%
- Tất cả yêu cầu đều thất bại
Loại lỗi chính:
- Non HTTP response code: java.lang.IllegalArgumentException
- java.net.URISyntaxException: URL sai định dạng
Thống kê hiệu năng:
Thông số	Giá trị trung bình
Thời gian phản hồi	~0 ms
Số lượng byte phản hồi	~1 KB
Dữ liệu gửi đi	0 byte
Số luồng hoạt động	1–3 luồng
Nhận xét:
- Các lỗi xảy ra do URL không hợp lệ, ví dụ: "http:/\t/team19.thoitrangstore.com/login.php".
- Đây là lỗi cấu hình script JMeter, cần chuẩn hóa lại URL sử dụng trong .jmx.
