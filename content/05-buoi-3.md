# 4. Buổi 3 – CSS, Selector, DevTools và Box Model

## 4.1. CSS là gì?

CSS giúp thay đổi:

- Màu chữ.
- Màu nền.
- Font chữ.
- Kích thước.
- Khoảng cách.
- Viền.
- Bố cục.
- Hiệu ứng giao diện.

---

## 4.2. Cấu trúc một quy tắc CSS

```css
selector {
  property: value;
}
```

Ví dụ:

```css
h1 {
  color: darkorange;
  font-size: 40px;
  text-align: center;
}
```

Phân tích:

```text
h1          → selector
color       → property
darkorange  → value
```

Một selector có thể có nhiều khai báo:

```css
p {
  color: #333333;
  font-family: Arial, sans-serif;
  font-size: 18px;
  line-height: 1.6;
}
```

---

## 4.3. Ba cách viết CSS

### Inline CSS

```html
<p style="color: red; font-size: 20px;">
  Nội dung
</p>
```

Hạn chế:

- Khó tái sử dụng.
- HTML dài và rối.
- Khó sửa nhiều phần tử cùng lúc.

### Internal CSS

```html
<head>
  <style>
    p {
      color: blue;
    }
  </style>
</head>
```

Phù hợp với:

- Ví dụ ngắn.
- Trang thử nghiệm.
- Một file HTML đơn giản.

### External CSS

Trong HTML:

```html
<link
  rel="stylesheet"
  href="./css/style.css"
/>
```

Trong `style.css`:

```css
p {
  color: green;
}
```

External CSS nên được ưu tiên trong dự án vì:

- HTML và CSS tách riêng.
- Nhiều trang dùng chung một file.
- Dễ sửa và quản lý.

---

## 4.4. CSS Selector

### Tag selector

```css
p {
  color: #333333;
}
```

Chọn tất cả thẻ `<p>`.

### Class selector

HTML:

```html
<p class="highlight">
  Nội dung quan trọng
</p>

<p class="highlight">
  Nội dung khác
</p>
```

CSS:

```css
.highlight {
  color: orange;
  font-weight: bold;
}
```

Một class có thể dùng cho nhiều phần tử.

### ID selector

HTML:

```html
<h1 id="main-title">
  Portfolio của Quang
</h1>
```

CSS:

```css
#main-title {
  color: navy;
}
```

Một ID nên đại diện cho một phần tử duy nhất trên trang.

### Selector con cháu

```css
.project-card p {
  color: gray;
}
```

Chỉ chọn các thẻ `<p>` nằm bên trong `.project-card`.

### Chọn nhiều selector

```css
h1,
h2,
h3 {
  font-family: Arial, sans-serif;
}
```

### Một phần tử có nhiều class

```html
<article class="card featured">
  Nội dung
</article>
```

```css
.card {
  padding: 20px;
}

.featured {
  border: 3px solid orange;
}
```

Chọn phần tử có đồng thời hai class:

```css
.card.featured {
  background-color: lightyellow;
}
```

---

## 4.5. Quy tắc đặt class

Nên đặt theo ý nghĩa:

```html
<nav class="main-navigation"></nav>

<section class="project-list"></section>

<article class="project-card"></article>
```

Không nên đặt theo giao diện tạm thời:

```html
<div class="red-box"></div>
```

Nếu sau này đổi màu xanh, tên `red-box` trở nên không đúng.

Tốt hơn:

```html
<div class="warning-box"></div>
```

---

## 4.6. Các thuộc tính CSS cơ bản

### Màu chữ

```css
.title {
  color: #f97316;
}
```

### Màu nền

```css
.card {
  background-color: #fff7ed;
}
```

### Font chữ

```css
body {
  font-family: Arial, Helvetica, sans-serif;
}
```

### Kích thước chữ

```css
h1 {
  font-size: 40px;
}
```

### Căn chữ

```css
h1 {
  text-align: center;
}
```

### Độ đậm

```css
strong {
  font-weight: 700;
}
```

### Khoảng cách dòng

```css
p {
  line-height: 1.6;
}
```

### Bo góc

```css
.card {
  border-radius: 16px;
}
```

### Đổ bóng

```css
.card {
  box-shadow: 0 8px 24px rgb(0 0 0 / 10%);
}
```

---

## 4.7. Đơn vị CSS

| Đơn vị | Ý nghĩa                       | Thường dùng                |
| ------ | ----------------------------- | -------------------------- |
| `px`   | Pixel cố định                 | Viền, icon, kích thước nhỏ |
| `%`    | Theo kích thước phần tử cha   | Chiều rộng linh hoạt       |
| `rem`  | Theo kích thước chữ gốc       | Font, padding, margin      |
| `vw`   | Phần trăm chiều rộng viewport | Kích thước theo màn hình   |
| `vh`   | Phần trăm chiều cao viewport  | Hero toàn màn hình         |

Ví dụ:

```css
.container {
  width: 90%;
  max-width: 1100px;
}

h1 {
  font-size: 2.5rem;
}
```

