# 5. Buổi 4 – Cascade, kế thừa và Position

## 5.1. Cascade là gì?

Cascade là cách trình duyệt quyết định quy tắc CSS nào được áp dụng khi có nhiều quy tắc cùng tác động lên một thuộc tính.

HTML:

```html
<p
  class="message"
  id="welcome"
>
  Xin chào Quang
</p>
```

CSS:

```css
p {
  color: black;
}

.message {
  color: blue;
}

#welcome {
  color: red;
}
```

Trong ví dụ, màu đỏ thắng vì ID selector có độ ưu tiên cao hơn class và tag selector.

---

## 5.2. Cách ghi nhớ cơ bản

Trong phạm vi cơ bản:

```text
ID selector > Class selector > Tag selector
```

Ví dụ:

```text
#welcome  >  .message  >  p
```

Inline CSS thường có mức ưu tiên cao hơn các quy tắc CSS thông thường.

```html
<p
  class="message"
  style="color: purple;"
>
  Nội dung
</p>
```

---

## 5.3. [Mở rộng nhẹ] Thứ tự xuất hiện

Nếu hai quy tắc có độ ưu tiên bằng nhau, quy tắc xuất hiện sau thường thắng.

```css
.note {
  color: red;
}

.note {
  color: blue;
}
```

Kết quả:

```text
Màu xanh
```

---

## 5.4. [Mở rộng nhẹ] Internal và External CSS

Không nên hiểu rằng Internal CSS luôn mạnh hơn External CSS.

Ví dụ:

```html
<head>
  <style>
    .note {
      color: blue;
    }
  </style>

  <link
    rel="stylesheet"
    href="./style.css"
  />
</head>
```

Trong `style.css`:

```css
.note {
  color: red;
}
```

Nếu hai selector có cùng độ ưu tiên, quy tắc được trình duyệt đọc sau có thể thắng.

Các yếu tố cần kiểm tra:

1. Nguồn CSS.
2. Specificity.
3. Thứ tự khai báo.
4. Inline style.
5. `!important`, nếu có.

---

## 5.5. Không nên lạm dụng `!important`

```css
.note {
  color: red !important;
}
```

`!important` có thể khiến CSS khó sửa.

Nên kiểm tra trước:

- Selector có đúng không?
- File CSS có được liên kết không?
- Có quy tắc khác cụ thể hơn không?
- Quy tắc nào xuất hiện sau?
- Class trong HTML có viết đúng không?

---

## 5.6. Bảng specificity đơn giản

| Selector       | Trọng số minh họa |
| -------------- | ----------------: |
| `p`            |           `0-0-1` |
| `.message`     |           `0-1-0` |
| `p.message`    |           `0-1-1` |
| `#welcome`     |           `1-0-0` |
| `nav a.active` |           `0-1-2` |

Thứ tự so sánh:

```text
ID → Class/Attribute/Pseudo-class → Tag
```

---

## 5.7. Tính kế thừa

Một số thuộc tính của phần tử cha có thể truyền xuống phần tử con.

HTML:

```html
<section class="intro">
  <h2>Giới thiệu</h2>

  <p>Mình là Quang.</p>
</section>
```

CSS:

```css
.intro {
  color: darkblue;
  font-family: Arial, sans-serif;
}
```

`h2` và `p` có thể nhận màu và font từ `.intro`.

### Thuộc tính thường kế thừa

- `color`
- `font-family`
- `font-size` trong nhiều trường hợp
- `line-height`
- `text-align`

### Thuộc tính thường không kế thừa

- `margin`
- `padding`
- `border`
- `width`
- `height`
- `background`

---

## 5.8. Selector kết hợp

### Selector con cháu

```css
.navbar a {
  color: white;
}
```

Chọn mọi thẻ `<a>` bên trong `.navbar`.

### Con trực tiếp

```css
.nav-list > li {
  margin-right: 16px;
}
```

Chỉ chọn `<li>` là con trực tiếp của `.nav-list`.

### Nhiều class

```css
.card.featured {
  border-color: gold;
}
```

### Pseudo-class `:hover`

```css
.button:hover {
  background-color: darkred;
}
```

### [Mở rộng nhẹ] Transition

```css
.button {
  transition: background-color 0.2s ease;
}
```

Giúp sự thay đổi màu diễn ra mượt hơn.

---

## 5.9. Normal Flow

Trước khi học Position, cần hiểu normal flow.

```html
<h1>Tiêu đề</h1>
<p>Đoạn 1</p>
<p>Đoạn 2</p>
```

Theo mặc định:

- Các phần tử block xếp từ trên xuống.
- Phần tử sau nằm sau phần tử trước.
- Trình duyệt dành không gian cho từng phần tử.

Khi dùng `absolute` hoặc `fixed`, phần tử có thể rời normal flow.

---

## 5.10. `position: static`

