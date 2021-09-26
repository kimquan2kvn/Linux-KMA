# Tìm hiểu các lệnh cơ bản trong Linux
## Xem thông tin OS
  - Sử dụng lệnh `cat /etc/os-release` hoặc `cat proc/version`
  
  ![image](https://user-images.githubusercontent.com/54978467/134767924-c1900041-eb57-49d8-9edf-9ab37538cf9a.png)
  
  - Dùng lệnh uname -
  
  ![image](https://user-images.githubusercontent.com/54978467/134768481-27af3fb3-0183-4f4d-b33d-70eadaae1bc3.png)

## Xem cấu hình máy
  - Vào Setting chọn About
  
  ![image](https://user-images.githubusercontent.com/54978467/134768421-c53988cc-5459-47ab-8b32-2813ef98f854.png)

## Xem thông tin về mạng
  - ```ifconfig``` để xem trạng thái các giao diện mạng
  ![image](https://user-images.githubusercontent.com/54978467/134769539-d22f34c1-35a9-4172-92f4-b8ae9786cad1.png)

## Quản lý tiến trình
  - Lệnh `top` quản trị được các thông số, CPU, RAM, I/O
  
  ![image](https://user-images.githubusercontent.com/54978467/134771031-bd615b7e-6f3d-4332-8927-a693e422eb0f.png)
  
  - Nhấn h để xem hướng dẫn, và nhấn ESC trở lại màng hình chính.

  - Nhấn f để thêm hoặc bớt các Field, sắp xếp trên Field hoặc đổi thứ tự các Field.
  
  - **Note:** Sử dụng lệnh `kill+PID` để đóng 1 tiến trình.
## Tìm kiếm file
  ![image](https://user-images.githubusercontent.com/54978467/134771254-da3a4ce4-37e2-46f5-831f-e32ace3b7a3e.png)

## Đặt lịch chạy định kỳ
`crontab` là 1 tính năng trong Linux thực hiện chế độ sắp xếp tự động các chương trình, ứng dụng và kích hoạt chúng tại 1 thời điểm nhất định trong hệ thống.
  - Cài đặt crontab: `sudo apt-get install cron`
  - Khởi động dịch vụ ‘crond‘ lên: `service crond start`
  - Để hiển thị danh sách lệnh crontab: `crontab -u <username> -l`
  - Mở trình editor chỉnh sửa file crontab:`crontab -e`
  - Ví dụ chạy một script nào đó vào 3 giờ chiều, mỗi thứ Năm h:
  ![image](https://user-images.githubusercontent.com/54978467/134792272-19e703f2-1a81-4429-8174-72452c891a6b.png)
  
  - Note: 
      - Biến SHELL chỉ định shell để sử dụng khi các câu lệnh được thực thi.
      - Biến MAILTO đặt địa chỉ mail nhận các kết quả của cron job.
      - Dòng thứ ba có nhiệm vụ thiết lập PATH cho môi trường.

## Phân quyền
Với 1 file/folder trong linux sẽ có 3 quyền cơ bản:
  - R (read) - với file thì có thể xem được nó, với thư mục thì có thể show được các thành phần ở trong đó.
  - W (write) - với file thì có thể chỉnh sửa nội dung file, với thư mục thì có thể thêm bớt, xóa file ở trong đó.
  - X (execute) - có quyền thực thi với file, thư mục

Với 1 file/folder trong linux sẽ có 3 đối tượng sử dụng:
  - O (owner): là chủ sở hữu của file thư mục, khi mới tạo file mặc định là là account tạo file.
  - G (group): là 1 hoặc 1 nhóm account, khi mới tạo file mặc định là là account tạo file.
  - U (user other) : là những account còn lại không thuộc 2 nhóm trên

Sử dụng lệnh `chmod` để phân quyền:
  - command thêm quyền execute cho group: `chmod g+x filename`
  - command xóa quyền write cho group:`chmod g-x file_name`
  - command thêm quyền write cho user other:`chmod a+x file_name`
  - command thêm quyền execute cho group và user other:`chmod ga+x file_name`
  
  Với o-owner, g - group, a - user other, r-read ,w-write, x-execute, add thêm quyền là '+', loại bỏ đi quyền là '-'.

Ví dụ phân quyền thực thi file bash:

  ![image](https://user-images.githubusercontent.com/54978467/134791397-a1d5ea47-773d-4548-8156-2c3ff65a301c.png)
  
**Note:** Thay đổi owner cho tập tin và thư mục:
Ví dụ bạn muốn set lại owner cho text1.txt với owner mới là user1: `chown user1 text1.txt`

  