Ở giai đoạn đầu, có thể dùng `px`. Khi quen hơn, dùng `rem` cho font và khoảng cách.

---

## 4.8. CSS Box Model

Mỗi phần tử HTML có thể được xem như một chiếc hộp.

```text
┌──────────────────────── Margin ────────────────────────┐
│  ┌───────────────────── Border ─────────────────────┐  │
│  │  ┌────────────────── Padding ─────────────────┐  │  │
│  │  │                  Content                   │  │  │
│  │  └────────────────────────────────────────────┘  │  │
│  └──────────────────────────────────────────────────┘  │
└────────────────────────────────────────────────────────┘
```

### Content

Nội dung của phần tử:

- Chữ.
- Ảnh.
- Video.
- Phần tử con.

### Padding

Khoảng cách bên trong, từ content đến border.

```css
.card {
  padding: 20px;
}
```

### Border

Viền của phần tử.

```css
.card {
  border: 2px solid orange;
}
```

### Margin

Khoảng cách bên ngoài, giữa phần tử với xung quanh.

```css
.card {
  margin: 24px;
}
```

---

## 4.9. Tính kích thước Box Model

```css
.box {
  width: 200px;
  padding: 20px;
  border: 5px solid black;
}
```

Với `content-box` mặc định:

```text
Tổng chiều rộng
= content
+ padding trái
+ padding phải
+ border trái
+ border phải

= 200 + 20 + 20 + 5 + 5
= 250px
```

Margin không thuộc kích thước bên trong hộp nhưng tạo khoảng cách bên ngoài.

---

## 4.10. [Mở rộng nhẹ] `box-sizing`

```css
* {
  box-sizing: border-box;
}
```

Khi dùng `border-box`, giá trị `width` đã bao gồm:

- Content.
- Padding.
- Border.

Ví dụ:

```css
.box {
  box-sizing: border-box;

  width: 200px;
  padding: 20px;
  border: 5px solid black;
}
```

Tổng chiều rộng vẫn là `200px`.

Quy tắc thường đặt ở đầu file CSS:

```css
*,
*::before,
*::after {
  box-sizing: border-box;
}
```

---

## 4.11. Căn giữa container

```css
.container {
  width: 90%;
  max-width: 1100px;
  margin: 0 auto;
}
```

Giải thích:

- `width: 90%`: không sát hai bên màn hình.
- `max-width: 1100px`: không quá rộng trên desktop.
- `margin: 0 auto`: căn giữa theo chiều ngang.

---

## 4.12. DevTools

Mở DevTools bằng:

- Chuột phải → **Inspect**.
- `F12`.
- `Ctrl + Shift + I`.

### Các tab chính

| Tab         | Công dụng                         |
| ----------- | --------------------------------- |
| Elements    | Xem và thử chỉnh HTML, CSS        |
| Console     | Xem thông báo hoặc lỗi JavaScript |
| Network     | Xem tài nguyên được tải           |
| Sources     | Xem mã nguồn                      |
| Application | Xem dữ liệu trình duyệt           |
| Performance | Phân tích hiệu suất               |

### Quy trình tìm lỗi CSS

1. Chuột phải vào phần tử bị lỗi.
2. Chọn **Inspect**.
3. Kiểm tra phần tử có đúng class không.
4. Xem bảng **Styles**.
5. Xem thuộc tính nào bị gạch ngang.
6. Thử thay đổi giá trị.
7. Khi tìm được kết quả đúng, sửa lại trong file CSS.
8. Lưu file.

Thay đổi trong DevTools chỉ mang tính thử nghiệm. Khi tải lại trang, thay đổi có thể mất.

---

## 4.13. Bài thực hành Buổi 3: Profile Card

HTML:

```html
<article class="profile-card">
  <img
    class="profile-card__image"
    src="./images/avatar.jpg"
    alt="Ảnh đại diện của Quang"
  />

  <h2 class="profile-card__title">
    Quang
  </h2>

  <p class="profile-card__description">
    Học viên JSB, yêu thích lập trình web.
  </p>

  <a
    class="profile-card__link"
    href="./about.html"
  >
    Xem giới thiệu
  </a>
</article>
```

CSS:

```css
.profile-card {
  width: 320px;
  margin: 40px auto;
  padding: 24px;

  background-color: white;
  border: 1px solid #dddddd;
  border-radius: 16px;

  box-shadow: 0 8px 24px rgb(0 0 0 / 10%);
}

.profile-card__image {
  width: 100%;
  border-radius: 12px;
}

.profile-card__title {
  color: darkorange;
}

.profile-card__description {
  color: #555555;
  line-height: 1.6;
}

.profile-card__link {
  display: inline-block;

  margin-top: 12px;
  padding: 10px 16px;

  color: white;
  background-color: darkorange;
  border-radius: 8px;

  text-decoration: none;
}
```

### Thử thách

1. Thay `padding: 24px` thành `0`.
2. Quan sát nội dung sát viền như thế nào.
3. Đổi `margin` thành `padding`.
4. Giải thích sự khác biệt.
5. Dùng DevTools đổi màu nút.
6. Ghi lại thay đổi vào file CSS.

---
