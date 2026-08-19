# 10. Bảng ghi nhớ nhanh

## 10.1. HTML

| Cú pháp               | Công dụng              |
| --------------------- | ---------------------- |
| `<h1>`                | Tiêu đề chính          |
| `<p>`                 | Đoạn văn               |
| `<ul>`                | Danh sách không thứ tự |
| `<ol>`                | Danh sách có thứ tự    |
| `<li>`                | Một mục danh sách      |
| `<a href="">`         | Liên kết               |
| `<img src="" alt="">` | Hình ảnh               |
| `<header>`            | Phần đầu               |
| `<nav>`               | Điều hướng             |
| `<main>`              | Nội dung chính         |
| `<section>`           | Khu vực nội dung       |
| `<article>`           | Nội dung độc lập       |
| `<footer>`            | Phần cuối              |
| `<div>`               | Vùng chứa chung        |

---

## 10.2. CSS cơ bản

| Thuộc tính         | Công dụng             |
| ------------------ | --------------------- |
| `color`            | Màu chữ               |
| `background-color` | Màu nền               |
| `font-family`      | Font chữ              |
| `font-size`        | Kích thước chữ        |
| `font-weight`      | Độ đậm                |
| `line-height`      | Khoảng cách dòng      |
| `text-align`       | Căn chữ               |
| `width`            | Chiều rộng            |
| `height`           | Chiều cao             |
| `padding`          | Khoảng cách bên trong |
| `border`           | Viền                  |
| `margin`           | Khoảng cách bên ngoài |
| `border-radius`    | Bo góc                |
| `box-shadow`       | Đổ bóng               |

---

## 10.3. Selector

| Selector   | Ví dụ           | Ý nghĩa                      |
| ---------- | --------------- | ---------------------------- |
| Tag        | `p`             | Chọn tất cả thẻ `p`          |
| Class      | `.card`         | Chọn phần tử có class `card` |
| ID         | `#title`        | Chọn phần tử có ID `title`   |
| Descendant | `.card p`       | Chọn `p` bên trong `.card`   |
| Child      | `.list > li`    | Chọn `li` con trực tiếp      |
| Hover      | `.button:hover` | Khi rê chuột                 |

---

## 10.4. Box Model

```text
Margin
└── Border
    └── Padding
        └── Content
```

| Thành phần | Vị trí         |
| ---------- | -------------- |
| Content    | Nội dung       |
| Padding    | Bên trong viền |
| Border     | Viền           |
| Margin     | Bên ngoài viền |

---

## 10.5. Position

| Giá trị    | Mốc định vị                            |         Giữ chỗ? |
| ---------- | -------------------------------------- | ---------------: |
| `static`   | Normal flow                            |               Có |
| `relative` | Vị trí ban đầu                         |               Có |
| `absolute` | Positioned ancestor gần nhất           |            Không |
| `fixed`    | Viewport trong trường hợp thông thường |            Không |
| `sticky`   | Vị trí cuộn và ngưỡng                  | Có trước khi bám |

---

## 10.6. Display

| Giá trị        | Đặc điểm                                     |
| -------------- | -------------------------------------------- |
| `block`        | Xuống dòng, thường chiếm chiều rộng khả dụng |
| `inline`       | Nằm cùng dòng, theo nội dung                 |
| `inline-block` | Cùng dòng nhưng đặt được kích thước          |
| `none`         | Không hiển thị và không giữ chỗ              |

---

## 10.7. Flexbox

| Thuộc tính        | Đặt ở đâu? | Công dụng             |
| ----------------- | ---------- | --------------------- |
| `display: flex`   | Cha        | Tạo flex container    |
| `flex-direction`  | Cha        | Chọn hướng main axis  |
| `justify-content` | Cha        | Căn theo main axis    |
| `align-items`     | Cha        | Căn theo cross axis   |
| `flex-wrap`       | Cha        | Cho phép xuống dòng   |
| `gap`             | Cha        | Khoảng cách giữa item |
| `flex-grow`       | Con        | Mức độ giãn           |
| `flex-shrink`     | Con        | Mức độ co             |
| `flex-basis`      | Con        | Kích thước cơ sở      |
| `align-self`      | Con        | Căn riêng một item    |
| `order`           | Con        | Thứ tự hiển thị       |

---

## 10.8. Responsive

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
/>
```

```css
img {
  max-width: 100%;
  height: auto;
}
```

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

---
