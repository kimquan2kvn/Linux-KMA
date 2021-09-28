# Bài 1: Shell script info.sh hiển thị các thông tin về hệ thống
  Kiểm tra phiên bản hệ điều hành Linux với lệnh `cat /etc/os-release`
  
  ![image](https://user-images.githubusercontent.com/54978467/135122088-92982128-dcc5-4050-9ad5-bd1718354538.png)
  
  Dùng lệnh `grep -w "NAME"` để tìm từ NAME, xác định vị trí cắt
  ```
  cut d '=' -f 2 
  d là dấu phân cách trường ta thấy dấu '='
  -f 2 là lấy trường thứ 2 là "Ubuntu"
  
  ```
  
  ![image](https://user-images.githubusercontent.com/54978467/135123355-b986f1b4-e00f-476c-9a03-ef2c9319f76a.png)
  
  ```
  "Ten may: `cat /etc/os-release | grep -w "NAME"|cut -d '=' -f2`"
  "Ban phan phoi: `cat /etc/os-release | grep -w "VERSION"|cut -d '=' -f2`"
  "He dieu hanh: `cat /proc/version |cut -d '=' -f2`"
  "Ten CPU: `cat /proc/cpuinfo | grep -w "model name" |cut -d ':' -f2`"
  "Bit CPU: `lscpu | grep -w "CPU op-mode(s)" | cut -d ':' -f2`"
  "Toc do CPU `lscpu | grep -w "CPU MHz"|cut -d ':' -f2` Mhz"
  ```

# Bài 2 : Cron job
