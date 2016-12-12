#Mục lục
[**1. HTML là gì?**](#phan1)

[**2. Cấu trúc một tài liệu web bằng HTML**](#phan2)

[**3. Các thẻ khai báo thông tin web cơ bản**](#phan3)

[**4. Các thẻ định dạng chữ viết và văn bản**](#phan4)

[**5. Tạo danh sách**](#phan5)

[**6. Thẻ tạo liên kết và liên kết neo**](#phan6)

[**7. Chèn tập tin kỹ thuật số vào web**](#phan7)

[**8.Tạo form nhập liệu**](#phan8)

<a name="phan1"></a>
**1. HTML là gì?
----------------

- HTML là HyperText Markup Language được sử dụng để tạo một trang web, trên một website có thể sẽ chứa nhiều trang và mỗi trang được quy ra là một tài liệu HTML.

Một tập tin HTML sẽ bao gồm các phần tử HTML và được lưu lại dưới đuôi mở rộng là `.html` hoặc `.htm`.

**HTML được xử lý ra sao?**

Khi một tập tin HTML được hình thành, việc xử lý nó sẽ do trình duyệt web đảm nhận. Trình duyệt sẽ đóng vai trò đọc hiểu nội dung HTML từ các thẻ bên trong và sẽ chuyển sang dạng văn bản đã được đánh dấu để đọc, nghe hoặc hiểu (do các bot máy tính hiểu).

**Cấu trúc một đoạn HTML**

Một tài liệu HTML được hình thành bởi các phần tử HTML (HTML Elements) được quy định bằng các cặp thẻ (tag), các cặp thẻ này được bao bọc bởi một dấu ngoặc ngọn (ví dụ `<html>`) và thường là sẽ được khai báo thành một cặp, bao gồm thẻ mở và thẻ đóng (ví `<strong>` dụ `</strong>` và ). Các văn bản muốn được đánh dấu bằng HTML sẽ được khai báo bên trong cặp thẻ (ví dụ `<strong>`Đây là chữ in đậm`</strong>`). Nhưng một số thẻ đặc biệt lại không có thẻ đóng và dữ liệu được khai báo sẽ nằm trong các thuộc tính (ví dụ như thẻ `<img>`).

Ví dụ: `<strong>`Đây là chữ in đậm`</strong>`

<strong>Đây là chữ in đậm</strong>

Ngoài ra, trong các thẻ còn có các thuộc tính, thuộc tính sẽ đặt bên trong thẻ mở đầu, mỗi thuộc tính sẽ có giá trị được đặt trong dấu ngoặc kép và cách nhau bởi dấu bằng (=) với tên thuộc tính. Ví dụ dưới đây là một thẻ có sử dụng thuộc tính

ví dụ : `<img src="ảnh.jpg">`

Một thẻ có thể sử dụng nhiều thuộc tính chứ không phải chỉ một thuộc tính nhé.

<a name="phan2"></a>
**2. Cấu trúc một tài liệu web bằng HTML
----------------------------------------

Một tài liệu hay tập tin HTML để được gọi là một tài liệu web thì sẽ được bao gồm bốn yếu tố chính đó là:

- Có thẻ khai báo loại tập tin/tài liệu.

- Có thẻ đóng và mở tài liệu HTML.

- Có thẻ đóng và mở phần thông tin website.

- Có thẻ đóng và mở phần nội dung website.

```sh
<!DOCTYPE html> #Thẻ khai báo loại tập tin
<html lang= "vi"> #Thẻ đóng mở tài liệu HTML
	<head> #Thẻ đóng và mở phần thông tin website
		<title>kunkka</title>
		<meta charset="utf-8">
	</head>
	<body> #Có thẻ đóng và mở phần nội dung website
		<h1>Từ ấy trong tôi bừng nắng hạ</h1>
	</body>
</html>
```

<a name="phan3"></a>
**3. Các thẻ khai báo thông tin web cơ bản
------------------------------------------

- Khai báo tên tài liệu với cặp thẻ `<title>` : thẻ `<title> </title>` có tác dụng khai báo tên tài liệu web của bạn đang soạn. Ứng dụng thực tiễn của thẻ này là giúp trình duyệt hiển thị tên tài liệu khi mở lên và các cỗ máy tìm kiếm như Google cũng hiển thị nội dung trong cặp thẻ này để lấy tên tài liệu

**Khai báo dữ liệu vĩ mô với thẻ <meta>**

ví dụ :`<meta charset="utf-8" />` khai báo thuộc tính web sử dụng là utf-8

- Thuộc tính charset: thuộc tính `charset` trong thẻ `<meta>` có nhiệm vụ khai báo cho trình duyệt biết bảng mã ký tự siêu văn bản bên trong tài liệu là gì

- Thuộc tính name: Đối với thuộc tính name thì thẻ meta của bạn phải có hai thuộc tính, đó là thuộc tính name và content, trong đó thuộc tính content được xem là thiết lập nội dung cho thuộc tính name

`<meta name="author" content="abcxyz" />`

Một số thuộc tính name hay dùng như:

- `author`: Khai báo tên tác giả của tài liệu.

- `description`: Khai báo mô tả của tài liệu.

- `keyword`: Khai báo từ khóa của tài liệu, các từ khóa này sẽ đóng vai trò hỗ trợ các trình tìm kiếm văn bản hoặc máy tìm kiếm website dò tìm.

- `application-name`: Tên ứng dụng đại diện của tài liệu web.

- `generator`: Khai báo tên ứng dụng tạo ra tài liệu.

<a name="phan4"></a>
**4. Các thẻ định dạng chữ viết và văn bản
------------------------------------------

- Thẻ tiêu đề : `<h1> </h1>`

- Đoạn văn bản: `<p></p>`

- `<strong>`: In đậm chữ viết.

- `<i>`: In nghiêng chứ viết.

- `<u>`: Gạch chân chữ viết.

- `<strike>`: Gạch ngang chữ viết.

- `<em>`: Nhấn mạnh câu.

- `<code>`: Định dạng cho một đoạn mã nào đó.

- `<hr>`: Thước kẻ ngang trên tài liệu.

- `<mark>`: Tô sáng chữ viết.

-Thẻ định dạng sẵn: `<pre> </pre>`

**Thuộc tính style để định dạng chữ viết**

Mặc dù việc lên màu sắc trên website là do CSS đảm nhận, nhưng nếu là một văn bản HTML thông thường thì bạn vẫn có thể thêm màu sắc cho chữ viết bằng thuộc tính style. Thuộc tính style có thể đặt trong bất cứ thẻ nào và giá trị của thuộc tính đó là các thuộc tính của CSS

Cấu trúc viết thuộc tính sẽ là `<tên thẻ style="tên thuộc tính: giá trị">`.

- Màu chữ: `<span style="color: white; background-color: red">Chữ có nền màu đỏ và màu chữ là trắng</span>`

- Kích thước chữ: Kích thước chữ bạn có thể sử dụng thuộc tính font-size và giá trị là số kèm đơn vị. Bạn có thể sử dụng đơn vị px, %, pt hoặc em tùy thích, đơn giản nhất là dùng px. `<span style="font-size: 32px">Chữ có kích thước 32px</span>`

-Căn lề văn bản: `<span style="text-align: center">Canh giữa văn bản</span>`

<a name="phan5"></a>
**5. Tạo danh sách
------------------

Trong HTML có ba kiểu danh sách (list type) đó là kiểu sắp xếp (ordered list), kiểu không sắp xếp (unordered list) và kiểu danh sách mô tả (description list). Cụ thể:

- Kiểu sắp xếp (Ordered List): Là kiểu hiển thị một danh sách mà các mục con của nó được sắp xếp theo thứ tự bằng số hoặc chữ cái.

- Kiểu không sắp xếp (Unordered List): Là kiểu hiển thị danh sách mà các mục con của nó sẽ không được sắp xếp theo thứ tự mà chỉ được đánh dấu bằng một ký tự đặc trưng.

- Kiểu mô tả (Description List): Là kiểu hiển thị danh sách mà các mục con của nó sẽ không được đánh dấu thứ tự, nhưng sẽ có kèm theo một đoạn miêu tả.

**Ordered List**

Để khai báo một danh sách với kiểu được sắp xếp, bạn phải bắt đầu bằng cặp thẻ `<ol> </ol>`. Bên trong cặp thẻ này sẽ là danh sách các mục con, mỗi mục sẽ đặt trong cặp thẻ `<li> </li>`, xem ví dụ bên dưới.

```sh
<ol>
  <li>Mục con 1</li>
  <li>Mục con 2</li>
  <li>Mục con 3</li>
</ol>

<ol type="I">
  <li>Mục con 1</li>
  <li>Mục con 2</li>
  <li>Mục con 3</li>
</ol>
```

Thẻ `<ol>` cũng hỗ trợ thêm một thuộc tính nữa tên là type, thuộc tính này là để bạn thiết lập kiểu sắp xếp các mục con bên trong danh sách. Giá trị của thuộc tính type là 1, i, I, a, A

**Unordered List**

Giống như Ordered List, kiểu danh sách Unordered List sẽ bắt đầu bằng cặp thẻ `<ul> </ul>` và bên trong nó các mục con sẽ được khai báo bằng cặp thẻ `<li> </li>`.

```sh
<ul>
  <li>Mục con 1</li>
  <li>Mục con 2</li>
  <li>Mục con 3</li>
</ul>
```

Bạn cũng có thể thay đổi kiểu hiển thị của thẻ `<ol>` bằng cách thêm thuộc tính style với thuộc tính CSS là `list-style-type` và giá trị là `disc,square, circle` và none.

**Description List**

Với kiểu danh sách này thì cách viết thẻ hơi khác một tí, đó là nó sẽ bắt đầu danh sách bằng cặp thẻ `<dl> </dl>`, trong đó tên mỗi mục con sẽ được khai báo bằng cặp thẻ `<dt> </dt>` và mô tả cho mục con sẽ được khai báo bằng cặp thẻ `<dd> </dd>`.

```sh
<p>Một website gồm có</p>
<dl>
  <dt>HTML</dt>
  <dd>- khung xương của website.</dd>
  
  <dt>CSS</dt>
  <dd>- bộ da của website</dd>
  
  <dt>Javascript</dt>
  <dd>- bộ cánh của website</dd>
  
  <dt>Ngôn ngữ server-side (ASP.NET, PHP, RUBY,..)</dt>
  <dd>- linh hồn của website</dd>
</dl>
```

<a name="phan6"></a>
**6. Thẻ tạo liên kết và liên kết neo:
--------------------------------------

HTML Links - Syntax : `<a href="url">link text</a>`

Ví dụ : `<a href="http://www.w3schools.com/html/">Visit our HTML tutorial</a>`

Ngoài ra ta có thể đặt local link.

Ý nghĩa các thuộc tính:

- href: Địa chỉ của tài liệu muốn liên kết đến, đây có thể là một đường dẫn thư mục hoặc địa chỉ website. Nếu bạn muốn truy cập một tài liệu trên cùng một cấp thư mục thì chỉ cần ghi tên-tập-tin.định dạng (ví dụ: gioi-thieu.html).

- title: Tiêu đề của liên kết, tiêu đề sẽ hiển thị như một thông tin thêm khi rê chuột vào liên kết.

- target: Xác định nơi mở tài liệu, nó có các giá trị như _blank (mở tài liệu trên cửa sổ mới), _self (mở tài liệu trên cửa sổ hiện tại, nếu bạn không khai báo thuộc tính target thì nó sẽ sử dụng giá trị này làm mặc định),  _top (mở tài liệu trong nội dung trang hiện tại), _parent (mở tài liệu trên khung trình duyệt mẹ của nó).

Và một điều bạn cần biết đó là nội dung trong cặp thẻ `<a>` có thể là một nội dung siêu văn bản nào, bao gồm các thẻ tiêu đề, hình ảnh,…

<a name="phan7"></a>
**7. Chèn tập tin kỹ thuật số vào web
-------------------------------------

**Chèn ảnh**

ví dụ: `<img src="pic_mountain.jpg"title="muontain" alt="Mountain View" style="width:304px;height:228px;">`

Giải thích các thuộc tính:

- src: Đường dẫn đến tập tin hình ảnh.

- title: Tiêu đề của hình ảnh.

- alt: Tên định danh của hình ảnh.

**Chèn video**

dùng `<video> </video>`

**Chèn âm thanh – nhạc**

Giống như thẻ `<video>`, để chèn âm thanh vào tài liệu HTML thì bạn có thể sử dụng thẻ `<audio>` và thẻ này cũng là HTML5.

<a name="phan8"></a>
**8.Tạo form nhập liệu
----------------------

Ở HTML, để tạo form chúng ta sẽ sử dụng cặp thẻ `<form> </form>`, thẻ này sẽ chứa một vài thuộc tính quan trọng và nội dung bên trong cặp thẻ đó là các thẻ `<input>` để khai báo các trường nhập liệu

ví dụ:
```sh
<form action="#" method="post" name="form ví dụ">
  ô nhập gì đó: <input type="text" name="ok" placeholder="ok" /> <br />
  vui mà: <input type="password" name="yes" placeholder="yes" /> <br />
  <input type="submit" name="submit" value="form" />
</form>
```
Các thuộc tính trong thẻ `<form>`:

- action: Đường dẫn đến một trang xử lý dữ liệu sau khi người dùng ấn nút gửi dữ liệu.

- method: Phương thức gửi dữ liệu.

- name: Tên của form.

**Các thuộc tính trong thẻ `<input>`**:

Danh sách các giá trị của thuộc tính type:

- button
- checkbox
- color
- date
- datetime
- email
- file
- hidden
- image
- month
- number
- password
- radio
- search
- submit
- text
- time
- url

