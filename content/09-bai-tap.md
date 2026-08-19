# 8. Bài tập thực hành theo cấp độ

## 8.1. Mức 1 – HTML cơ bản

Tạo trang giới thiệu có:

- Một `<h1>`.
- Hai `<h2>`.
- Ba đoạn văn.
- Một danh sách sở thích.
- Một ảnh có `alt`.

Chưa viết CSS.

### Tự kiểm tra

- Nội dung có nằm trong `<body>` không?
- `<title>` có đúng không?
- Ảnh có hiển thị không?
- Thẻ có đóng đúng thứ tự không?

---

## 8.2. Mức 2 – Website nhiều trang

Tạo:

```text
index.html
about.html
projects.html
```

Mỗi trang có:

- Header.
- Navigation.
- Main.
- Footer.

Yêu cầu:

- Từ trang nào cũng đi được đến hai trang còn lại.
- Chỉ dùng đường dẫn tương đối.
- Không dùng đường dẫn ổ đĩa máy tính.

Không nên:

```text
C:\Users\Quang\Desktop\portfolio\about.html
```

---

## 8.3. Mức 3 – CSS và Box Model

Trang trí Portfolio:

- Body có font chữ.
- Container có `max-width`.
- Card có padding.
- Card có border.
- Card có margin hoặc gap.
- Button dùng `inline-block`.

Thử thay:

```css
padding: 24px;
```

thành:

```css
margin: 24px;
```

Sau đó giải thích sự khác biệt.

---

## 8.4. Mức 4 – Position

Tạo card sản phẩm có:

- Ảnh.
- Tên.
- Giá.
- Badge “Giảm 20%”.
- Nút mua.

Yêu cầu:

- Badge nằm ở góc trên bên phải.
- Card làm mốc định vị.
- Badge không che nội dung quan trọng.

Sau đó xóa:

```css
position: relative;
```

khỏi card và quan sát kết quả.

---

## 8.5. Mức 5 – Flexbox

Tạo navbar:

```text
Logo                         Trang chủ | Dự án | Liên hệ
```

Yêu cầu:

- Logo ở bên trái.
- Menu ở bên phải.
- Căn giữa theo chiều dọc.
- Có khoảng cách giữa các link.
- Trên mobile, navbar chuyển thành cột.

---

## 8.6. Mức 6 – Danh sách sản phẩm responsive

Tạo ít nhất sáu card:

- Desktop: khoảng ba card mỗi hàng.
- Tablet: khoảng hai card mỗi hàng.
- Mobile: một card mỗi hàng.

Gợi ý:

```css
.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
}

.product-card {
  flex: 1 1 280px;
}
```

---

## 8.7. Mức 7 – Mô phỏng Checkpoint 1

Trong khoảng một buổi tự luyện, xây website cá nhân mà không xem code cũ.

Yêu cầu tối thiểu:

- HTML5 đúng cấu trúc.
- Semantic HTML.
- Navigation.
- Ảnh và danh sách.
- External CSS.
- Ít nhất hai loại selector.
- Box Model.
- Một phần tử Position.
- Một Flexbox.
- Một Media Query.
- Không tràn ngang ở màn hình nhỏ.

---
