# Linux 
## 1. Cơ bản về Bash Scripting
Bất kì ai đã, đang hoặc từng sử dụng Linux thì đều nhận ra các điều sau đây:
  - Các chương trình chỉ làm được một công việc đơn giản và không thể làm 2 công việc khác nhau trở lên.
  - Các chương trình phải hoạt động theo một thứ tự nhất định để thực hiện một công việc nào đó và nếu thay đổi thứ tự này sẽ dẫn đến việc xử lý công việc khác.
  - Có một số công việc phải làm với tất suất lớn và đôi khi là lặp đi lại trong thời gian ngắn.

=> `Bash script` trở nên hữu ích. Các script viết ra có thể đảm nhiệm được một công việc ngay lập tức thay vì phải gõ lại một loạt các câu lệnh phức tạp.
Bash script là một loại ngôn ngữ kịch bản, bash script cũng có riêng một trình thông dịch đó là `BASH` (Bourne Again Shell). Có 2 cách để `bash script` được thực thi:
  - Chạy từng dòng một trên cửa sổ Terminal (nó không khác với việc chạy từng câu lệnh để hoàn thành 1 tác vụ nào đó).
  - Viết tất cả các câu lệnh cần thiết vào một file Bash `(.sh)` và thực thi.
 
`#! (shebang)`: dòng thông báo cho hệ điều hành biết file script này sẽ được thực thi bởi chương trình nào.

### a. Variable trong Bash
Variable (hay biến) chỉ các ô nhớ được khai báo cụ thể.

Để khai báo một biến, ta sử dụng ký hiệu equal `=` đặt giữa tên và giá trị của biến (không được đặt bất cứ dấu *space* nào ở trước hoặc sau `=`.

Để truy cập tới một biến, ta sử dụng ký hiệu dollar `$` ở ngay trước tên biến đó.
```bash
n=10
echo $n
```
### b. Nhập, in dữ liệu từ bàn phím 
Câu lệnh `read`
-p : thêm dấu nhắc nhập lệnh -s : ẩn đi giá trị bạn nhập

Câu lệnh `echo` để in ra văn bản, giá trị biến

```bash
#!/bin/bash
echo Ban ten la gi?
read who
echo Xin chao $who!
read -p 'Username: ' user
read -sp 'Password: ' pass
echo -e '\n'
echo Username: $user Password: $pass
```
![image](https://user-images.githubusercontent.com/54978467/134796158-a829ac2d-7a1c-49d9-ab8f-820a682eb8af.png)

### c. Tính toán cơ bản
```bash
#!/bin/bash
a=10
expr 10 + $a
expr 10 \* 3
expr 10 / 2
let b=15+$a
echo $b
let c=$b-5
echo $c
echo "3.4+7/8-(5.94*3.14)" | bc
```
![image](https://user-images.githubusercontent.com/54978467/134798462-0473efe4-0bc7-41fd-bee0-feb83028ed89.png)

`expr` chú ý khoảng trắng, tách biệt giữa các số các biến 
`let` không áp dụng số rời nhau.
`bc` đổi số nhị phân – thập phân – thập lục phân,

**Toán tử logic trong bash hơi khác ngôn ngữ khác, cần chú ý**

![image](https://user-images.githubusercontent.com/54978467/134814543-4c219f16-f288-440c-84cc-e4b27752fe1c.png)

**Boolean Operations** gồm có
  - and - &&
  - or - ||

### d. Câu lệnh điều kiện
* Dạng đơn giản: chỉ bao gồm một điều kiện, tùy theo điều kiện đúng hay sai mà sẽ thực hiện câu lệnh cụ thể

```bash
if [conditional] ; then
    statement_1
else
    statement_2
fi
```
* Dạng đầy đủ: bao gồm từ 2 điều kiện trở lên

```bash
if [conditional_1] ; then
    statement_1
elif [conditional_2] ; then
    statement_2
else
    statement_3
fi
```

* Dạng mở rộng: có nhiều điều kiện lồng nhau

```bash
if [conditional_1]; then
    if [conditional_2]; then
        statement_1
    else
        statement_2
    fi
fi
```
Ví dụ:
```bash
#!/bin/bash
read -p 'Nhap a: ' a
read -p 'Nhap b: ' b
if [ $a -gt $b ]; then
        echo "$a lon hon $b"

else
        echo "$a nho hon $b"
fi
```
![image](https://user-images.githubusercontent.com/54978467/134799570-51a57d8d-eb04-4cac-8c39-c36f467a23d0.png)

### e. Vòng lặp
#### Vòng lặp for
  - **Vòng lặp for với 3 điều kiện**
  ```
  for (( EXP1; EXP2; EXP3 ))
  do
      command1
      command2
      command3
  done
  ```
  
  Một ví dụ đơn giản như sau:
  
  ```bash
  #!/bin/bash
  for (( i=1; i<=5; i++))
  do
        echo "Xin chao ban, $i"
  done
  ```
  
  - **Vòng for để bỏ qua hay continue loop**
  ```
  for I in 1 2 3 4 5
  do
    if [condition]
  then
    continue
    fi
    statement
  done
  ```
  Ví dụ:
  
  ![image](https://user-images.githubusercontent.com/54978467/134815342-2271f8b5-b26b-4491-ab14-081630f17c39.png)
  
  Vì giá trị 4 khớp với điều kiện để continue nên nó nhảy qua giá trị 4
  
#### Vòng lặp while
  - **Vòng lặp while**
  ```bash
  #!/bin/bash
  input = hello
  while [ "$input" != "bye" ]
  do
    echo "Nhap nhung gi ban muon (bye to quit)"
    read input
    echo "Ban vua nhap: $input "
  done
  ```
  
### f. Cấu trúc case
Mời bạn xem qua ví dụ sau để hiểu về cấu trúc case:
```bash
#!/bin/bash
read -p "Nhap a: " a
read -p "Nhap b: " b
echo "1. Thuc hien phep cong"
echo "2. Thuc hien phep tru"
echo "3. Thuc hien phep nhan"
read -p "Nhap lua chon cua ban : " n
case $n in
        1)
                let c=$a+$b
                echo "Ket qua la: $c"
                ;;
        2)
                let c=$a-$b
                echo "Ket qua la: $c"
                ;;
        3)
                let c=$a*$b
                echo "Ket qua la: $c"
                ;;
        *)
                echo "Ban nhap sai roi. Ko the tinh duoc"
                ;;
esac
```

![image](https://user-images.githubusercontent.com/54978467/134820440-8a989b35-da75-47ee-a0c6-34b00848fddd.png)

### g. Hàm
Chúng ta cần hiểu cách tạo hàm và gọi hàm
```bash
#!/bin/bash
Tinh_s() {
dientich=$(($1*$2))
echo "Dien tich la : $dientich"
}
Tinh_s 30 20 
```

### h. Một số lệnh hay dùng
Chẳng hạn như `tr`, `grep`, `expr`, `cut`, `find`, `tee`.

**grep** để tìm kiếm từ, chuỗi trong file, thư mục
  - Tìm kiếm text đơn giản
  ```
  grep "test" test1.txt

  output:
  This is a test 1.
  ```
  
  - Tìm kiếm theo từng chữ
  ```
  grep -w "i" test1.txt
  ```
  - Tìm kiếm dòng chứa kí tự (thêm dấu .* vào giữa các kí tự)
  ```
  grep "This.*test" test1.txt
  ```
  - Tìm nhiều kí tự (sử dụng option -e)
  ```
  grep -e text 1 -e text2 -e text3 file text
  ```

### i. Viết 1 file bash

