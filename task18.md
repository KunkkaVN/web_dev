
#Mục lục
[**1. Khai báo CSS**](#phan1)

[**2. Tìm hiểu về vùng chọn cơ bản (Selector)**](#phan2)

[**3. đơn vị px, pt, percentages, em và rem**](#phan3)

[**4. Các thuộc tính cho Text (văn bản)**](#phan4)

[**5.Phần tử Block (khối) và Inline (nội dòng)**](#phan5)

[**6. Thẻ div và tạo bố cục trên website**](#phan6)

[**7. Box Model và các thuộc tính**](#phan7)

[**8. Các thuộc tính tùy chỉnh kích thước**](#phan8)

[**9. Màu nền và Ảnh nền (background)**](#phan9)


<a name="phan1">
**1. Khai báo CSS:
------------------

Nhúng CSS vào website thì chúng ta có hai cách là:

- Inline Styles – Nhúng trực tiếp vào tài liệu HTML thông qua cặp thẻ <style> </style>.

Thích hợp với việc chèn một vài đoạn CSS ngắn.

Trình duyệt không mất thời gian tải tập tin CSS.

Ví dụ:

```sh
<style type="text/css">
			p{
				color: red;
			}
		</style>
```

- External Styles – Tạo một tập tin .css riêng và nhúng vào tài liệu HTML thông qua cặp thẻ <link>.

Thích hợp với việc chèn nhiều đoạn CSS, dễ quản lý.

Nhưng trình duyệt sẽ mất thêm thời gian để tải tập tin CSS.

```sh
<link rel="stylesheet" href="name.css" />
```

<a name="phan2">
**2. Tìm hiểu về vùng chọn cơ bản (Selector):
---------------------------------------------

Trong CSS, vùng chọn nghĩa là khu vực mà bạn muốn nó sẽ được áp dụng các quy tắc CSS mà bạn muốn chỉ định cho nó. Ví dụ bạn muốn tăng kích thước font chữ của các thẻ h1 thì vùng chọn của bạn sẽ là h1.

Các loại vùng chọn cơ bản

- Vùng chọn dựa vào tên thẻ

- Vùng chọn dựa vào ID

- Vùng chọn dựa vào Class

<img src="http://i.imgur.com/PxXZfdP.jpg">

```sh
#title-1 {
  color: blue;
}

.class-1{
	text-align: center;
}
```

- Vùng chọn theo thứ cấp: được sử dụng khi muốn áp dụng css cho phần tử của 1 bộ phận nào đó như list

ví dụ:

```sh
<ul id="menu">
  			<li>Menu 1</li>
  			<li>Menu 2</li>
  			<li>Menu 3</li>
		</ul>

		<ul id="social">
  			<li>Facebook</li>
 			<li>Twitter</li>
  			<li>Google+</li>
		</ul>
```
```sh
#menu li {
	color: red;
	background: blue;
}
```

- Vùng chọn theo thứ cấp liền nhau: được dùng muốn chọn 1 mục con css trong mục các mục mẹ

<a name="phan3">
**3. đơn vị px, pt, percentages, em và rem:
-------------------------------------------

Trong CSS có hai loại đơn vị là Absolute Units (đơn vị tuyệt đối) và Relative Units (đơn vị tương đối). Trong đó:

- Đơn vị tuyệt đối: px, pt

- Đơn vị tương đối: %, em, rem

<a name="phan4">
**4. Các thuộc tính cho Text (văn bản)
--------------------------------------

Text Styles trong CSS hiện tại có khoảng 13 thuộc tính được sử dụng bao gồm căn lề văn bản, trang trí văn bản, định hướng văn bản,….Cụ thể là có các thuộc tính thường dùng sau:

- text-align: Căn lề văn bản.

```sh
text-align: left; // Căn lề văn bản từ bên trái 
text-align: right; // Căn lề văn bản từ bên phải
text-align: center; // Căn lề văn bản từ chính giữa
text-align: justify; // Căn lề văn bản đều hai bên
```

- text-decoration: Trang trí văn bản.

```sh
overline: gạch trên chữ
underline: gạch dưới chữ
line-through: gạch ngang chữ
none: không có gạch gì cả
```

- text-indent: Thêm khoảng trống trước văn bản theo chiều ngang từ trái sang phải.

```sh
text-indent: 15px;
text-indent: 15%;
text-indent: 1.5pt;
```

- text-shadow: Thêm bóng cho văn bản.

`text-shadow: [màu sắc] [tọa độ x y] [độ mờ]`

- text-transform: Tùy chỉnh việc hiển thị chữ in hoa.

Thuộc tính này có 3 giá trị chính là `capitalize` (in hoa chữ cái đầu tiên của mỗi từ), `uppercase` (in hoa cả đoạn văn bản), `lowercase` (viết thường cả đoạn văn bản) và `none` (không có gì cả).

<a name="phan5">
**5. Phần tử Block (khối) và Inline (nội dòng)
----------------------------------------------

- Block là gì?

Phần tử khối (Block Elements) là thuật ngữ chỉ chung các thẻ HTML có chức năng tạo một khu vực hay nói dễ nghe xíu là một khối. Khối này có nghĩa là một thẻ khi mà bạn khai báo thì nó sẽ được hiển thị ở mỗi dòng riêng biệt bao gồm các nội dung nằm bên trong. Ở các bài học HTML cơ bản bạn có thể đã biết qua một số thẻ block cơ bản như `<p>`, `<ul>`, `<ol>`, `<h1>`,…

Và khi bạn học tới CSS, bạn sẽ dùng một thẻ rất quan trọng nữa đó là `<div>` và đây là một thẻ được dùng để tạo các block hay một khu vực nào đó để dễ dàng viết CSS sau này.

- Inline là gì?

Phần tử nội dòng (Inline Elements) là thuật ngữ chỉ chung các thẻ HTML khi mà khai báo vào nội dung thì nó vẫn sẽ nằm chung một dòng với các văn bản khác. Một số thẻ inline rất hay dùng đó là `<b>`, `<strong>`, `<i>`, `<u>`,…và đặc biệt là `<span>` nếu bạn cần gộp nhóm các phần tử nào đó mà không ảnh hưởng đến các văn bản chung một hàng, thẻ `<span>` này có ý nghĩa và cách sử dụng giống như `<div>` nhưng nó được dùng trong inline.

<a name="phan6">
**6. Thẻ div và tạo bố cục trên website
---------------------------------------

Đây là cái thẻ mà nó là chữ viết tắt của division (nghĩa là khu trong tiếng Việt theo từ điển kỹ thuật chung) được sử dụng để tạo ra một khu vực kiểu block nào đó trên một website, hay bạn có thể hiểu là gom nhóm tập hợp các phần tử trên website vào một khu vực với thẻ `<div>`.

<a name="'phan7">
**7. Box Model và các thuộc tính
--------------------------------

**Box Model** là một kỹ thuật cơ bản nhất trong CSS Layout và được sử dụng để bạn mô tả về khoảng cách mà mỗi phần tử trên website được sở hữu, hay nói cách khác là kỹ thuật tinh chỉnh khoảng cách hiển thị cho mỗi phần tử trên website.

Kỹ thuật Box Model trong CSS bao gồm 4 phần quan trọng đó là:

- Margin: Khoảng cách tính từ bên ngoài của phần tử.

- Border: Đường viền của phần tử.

- Padding: Khoảng cách tính từ bên trong của phần tử.

- Content: Nội dung trong phần tử.

<img src="https://thachpham.com/wp-content/uploads/2015/04/box-model.gif">

```sh
margin: top right bottom left; 
border: top right bottom left; 
padding: top right bottom left;
```

<a name="phan8">
**8. Các thuộc tính tùy chỉnh kích thước
-----------------------------------------

<img src="http://i.imgur.com/cDI0jPZ.jpg">

<a name="phan9">
**9. Màu nền và Ảnh nền (background)
------------------------------------

**Màu nền với background-color**

Nếu bạn muốn thiết lập màu nền bằng CSS thì có thể sử dụng thuộc tính background-color và giá trị của nó là tên màu, hoặc mã màu HEX/RBG

**Ảnh nền với background-image**

``background-image: url('ảnh 1'), url('ảnh 2');``

**Tùy chỉnh lặp lại ảnh nền** với `background-repeat`

Mặc định khi sử dụng ảnh nền, thì hình ảnh sẽ được lặp đi lặp lại theo cả chiều ngang và chiều dọc cho đến khi ảnh nền lấp toàn bộ phần tử. Nhưng bạn cũng có thể tùy chỉnh lại việc lặp ảnh nền thông qua thuộc tính background-repeat, nó hỗ trợ các giá trị như sau:

- no-repeat: Không lặp.

- repeat-x: Lặp theo chiều ngang.

- repeat-y: Lặp theo chiều dọc.

- space: Lặp đều theo chiều ngang và chiều dọc, ảnh nền sẽ cách nhau bằng khoảng trắng.

- round: Chưa hiểu lắm nên không giải thích.

- repeat: Mặc định.

**Đổi vị trí ảnh nền với** `background-position`

- top: hiển thị ở trên đầu phần tử.

- bottom: hiển thị bên dưới phần tử.

- left: hiển thị bên trái phần tử.

- right: hiển thị bên phải phần tử.

- center: hiển thị chính giữa phần tử.

- y-x: tùy biến vị trí hiển thị theo tọa độ, giá trị đứng trước là y và đứng sau là x. Ví dụ: 15px 10px