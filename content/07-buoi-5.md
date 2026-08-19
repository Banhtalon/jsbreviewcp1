# 6. Buổi 5 – Display, Responsive và Flexbox

## 6.1. Thuộc tính `display`

### `display: block`

```css
.element {
  display: block;
}
```

Đặc điểm:

- Bắt đầu ở dòng mới.
- Thường chiếm toàn bộ chiều rộng khả dụng.
- Có thể đặt `width` và `height`.

Phần tử block thường gặp:

- `<div>`
- `<section>`
- `<p>`
- `<h1>`

### `display: inline`

```css
.element {
  display: inline;
}
```

Đặc điểm:

- Không tự xuống dòng.
- Chiếm chiều rộng theo nội dung.
- `width` và `height` không hoạt động như block.

Phần tử inline thường gặp:

- `<span>`
- `<a>`

### `display: inline-block`

```css
.button {
  display: inline-block;

  width: 160px;
  padding: 12px;
}
```

Đặc điểm:

- Có thể nằm cùng dòng.
- Đặt được width, height và padding giống block.

### `display: none`

```css
.menu {
  display: none;
}
```

Đặc điểm:

- Không hiển thị.
- Không chiếm chỗ trong layout.

---

## 6.2. [Mở rộng nhẹ] `visibility: hidden`

```css
.box {
  visibility: hidden;
}
```

So sánh:

| Thuộc tính           | Có nhìn thấy? | Có giữ chỗ? |
| -------------------- | ------------: | ----------: |
| `display: none`      |         Không |       Không |
| `visibility: hidden` |         Không |          Có |

---

## 6.3. Responsive Web Design

Responsive Web Design giúp website thích nghi với nhiều kích thước màn hình:

- Desktop.
- Laptop.
- Tablet.
- Điện thoại.
- Màn hình ngang và dọc.

Ba nguyên tắc chính:

1. Bố cục linh hoạt.
2. Hình ảnh linh hoạt.
3. Media Queries.

---

## 6.4. Viewport meta tag

Đặt trong `<head>`:

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1.0"
/>
```

Dòng này giúp:

- Trình duyệt mobile sử dụng đúng chiều rộng thiết bị.
- Media Query hoạt động như dự kiến.
- Trang không bị thu nhỏ giả lập.

---

## 6.5. Tránh width cố định quá lớn

Không nên:

```css
.container {
  width: 1200px;
}
```

Trên điện thoại, phần tử có thể tràn ngang.

Tốt hơn:

```css
.container {
  width: 90%;
  max-width: 1200px;
  margin: 0 auto;
}
```

---

## 6.6. Ảnh responsive

```css
img {
  max-width: 100%;
  height: auto;
}
```

Ý nghĩa:

- Ảnh không vượt quá phần tử chứa.
- Ảnh giữ tỷ lệ gốc.
- Giảm nguy cơ tràn ngang.

---

## 6.7. Media Queries

Cú pháp:

```css
@media screen and (max-width: 768px) {
  body {
    background-color: lightyellow;
  }
}
```

Ý nghĩa:

- Áp dụng cho màn hình.
- Khi viewport rộng tối đa `768px`.
- CSS bên trong được kích hoạt.

### Ví dụ đổi bố cục

Desktop:

```css
.hero {
  display: flex;
  flex-direction: row;
}
```

Mobile:

```css
@media screen and (max-width: 768px) {
  .hero {
    flex-direction: column;
  }
}
```

---

## 6.8. Breakpoint

Các mốc tham khảo:

|      Mốc | Thiết bị gợi ý      |
| -------: | ------------------- |
|  `320px` | Điện thoại nhỏ      |
|  `480px` | Điện thoại phổ biến |
|  `768px` | Tablet              |
|  `992px` | Laptop              |
| `1200px` | Desktop             |

Breakpoint không phải luật cứng.

Nên tạo breakpoint tại thời điểm:

- Nội dung bắt đầu chật.
- Menu bị tràn.
- Card quá nhỏ.
- Chữ khó đọc.
- Hình ảnh làm vỡ bố cục.

---

## 6.9. Desktop-first

Viết giao diện desktop trước, sau đó dùng `max-width`.

```css
.card-list {
  display: flex;
}

@media (max-width: 768px) {
  .card-list {
    flex-direction: column;
  }
}
```

---

## 6.10. [Mở rộng nhẹ] Mobile-first

Viết giao diện mobile trước, sau đó dùng `min-width`.

```css
.card-list {
  display: flex;
  flex-direction: column;
}

@media (min-width: 768px) {
  .card-list {
    flex-direction: row;
  }
}
```

Nên chọn một hướng nhất quán trong dự án.

---

## 6.11. Flexbox là gì?

Flexbox là mô hình bố cục một chiều.

Nó phù hợp để sắp xếp phần tử theo:

- Một hàng.
- Một cột.

HTML:

```html
<div class="container">
  <div class="item">Item 1</div>
  <div class="item">Item 2</div>
  <div class="item">Item 3</div>