```css
.box {
  position: static;
}
```

Đặc điểm:

- Là giá trị mặc định.
- Phần tử đi theo normal flow.
- `top`, `right`, `bottom`, `left` không tạo hiệu quả định vị như các giá trị khác.

---

## 5.11. `position: relative`

```css
.box {
  position: relative;
  top: 10px;
  left: 20px;
}
```

Đặc điểm:

- Vẫn giữ chỗ cũ trong normal flow.
- Hình ảnh hiển thị được dịch so với vị trí ban đầu.
- Thường dùng làm mốc cho phần tử con `absolute`.

---

## 5.12. `position: absolute`

```css
.parent {
  position: relative;
}

.child {
  position: absolute;
  top: 0;
  right: 0;
}
```

Đặc điểm:

- Rời normal flow.
- Không giữ chỗ cũ.
- Định vị theo phần tử tổ tiên gần nhất có `position` khác `static`.
- Nếu không có mốc phù hợp, phần tử có thể bám theo vùng chứa ban đầu của trang.

---

## 5.13. `position: fixed`

```css
.help-button {
  position: fixed;
  right: 24px;
  bottom: 24px;
}
```

Đặc điểm:

- Rời normal flow.
- Thường được định vị theo viewport.
- Khi người dùng cuộn trang, phần tử vẫn ở vị trí trên màn hình.

Ví dụ:

- Nút chat.
- Nút trở về đầu trang.
- Thanh công cụ cố định.

---

## 5.14. [Mở rộng nhẹ] `position: sticky`

```css
.site-header {
  position: sticky;
  top: 0;
}
```

Đặc điểm:

- Ban đầu gần giống `relative`.
- Khi cuộn tới ngưỡng `top: 0`, phần tử bám ở mép trên.
- Cần khai báo ít nhất một giá trị như `top`.

---

## 5.15. Ví dụ badge trên card

HTML:

```html
<article class="product-card">
  <img
    class="product-card__image"
    src="./images/product.jpg"
    alt="Bàn phím cơ màu trắng"
  />

  <span class="product-card__badge">
    Mới
  </span>

  <h2>Bàn phím cơ</h2>

  <p>Giá: 990.000đ</p>

  <a
    class="product-card__button"
    href="#"
  >
    Mua ngay
  </a>
</article>
```

CSS:

```css
.product-card {
  position: relative;

  width: 320px;
  padding: 16px;

  border: 1px solid #dddddd;
  border-radius: 16px;
}

.product-card__image {
  width: 100%;
  border-radius: 12px;
}

.product-card__badge {
  position: absolute;
  top: 28px;
  right: 28px;

  padding: 6px 10px;

  color: white;
  background-color: red;
  border-radius: 999px;
}
```

Điểm quan trọng:

```css
.product-card {
  position: relative;
}
```

Nếu thiếu dòng này, badge có thể định vị theo trang hoặc một phần tử khác.

---

## 5.16. [Mở rộng nhẹ] `z-index`

```css
.site-header {
  position: sticky;
  top: 0;
  z-index: 100;
}
```

`z-index` giúp điều chỉnh thứ tự chồng lớp.

Ghi nhớ:

- Thường có ý nghĩa với phần tử được định vị.
- Không nên dùng số quá lớn tùy tiện.
- Nếu không hoạt động, cần kiểm tra phần tử cha và stacking context.

---

## 5.17. Căn giữa bằng Position

```css
.parent {
  position: relative;
}

.child {
  position: absolute;

  top: 50%;
  left: 50%;

  transform: translate(-50%, -50%);
}
```

Giải thích:

- `top: 50%`: đưa mép trên của phần tử tới giữa cha.
- `left: 50%`: đưa mép trái tới giữa cha.
- `translate(-50%, -50%)`: kéo phần tử ngược lại theo chính kích thước của nó.

---

## 5.18. Bài thực hành Buổi 4

### Bài 1: Card sản phẩm

Yêu cầu:

- Card có ảnh.
- Có tên sản phẩm.
- Có giá.
- Có badge ở góc trên bên phải.
- Cha dùng `relative`.
- Badge dùng `absolute`.

### Bài 2: Navbar bám trên trang

Thử `fixed`:

```css
.navbar {
  position: fixed;

  top: 0;
  left: 0;

  width: 100%;
}
```

Thử `sticky`:

```css
.navbar {
  position: sticky;
  top: 0;
}
```

Quan sát:

- Fixed có che nội dung đầu trang không?
- Sticky bắt đầu bám khi nào?
- Hai cách có giữ chỗ trong bố cục giống nhau không?

### Bài 3: The Flag

1. Tạo khung cờ bằng `<div>`.
2. Đặt khung cờ `position: relative`.
3. Tạo biểu tượng bằng phần tử con.
4. Dùng `absolute`.
5. Căn biểu tượng vào giữa.

---
