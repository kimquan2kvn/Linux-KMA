## Linux 
# 1. Cơ bản về Bash Scripting
Với những ai thường xuyên sử dụng các hệ điều hành Linux cho công việc thì việc thao tác với các dòng lệnh là điều cần thiết và rất quan trọng.
Tuy nhiên bất kì ai đã, đang hoặc từng sử dụng Linux thì đều nhận ra các điều sau đây:
  - Các chương trình chỉ làm được một công việc đơn giản và không thể làm 2 công việc khác nhau trở lên.
  - Các chương trình phải hoạt động theo một thứ tự nhất định để thực hiện một công việc nào đó và nếu thay đổi thứ tự này sẽ dẫn đến việc xử lý công việc khác.
  - Có một số công việc phải làm với tất suất lớn và đôi khi là lặp đi lại trong thời gian ngắn.

=> `Bash script` trở nên hữu ích. Các script viết ra có thể đảm nhiệm được một công việc ngay lập tức thay vì phải gõ lại một loạt các câu lệnh phức tạp.
Bash script là một loại ngôn ngữ kịch bản, bash script cũng có riêng một trình thông dịch đó là `BASH` (Bourne Again Shell). Có 2 cách để `bash script` được thực thi:
  - Chạy từng dòng một trên cửa sổ Terminal (nó không khác với việc chạy từng câu lệnh để hoàn thành 1 tác vụ nào đó).
  - Viết tất cả các câu lệnh cần thiết vào một file Bash `(.sh)` và thực thi.
 
`#! (shebang)`: dòng thông báo cho hệ điều hành biết file script này sẽ được thực thi bởi chương trình nào.

**a. Variable trong Bash:**
Variable (hay biến) chỉ các ô nhớ được khai báo cụ thể.

Để khai báo một biến, ta sử dụng ký hiệu equal `=` đặt giữa tên và giá trị của biến (không được đặt bất cứ dấu *space* nào ở trước hoặc sau `=`.

Để truy cập tới một biến, ta sử dụng ký hiệu dollar `$` ở ngay trước tên biến đó.