</div>
```

CSS:

```css
.container {
  display: flex;
}
```

- `.container`: flex container.
- `.item`: flex items.

`display: flex` phải được đặt vào phần tử cha.

---

## 6.12. Main axis và Cross axis

### Khi `flex-direction: row`

```text
Main axis  → ngang
Cross axis → dọc
```

### Khi `flex-direction: column`

```text
Main axis  → dọc
Cross axis → ngang
```

Ghi nhớ:

- `justify-content`: căn theo main axis.
- `align-items`: căn theo cross axis.

---

## 6.13. `flex-direction`

```css
.container {
  display: flex;
  flex-direction: row;
}
```

Các giá trị:

| Giá trị          | Kết quả                   |
| ---------------- | ------------------------- |
| `row`            | Ngang, thứ tự bình thường |
| `row-reverse`    | Ngang, đảo thứ tự         |
| `column`         | Dọc, thứ tự bình thường   |
| `column-reverse` | Dọc, đảo thứ tự           |

---

## 6.14. `justify-content`

```css
.container {
  display: flex;
  justify-content: space-between;
}
```

Các giá trị phổ biến:

| Giá trị         | Kết quả                        |
| --------------- | ------------------------------ |
| `flex-start`    | Dồn về đầu main axis           |
| `flex-end`      | Dồn về cuối main axis          |
| `center`        | Căn giữa                       |
| `space-between` | Khoảng trống nằm giữa các item |
| `space-around`  | Có khoảng trống quanh mỗi item |
| `space-evenly`  | Các khoảng trống gần bằng nhau |

Ví dụ navbar:

```css
.navbar {
  display: flex;
  justify-content: space-between;
}
```

Logo ở đầu, menu ở cuối.

---

## 6.15. `align-items`

```css
.container {
  display: flex;
  align-items: center;
}
```

Các giá trị:

| Giá trị      | Kết quả                  |
| ------------ | ------------------------ |
| `flex-start` | Căn đầu cross axis       |
| `flex-end`   | Căn cuối cross axis      |
| `center`     | Căn giữa cross axis      |
| `stretch`    | Kéo giãn item            |
| `baseline`   | Căn theo đường cơ sở chữ |

### Vì sao `align-items: center` đôi khi không thấy tác dụng?

Nếu container không cao hơn item, không có khoảng trống để quan sát việc căn giữa.

Thử:

```css
.container {
  display: flex;
  align-items: center;

  min-height: 300px;
}
```

---

## 6.16. `flex-wrap`

```css
.product-list {
  display: flex;
  flex-wrap: wrap;
}
```

Nếu không đủ chỗ, item được xuống dòng.

Không có wrap:

```text
[Card][Card][Card][Card] → Có thể bị ép hoặc tràn
```

Có wrap:

```text
[Card][Card][Card]
[Card]
```

---

## 6.17. [Mở rộng nhẹ] `gap`

```css
.product-list {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
}
```

`gap` tạo khoảng cách giữa các item.

Có thể dùng:

```css
gap: 16px;
```

Hoặc:

```css
row-gap: 24px;
column-gap: 16px;
```

---

## 6.18. `flex-grow`

```css
.item {
  flex-grow: 1;
}
```

Xác định item được giãn ra bao nhiêu khi còn không gian.

```css
.item-a {
  flex-grow: 1;
}

.item-b {
  flex-grow: 2;
}
```

Item B nhận phần không gian dư theo tỷ lệ lớn hơn item A.

---

## 6.19. `flex-shrink`

```css
.item {
  flex-shrink: 1;
}
```

Xác định khả năng co lại khi thiếu không gian.

---

## 6.20. `flex-basis`

```css
.item {
  flex-basis: 240px;
}
```

Đây là kích thước cơ sở của item trước khi giãn hoặc co.

---

## 6.21. Cú pháp rút gọn `flex`

```css
.item {
  flex: 1 1 240px;
}
```

Tương ứng:

```text
flex-grow:   1
flex-shrink: 1
flex-basis:  240px
```

Ví dụ card responsive:

```css
.project-card {
  flex: 1 1 280px;
}
```

---

## 6.22. `align-self`

```css
.special-item {
  align-self: flex-end;
}
```

Căn riêng một item trên cross axis.

---

## 6.23. [Mở rộng nhẹ] `order`

```css
.first-item {
  order: -1;
}
```

Cho phép thay đổi thứ tự hiển thị.

Cần thận trọng vì thứ tự hiển thị có thể khác thứ tự trong HTML.

---

## 6.24. Navbar bằng Flexbox

HTML:

```html
<header class="site-header">
  <div class="navbar">
    <a
      class="logo"
      href="./index.html"
    >
      Quang.dev
    </a>

    <nav>
      <ul class="nav-list">
        <li>
          <a href="#about">
            Giới thiệu
          </a>
        </li>

        <li>
          <a href="#skills">
            Kỹ năng
          </a>
        </li>

        <li>
          <a href="#projects">
            Dự án
          </a>
        </li>
      </ul>
    </nav>
  </div>
</header>
```

CSS:

```css
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;

  min-height: 64px;
  padding: 0 24px;
}

.nav-list {
  display: flex;
  align-items: center;
  gap: 20px;

  margin: 0;
  padding: 0;

  list-style: none;
}
```

Responsive:

```css
@media (max-width: 640px) {
  .navbar {
    flex-direction: column;
    justify-content: center;
    gap: 12px;

    padding: 16px;
  }

  .nav-list {
    flex-wrap: wrap;
    justify-content: center;
  }
}
```

---

## 6.25. Danh sách card responsive

HTML:

```html
<div class="project-list">
  <article class="project-card">
    <h3>Portfolio</h3>

    <p>
      Website giới thiệu cá nhân.
    </p>
  </article>

  <article class="project-card">
    <h3>Product Page</h3>

    <p>
      Website hiển thị sản phẩm.
    </p>
  </article>

  <article class="project-card">
    <h3>The Flag</h3>

    <p>
      Dự án thực hành Position.
    </p>
  </article>
</div>
```

CSS:

```css
.project-list {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
}

.project-card {
  flex: 1 1 280px;

  padding: 24px;

  border: 1px solid #dddddd;
  border-radius: 16px;
}
```

---
