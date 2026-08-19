# 2. Buổi 1 – Website và HTML cơ bản

## 2.1. Website là gì?

### [JSB] Website

Website là tập hợp nhiều trang thông tin có thể được truy cập qua Internet.

Ví dụ một website cá nhân có thể gồm:

```text
Trang chủ
Trang giới thiệu
Trang dự án
Trang liên hệ
```

### [JSB] Webpage

Webpage là một trang riêng lẻ trong website.

Ví dụ:

```text
index.html
about.html
projects.html
contact.html
```

Mỗi file HTML có thể đại diện cho một webpage.

### Phân biệt

| Khái niệm | Giải thích                          |
| --------- | ----------------------------------- |
| Website   | Tập hợp nhiều trang có liên quan    |
| Webpage   | Một trang riêng lẻ trong website    |
| Homepage  | Trang chính, thường là `index.html` |

---

## 2.2. Vai trò của HTML, CSS và JavaScript

| Công nghệ  | Vai trò                       | Ví dụ                       |
| ---------- | ----------------------------- | --------------------------- |
| HTML       | Xây dựng cấu trúc và nội dung | Tiêu đề, đoạn văn, hình ảnh |
| CSS        | Trang trí và bố trí giao diện | Màu sắc, font, khoảng cách  |
| JavaScript | Tạo logic và tương tác        | Nhấn nút, xử lý form        |

Có thể hình dung:

```text
HTML       = Bộ xương
CSS        = Quần áo và cách trang trí
JavaScript = Hành động và phản ứng
```

Trong Buổi 1–5, nội dung chính tập trung vào HTML và CSS.

---

## 2.3. Các khái niệm web cơ bản

| Khái niệm | Ý nghĩa                                                |
| --------- | ------------------------------------------------------ |
| W3C       | Tổ chức xây dựng và phát triển các tiêu chuẩn web      |
| URL       | Địa chỉ của một tài nguyên trên Internet               |
| HTTP      | Giao thức trao đổi dữ liệu giữa trình duyệt và máy chủ |
| HTTPS     | HTTP có thêm cơ chế bảo vệ dữ liệu                     |
| DNS       | Hệ thống tìm địa chỉ IP từ tên miền                    |
| Browser   | Trình duyệt như Chrome, Edge, Firefox                  |
| Server    | Máy chủ lưu và cung cấp tài nguyên website             |

Ví dụ URL:

```text
https://example.com/about.html
```

Phân tích đơn giản:

```text
https://        → Giao thức
example.com     → Tên miền
/about.html     → Đường dẫn tài nguyên
```

---

## 2.4. Website hoạt động như thế nào?

Luồng hoạt động cơ bản:

```text
1. Người dùng nhập URL
            ↓
2. Trình duyệt tìm địa chỉ máy chủ thông qua DNS
            ↓
3. Trình duyệt gửi HTTP/HTTPS Request
            ↓
4. Máy chủ nhận và xử lý yêu cầu
            ↓
5. Máy chủ trả về HTML, CSS, ảnh...
            ↓
6. Trình duyệt đọc và hiển thị website
```

### Ví dụ thực tế

Khi bạn nhập:

```text
https://example.com
```

Trình duyệt có thể nhận:

```text
index.html
style.css
avatar.jpg
logo.svg
```

Sau đó:

- HTML tạo nội dung.
- CSS tạo giao diện.
- Ảnh được hiển thị tại vị trí do HTML quy định.
- JavaScript, nếu có, xử lý tương tác.

### Câu hỏi gợi mở

Nếu phần chữ xuất hiện nhưng ảnh không hiển thị, lỗi có thể nằm ở đâu?

- Toàn bộ máy chủ?
- Đường dẫn ảnh?
- Tên file ảnh?
- Chữ hoa và chữ thường trong tên file?

---

## 2.5. Tổ chức thư mục học tập

### Cấu trúc theo từng buổi

```text
TEN_LOP/
├── SS1/
├── SS2/
├── SS3/
├── SS4/
└── SS5/
```

### Cấu trúc một dự án website

```text
portfolio-quang/
├── index.html
├── about.html
├── projects.html
├── css/
│   └── style.css
└── images/
    ├── avatar.jpg
    └── project-1.jpg
```

### Ý nghĩa

| File hoặc thư mục | Công dụng             |
| ----------------- | --------------------- |
| `index.html`      | Trang chủ             |
| `about.html`      | Trang giới thiệu      |
| `projects.html`   | Trang dự án           |
| `css/style.css`   | File CSS dùng chung   |
| `images/`         | Thư mục chứa hình ảnh |

### Quy tắc đặt tên nên dùng

Nên:

```text
avatar.jpg
project-card.jpg
about.html
style.css
```

Không nên:

```text
Ảnh của em.JPG
Trang Giới Thiệu.HTML
style mới nhất 2.css
```

Lý do:

- Khoảng trắng dễ làm đường dẫn khó đọc.
- Chữ hoa và chữ thường có thể gây lỗi khi deploy.
- Tên không rõ chức năng khiến dự án khó quản lý.
- Ký tự tiếng Việt đôi khi gây vấn đề trên một số hệ thống.

