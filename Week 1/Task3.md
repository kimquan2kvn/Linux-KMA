# Tìm hiểu cách cài đặt phần mềm trên Linux
## 1. Cài đặt file .deb
**1. Sử dụng Software Install**

Chỉ cần đến thư mục chứa file DEB bạn tải về và nháy đúp vào đó.

![image](https://user-images.githubusercontent.com/54978467/134763387-7477693f-60d2-4669-a912-0bf1c8a8e9bd.png)

**2. Dùng Gdebi**

Cài đặt gdebi bằng dòng lệnh sau:
```sudo apt install gdebi```

Sau khi cài xong mở Applications và mở Gdebi rồi open đến file .deb cần setup

![image](https://user-images.githubusercontent.com/54978467/134763659-2da0969f-4e8a-43d2-ba15-b6771bfd1516.png)

**3. Dùng dpkg**
```dpkg``` là phần mềm làm nền tảng cho các hệ thống quản lý gói tin trên hệ điều hành tự do nguồn mở Debian.

```sudo dpkg -i <Đường dẫn tới file .deb>```

![image](https://user-images.githubusercontent.com/54978467/134763949-d50e2845-b1cb-459e-a3ef-d8cadd6956f5.png)

**4. Gỡ file .deb**

 Tìm tên phần mềm ```dpkg -l | grep <Tên phần mềm>```
  
 Remove ```dpkg -r <Tên phần mềm>```
  
 ![image](https://user-images.githubusercontent.com/54978467/134765469-feb7e274-d34d-4334-8b8e-1faeb0f2a4bc.png)


## 2. Cài qua apt-get
APT(Advanced Packaging Tool), là phần mềm miễn phí dùng để quản lý việc cài đặt phần mềm trên Linux.

Cập nhật các package của hệ thống: ```apt-get update```

Cập nhật các phần mềm của hệ thống: ```apt-get upgrade```

Cài đặt hoặc nâng cấp một package cụ thể: ```apt-get install <tên package>```

Gỡ bỏ một packages không thông qua cấu hình: ```apt-get remove <tên package>```

Gỡ bỏ một packages không thông qua cấu hình: ```apt-get remove <tên package>```

Tìm kiếm tên và thông tin về một package: ```apt-cache search <tên package>```

Ví dụ mình sẽ cài Zoom:

![image](https://user-images.githubusercontent.com/54978467/134766549-03f8627c-ebcc-431a-ad0b-15482b69a256.png)
