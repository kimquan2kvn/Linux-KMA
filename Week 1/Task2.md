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

**Note:**
  - Để liệt kê các file của thư mục cụ thể ở định dạng cây, chẳng hạn như /etc, hãy chạy lệnh: ```tree/etc```

## 2. Các hệ thống file có trên Linux
![image](https://user-images.githubusercontent.com/54978467/134631226-1dc73465-c194-4230-8db7-fa1e7b83d770.png)

**1. Hệ thống tệp Ext, Ext2, Ext3 và Ext4**
 - **Ext2** là hệ thống tệp Linux đầu tiên cho phép quản lý hai terabyte dữ liệu.
 - **Ext3** là tương thích ngược với Ext2, và do vậy những ổ đĩa, phân vùng có thể dễ dàng được chuyển đổi giữa 2 chế độ mà không cần phải format. **Hạn chế Ext3 là không hỗ trợ máy chủ**
 - **Ext4** có tương thích ngược, tốc độ nhanh hơn, phân mảnh ổ cứng ít hơn. Dung lượng file tối đa định dạng Ext4 là 16 tebibyte, tương đương với khoảng 17,6 terabyte.

**2. Hệ thống tệp BtrFS**
  - Butter FS. Được phát triển bởi oracle , đây là một trong những hệ thống tệp hiệu quả nhất, xử lý khối lượng lớn dữ liệu, được thiết kế riêng biệt dành cho các doanh nghiệp có quy mô lớn.

**3. JFS**
  - JFS là viết tắt của Journaled File System , và nó được IBM phát triển
  - Hoạt động tốt với cả hai loại ổ cứng: lưu trữ nhỏ và lớn. Nó sử dụng rất ít sức mạnh xử lý của CPU.

**4. ReiserFS**
  - Đạt hiệu suất hoạt động rất cao đối với những file nhỏ như file log, phù hợp với database và server email.

**5. ZFS**
  - Hệ thống tệp này cho phép bạn phân chia ổ đĩa động và gộp ổ đĩa -> hữu ích khi làm việc với thiết bị lưu trữ dữ liệu

**6. FAT32**
  - Cung cấp cách tốt nhất để lưu trữ các tệp để hệ điều hành có thể dễ dàng tìm thấy các tệp và thư mục.
  - Dung lượng file phải nhỏ hơn 4GB, kích thước phân vùng tối đa 8TB.

**7. exFAT**
  - Là một hệ thống tệp khác thuộc họ FAT. Nó cũng được coi là hệ thống tệp thường được sử dụng để làm việc với dữ liệu hoặc tệp.
  - Hiệu quả hơn FAT32.

**8. Swap**
  - Sử dụng dưới 1 dạng bộ nhớ ảo và không có cấu trúc file hệ thống cụ thể. 
  - Không thể kết hợp và đọc dữ liệu được. Chỉ có thể được dùng bởi kernel để ghi thay đổi vào ổ cứng.

**9. TmpFS**
  - Tốc độ đọc/ghi rất nhanh (dữ liệu lưu trên RAM). Phù hợp để lưu trữ cache như Web Server Caching page.
  - Dữ liệu lưu trên phân vùng file system tmpfs sẽ bị mất khi reboot hệ thống.

## 3. Cách kiểm tra loại file hệ thống trên Linux
**1. Lệnh df**
  - Lệnh df trên Linux cho biết dung lượng đang sử dụng của các phân vùng ổ cứng, bên cạnh đó bạn có thể xem được cả loại file system của partition hoặc disk với option “-T“.

**2. Lệnh “file”**
  - Lệnh file nếu sử dụng option ‘-s‘ sẽ đọc thông tin và đặc điểm về file hoặc block. Kết hợp option ‘-L‘ sẽ hỗ trợ cả symlink.
  
![image](https://user-images.githubusercontent.com/54978467/134639715-277bac25-8c49-44d6-bfd8-a9e05c6bf327.png)







