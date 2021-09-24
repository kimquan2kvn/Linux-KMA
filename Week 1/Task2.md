# Tìm hiểu về hệ điều hành Linux
Linux là một họ các hệ điều hành tự do nguồn mở tương tự Unix và dựa trên Linux kernel, một hạt nhân hệ điều hành được phát hành lần đầu tiên vào ngày 17 tháng 9 năm 1991, bởi Linus Torvalds.

Các phiên bản hệ điều hành Linux phổ biến:
  - Ubuntu.
  - Fedora – Red Hat.
  - Linux Mint.
  - Kali Linux.
  - CentOS.

Hiện nay thì linux đang là hệ điều hành đang được sử dụng nhiều nhất trên thế giới.
## 1. Chức năng, ý nghĩa của các thư mục dưới thư mục gốc (/)
![image](https://user-images.githubusercontent.com/54978467/134626651-95d5d3f7-d14b-44df-830d-ebbb4cccb421.png)

**1. / - Thư mục Root**
  - Là thư mục bắt đầu của tất cả các file và thư mục khác
  - Chỉ có root user mới có quyền sửa đổi trong thư mục

**2. /bin – Chương trình của người dùng**
  - Chứa các chương trình thực thi của tất cả người dùng
  - Ví dụ: ping, ls...

**3.	/sbin – Chứa các tập tin thực thi của hệ thống**
  - Chức các chương trình thực thi dùng cho các quản trị viên
  - Ví dụ iptable, reboot...

**4.	/etc – Các tập tin cấu hình**
  - Các tập tin cấu hình cho tất cả chương trình
  - Chứa các shell script (kịch bản) để khởi động hoặc tắt chương trình

**5. /dev - Các device của thiết bị**

**6. /tmp - Các file tạm thời**
  - Sẽ bị xóa khi hệ thống khởi động lại

**7. /proc - Thông tin về các tiến trình và tài nguyên đang sử dụng**

![image](https://user-images.githubusercontent.com/54978467/134629411-75d5b1a1-0238-4a11-8904-c5d409d0d80c.png)

  - /proc/version : Xem phiên bản Linux Kernel và trình biên dịch được sử dụng để xây dựng nó
  - /proc/uptime: Thời gian hoạt động của cpu

**8.	/var – Các tập tin biến đổi**
  - /var/log: các tập tin ghi chú hệ thống
  - /var/lib: các gói và các tập tin cơ sở dữ liệu
  - /var/mail: thư điện tử
  - /var/lock: các tập tin khóa

**9.	/usr – Chương trình của người dùng**
  - /usr/bin: Chứa các tập tin thực thi cho các chương trình của người dùng
  - /usr/sbin: Chứa các tập tin thực thi quản trị hệ thống
  - /usr/lib: Các tập tin thư viện
  - /usr/local: Chứa các chương trình của người dùng mà bạn đã cài từ mã nguồn. 
 
    Ví dụ: khi cài Apache từ mã nguồn, nó được đưa vào thư mục /usr/local/apache2

**10.	/home – Thư mục của người dùng**

**11.	/boot – Các file khởi động**

**12.	/lib – Thư viện hệ thống**

**13.	/opt – Các ứng dụng phụ tùy chọn**

**14.	/mnt – Thư mục để mount**
  - Người dùng quản trị có thể mount các tập tin hệ thống

**15.	/media – Các thiết bị tháo lắp**
  - Chứa các mount tạm thời cho các thiết bị tháo lắp như đĩa CD

**16.	/srv – Dữ liệu dịch vụ**
  - Srv là viết tắt service
  - Chứa dữ liệu liên quan tới các dịch vụ trên máy chủ