---

## 2.6. Visual Studio Code

### Các khu vực chính

| Khu vực    | Công dụng                   |
| ---------- | --------------------------- |
| Explorer   | Quản lý file và thư mục     |
| Editor     | Viết và chỉnh sửa code      |
| Extensions | Cài tiện ích                |
| Terminal   | Chạy lệnh                   |
| Problems   | Xem một số lỗi              |
| Status Bar | Xem thông tin file hiện tại |

### Tiện ích thường dùng

- Live Server.
- Auto Rename Tag.
- CSS Formatter.
- Material Icon Theme.

### Quy trình chạy website

1. Mở VS Code.
2. Chọn **File → Open Folder**.
3. Mở đúng thư mục dự án.
4. Mở `index.html`.
5. Lưu file.
6. Nhấn chuột phải.
7. Chọn **Open with Live Server**.
8. Quan sát kết quả trên trình duyệt.

### Phím lưu file

Windows:

```text
Ctrl + S
```

macOS:

```text
Cmd + S
```

### Lỗi thường gặp

- Mở từng file thay vì mở cả folder.
- File có tên `index.html.txt`.
- Viết code nhưng chưa lưu.
- Live Server đang chạy một folder khác.
- Đường dẫn CSS hoặc ảnh bị sai.

---

## 2.7. Bộ khung HTML5

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />

    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />

    <title>Portfolio của Quang</title>
  </head>

  <body>
    <h1>Xin chào, mình là Quang</h1>

    <p>Mình đang học Web Developer Basic.</p>
  </body>
</html>
```

### Giải thích

| Thành phần               | Công dụng                               |
| ------------------------ | --------------------------------------- |
| `<!DOCTYPE html>`        | Khai báo tài liệu HTML5                 |
| `<html>`                 | Phần tử gốc của trang                   |
| `lang="vi"`              | Ngôn ngữ chính là tiếng Việt            |
| `<head>`                 | Thông tin cấu hình của trang            |
| `<meta charset="UTF-8">` | Hiển thị tiếng Việt đúng                |
| `<meta name="viewport">` | Hỗ trợ responsive trên thiết bị di động |
| `<title>`                | Tiêu đề tab trình duyệt                 |
| `<body>`                 | Nội dung người dùng nhìn thấy           |

---

## 2.8. Thẻ HTML và phần tử HTML

Ví dụ:

```html
<p>Mình đang học HTML.</p>
```

Phân tích:

```text
<p>                  → Thẻ mở
Mình đang học HTML.  → Nội dung
</p>                 → Thẻ đóng
```

Toàn bộ đoạn trên được gọi là một HTML element.

---

## 2.9. Thẻ tiêu đề

```html
<h1>Portfolio của Quang</h1>
<h2>Giới thiệu</h2>
<h3>Sở thích</h3>
```

HTML có tiêu đề từ:

```text
<h1> đến <h6>
```

### Cách dùng hợp lý

- `<h1>`: tiêu đề chính của trang.
- `<h2>`: tiêu đề của một khu vực lớn.
- `<h3>`: tiêu đề nhỏ nằm trong khu vực `<h2>`.

Không nên chọn `<h1>` chỉ vì muốn chữ to. Kích thước chữ nên được chỉnh bằng CSS.

---

## 2.10. Thẻ đoạn văn

```html
<p>
  Mình tên là Quang. Mình đang học JSB và muốn xây dựng
  một website cá nhân.
</p>
```

Mỗi ý tương đối độc lập nên được đặt trong một thẻ `<p>` riêng.

```html
<p>Mình đang học HTML.</p>

<p>Mục tiêu của mình là tạo được Portfolio cá nhân.</p>
```

---

## 2.11. Chú thích HTML

```html
<!-- Đây là phần giới thiệu -->
<section>
  <h2>Giới thiệu</h2>
</section>
```

Chú thích:

- Không xuất hiện trên website.
- Giúp người viết code ghi nhớ chức năng của từng phần.
- Không nên ghi thông tin bí mật trong chú thích.

---

## 2.12. Bài thực hành Buổi 1

Tạo file `index.html`:

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />

    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />

    <title>Giới thiệu Quang</title>
  </head>

  <body>
    <h1>Xin chào, mình là Quang</h1>

    <h2>Thông tin cá nhân</h2>

    <p>Tuổi: ...</p>
    <p>Trường: ...</p>

    <h2>Sở thích</h2>

    <p>Mình thích học lập trình và chơi thể thao.</p>

    <h2>Mục tiêu</h2>

    <p>
      Mục tiêu của mình là xây dựng được một website cá nhân
      bằng HTML và CSS.
    </p>
  </body>
</html>
```

### Thử thách

1. Thêm một tiêu đề cấp 3 cho môn học yêu thích.
2. Thêm hai đoạn văn giới thiệu mục tiêu học web.
3. Đổi nội dung trong `<title>`.
4. Quan sát sự thay đổi trên tab trình duyệt.
5. Cố ý xóa một thẻ đóng.
6. Quan sát kết quả rồi sửa lại.

---
