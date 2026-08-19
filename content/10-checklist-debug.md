# 9. Checklist debug

## 9.1. HTML không hiển thị đúng

Kiểm tra:

1. File có đuôi `.html` không?
2. Đã lưu file chưa?
3. Nội dung có nằm trong `<body>` không?
4. Thẻ mở và đóng có đúng không?
5. Có lồng sai thẻ không?
6. Live Server có chạy đúng folder không?

---

## 9.2. CSS không hoạt động

### Kiểm tra liên kết CSS

```html
<link
  rel="stylesheet"
  href="./css/style.css"
/>
```

Đối chiếu với cấu trúc thư mục.

### Kiểm tra selector

HTML:

```html
<div class="project-card"></div>
```

CSS đúng:

```css
.project-card {
}
```

Không phải:

```css
#project-card {
}
```

### Kiểm tra dấu ngoặc

Sai:

```css
.card {
  color: red;
```

Đúng:

```css
.card {
  color: red;
}
```

### Kiểm tra cascade

Trong DevTools, thuộc tính bị gạch ngang thường có nghĩa một quy tắc khác đang thắng.

---

## 9.3. Ảnh không hiển thị

Kiểm tra:

- Tên file có đúng không?
- Phần mở rộng có đúng không?
- `avatar.jpg` và `avatar.JPG` có khác nhau không?
- Ảnh có nằm đúng thư mục không?
- Đường dẫn có cần `../` không?
- Tên file có khoảng trắng không?

---

## 9.4. Position không đúng

Kiểm tra:

- Phần tử con có `position: absolute` không?
- Phần tử cha có `position: relative` không?
- Có đặt `top`, `right`, `bottom`, `left` không?
- Phần tử có bị che không?
- Có cần `z-index` không?

---

## 9.5. Flexbox không hoạt động

Kiểm tra:

- `display: flex` có đặt vào cha không?
- Item có thực sự là con của container không?
- Đang dùng `row` hay `column`?
- Đang căn theo main axis hay cross axis?
- Container có đủ chiều cao không?
- Có cần `flex-wrap: wrap` không?

---

## 9.6. Responsive không hoạt động

### Kiểm tra viewport

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
/>
```

### Kiểm tra thứ tự CSS

```css
.hero {
  flex-direction: row;
}

@media (max-width: 720px) {
  .hero {
    flex-direction: column;
  }
}
```

Media Query thường nên đặt sau CSS mặc định.

### Kiểm tra selector

Sai:

```css
.hero-section {
  display: flex;
}

@media (max-width: 720px) {
  .hero {
    flex-direction: column;
  }
}
```

`.hero-section` và `.hero` là hai class khác nhau.

### Kiểm tra width cố định

```css
.card {
  width: 1000px;
}
```

Đây có thể là nguyên nhân gây tràn ngang.

---

## 9.7. Quy trình debug tổng quát

```text
1. Xác định phần tử bị lỗi
2. Inspect phần tử
3. Kiểm tra HTML và class
4. Kiểm tra CSS đang áp dụng
5. Kiểm tra quy tắc bị ghi đè
6. Thử thay đổi trong DevTools
7. Sửa lại trong file
8. Lưu và kiểm tra lại
```

---

## 9.8. Chụp màn hình khi cần gửi lỗi

Windows:

```text
Win + Shift + S
```

macOS:

```text
Shift + Cmd + 4
```

hoặc:

```text
Shift + Cmd + 5
```

Nên chụp:

- Đoạn code liên quan.
- Explorer và cấu trúc folder.
- Giao diện đang lỗi.
- Bảng Styles trong DevTools.

---
