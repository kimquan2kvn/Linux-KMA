# 1. Shell script info.sh hiển thị các thông tin về hệ thống
  Kiểm tra phiên bản hệ điều hành Linux với lệnh `cat /etc/os-release`
  
  ![image](https://user-images.githubusercontent.com/54978467/135122088-92982128-dcc5-4050-9ad5-bd1718354538.png)
  
  Dùng lệnh `grep -w "NAME"` để tìm đến dòng có từ NAME, xác định vị trí cắt
  ```
  cut d '=' -f 2 
  d là dấu phân cách trường ta thấy dấu '='
  -f 2 là lấy trường thứ 2 là "Ubuntu"
  
  ```
  
  ![image](https://user-images.githubusercontent.com/54978467/135123355-b986f1b4-e00f-476c-9a03-ef2c9319f76a.png)
  
  ```bash
  #!/bin/bash
  menu=(
  "Ten may: `cat /etc/os-release | grep -w "NAME"|cut -d '=' -f2`"
  "Ban phan phoi: `cat /etc/os-release | grep -w "VERSION"|cut -d '=' -f2`"
  "He dieu hanh: `cat /proc/version |cut -d '=' -f2`"
  "Ten CPU: `cat /proc/cpuinfo | grep -w "model name" |cut -d ':' -f2`"
  "Bit CPU: `lscpu | grep -w "CPU op-mode(s)" | cut -d ':' -f2`"
  "Toc do CPU: `lscpu | grep -w "CPU MHz"|cut -d ':' -f2` Mhz"
  "Dung luong o cung: `df -h /dev/sda4 --output=size|grep "G"`" 
  "Dung luong con lai: `df -h /dev/sda4--output=avail|grep "G"`"
  "Dia chi DNS: ` grep nameserver /etc/resolv.conf | cut -d ' ' -f 2`"
  "Dia chi ip: `ip addr |grep -w "inet"|cut -d '/' -f2 | tr -s ' '|cut -d ' ' -f3`"
  "Gateway: `route -n | grep 'UG[ \t]' | awk '{print $2}'`"
  )
  
  for ((i=0;i<${#menu[@]};i++))
  do
      echo -e ${menu[i]} 
  done
  
  users="`cut -d : -f 1 /etc/passwd|sort`"
  echo "Danh sach user:"
  echo $users | tr [:space:] '\n'

  echo -e "\nDanh sach tien trinh dang chay duoi quyen root: \n"
  ps -fU root |sort
  
  echo -e "\nDanh sach file ma other co quyen ghi: \n"
  find -perm -o=r

  ehco -e "\nDanh sach cac phan mem duoc cai dat tren he thong: \n"
  apt list --installed
  
  echo -e "\nDanh sach cach port dang mo va cac tien trinh: \n"
  netstat | sort -n
  
  ```

# 2. Cron job
  - Tạo cron job chạy định kỳ với thời gian chỉ định nhằm kiểm tra sự thay đổi của một folder.   
  - Kiểm tra xem có file nào trong folder được tạo mới (so với lần chạy trước theo lịch đã đặt) hay không? Nếu có thì in ra tên các file đó.   
  - Kiểm tra xem có file nào trong folder bị thay đổi (so với lần chạy trước theo lịch đã đặt) hay không? Nếu có thì in ra tên các file đó.   
  - Kiểm tra xem có file nào trong folder bị xóa (so với lần chạy trước theo lịch đã đặt) hay không? Nếu có thì in ra tên các file đó.
  - Tất cả các các điều trên được lưu vào file .log tự định sẵn
