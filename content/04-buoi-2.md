# 3. Buổi 2 – HTML bậc trung và website nhiều trang

## 3.1. Semantic HTML

Semantic HTML là cách chọn thẻ dựa trên ý nghĩa của nội dung.

Ví dụ:

```html
<header>
  <h1>Portfolio của Quang</h1>
</header>

<nav>
  <a href="./index.html">Trang chủ</a>
  <a href="./about.html">Giới thiệu</a>
  <a href="./projects.html">Dự án</a>
</nav>

<main>
  <section>
    <h2>Giới thiệu</h2>

    <p>Mình là học viên JSB.</p>
  </section>
</main>

<footer>
  <p>© 2026 Quang</p>
</footer>
```

### Các thẻ chính

| Thẻ         | Công dụng                          |
| ----------- | ---------------------------------- |
| `<header>`  | Phần mở đầu của trang hoặc khu vực |
| `<nav>`     | Chứa các liên kết điều hướng       |
| `<main>`    | Chứa nội dung chính                |
| `<section>` | Một khu vực có chủ đề              |
| `<article>` | Nội dung tương đối độc lập         |
| `<footer>`  | Phần kết thúc                      |

### Lợi ích

- Code dễ đọc hơn.
- Cấu trúc rõ ràng hơn.
- Hỗ trợ công cụ tìm kiếm hiểu nội dung.
- Hỗ trợ công cụ trợ năng.

---

## 3.2. Khi nào dùng `<div>`?

`<div>` là vùng chứa chung, không mang ý nghĩa nội dung cụ thể.

Dùng `<div>` khi:

- Cần nhóm phần tử để trang trí.
- Cần tạo container cho Flexbox.
- Không có thẻ semantic phù hợp.

Ví dụ:

```html
<section>
  <h2>Dự án</h2>

  <div class="project-list">
    <article>Dự án 1</article>
    <article>Dự án 2</article>
  </div>
</section>
```

Trong ví dụ:

- `<section>` mô tả ý nghĩa nội dung.
- `<div class="project-list">` phục vụ bố cục.

---

## 3.3. Danh sách không có thứ tự

```html
<h2>Kỹ năng</h2>

<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>Flexbox</li>
</ul>
```

Dùng `<ul>` khi thứ tự không quan trọng.

Ví dụ:

- Danh sách kỹ năng.
- Danh sách sở thích.
- Danh sách liên kết điều hướng.

---

## 3.4. Danh sách có thứ tự

```html
<h2>Quy trình làm bài</h2>

<ol>
  <li>Tạo thư mục dự án</li>
  <li>Tạo file HTML</li>
  <li>Viết nội dung</li>
  <li>Chạy bằng Live Server</li>
</ol>
```

Dùng `<ol>` khi thứ tự có ý nghĩa.

---

## 3.5. Danh sách lồng nhau

```html
<ul>
  <li>
    Lập trình web

    <ul>
      <li>HTML</li>
      <li>CSS</li>
    </ul>
  </li>

  <li>
    Thể thao

    <ul>
      <li>Bóng đá</li>
      <li>Cầu lông</li>
    </ul>
  </li>
</ul>
```

Danh sách con nên nằm bên trong một `<li>`.

Không nên:

```html
<ul>
  <li>Lập trình web</li>

  <ul>
    <li>HTML</li>
  </ul>
</ul>
```

Nên:

```html
<ul>
  <li>
    Lập trình web

    <ul>
      <li>HTML</li>
    </ul>
  </li>
</ul>
```

---

## 3.6. Thẻ liên kết `<a>`

### Liên kết đến website khác

```html
<a href="https://example.com">
  Mở website tham khảo
</a>
```

### Liên kết đến trang trong cùng dự án

```html
<a href="./about.html">
  Trang giới thiệu
</a>
```

### Liên kết đến một khu vực trên cùng trang

```html
<a href="#projects">
  Xem dự án
</a>

<section id="projects">
  <h2>Dự án</h2>
</section>
```

Giá trị:

```text
#projects
```

sẽ tìm phần tử có:

```html
id="projects"
```

### Mở trang ngoài trong tab mới

```html
<a
  href="https://example.com"
  target="_blank"
  rel="noopener noreferrer"
>
  Mở trang tham khảo
</a>
```

- `target="_blank"`: mở tab mới.
- `rel="noopener noreferrer"`: mở rộng nhẹ nhằm tăng an toàn khi mở trang ngoài.

### Thẻ `<a>` thiếu `href`

```html
<a>Trang giới thiệu</a>
```

Thẻ có nội dung nhưng chưa có địa chỉ điều hướng.

---

## 3.7. Đường dẫn tương đối

Giả sử cấu trúc:

```text
portfolio/
├── index.html
├── about.html
├── pages/
│   └── contact.html
└── images/
    └── avatar.jpg
```

### Từ `index.html`

```html
<a href="./about.html">
  Giới thiệu
</a>

<a href="./pages/contact.html">
  Liên hệ
</a>

<img
  src="./images/avatar.jpg"
  alt="Ảnh đại diện của Quang"
/>
```

### Từ `pages/contact.html` về trang chủ

```html
<a href="../index.html">
  Trang chủ
</a>
```

### Ký hiệu

| Ký hiệu | Ý nghĩa                                         |
| ------- | ----------------------------------------------- |
| `./`    | Thư mục hiện tại                                |
| `../`   | Đi lên một thư mục                              |
| `/`     | Đường dẫn từ gốc website trong nhiều trường hợp |

---

## 3.8. Thẻ hình ảnh `<img>`

```html
<img
  src="./images/avatar.jpg"
  alt="Ảnh chân dung của Quang"
/>
```

### Thuộc tính quan trọng

| Thuộc tính | Công dụng                        |
| ---------- | -------------------------------- |
| `src`      | Đường dẫn tới ảnh                |
| `alt`      | Nội dung thay thế hoặc mô tả ảnh |
| `width`    | Chiều rộng ảnh                   |
| `height`   | Chiều cao ảnh                    |

### Viết `alt` tốt

Không nên:

```html
<img
  src="./images/avatar.jpg"
  alt="ảnh"
/>
```

Tốt hơn:

```html
<img
  src="./images/avatar.jpg"
  alt="Ảnh chân dung của Quang"
/>
```

Nếu ảnh chỉ dùng để trang trí:

```html
<img
  src="./images/decorative-wave.svg"
  alt=""
/>
```

---

## 3.9. Thẻ lồng nhau và thụt lề

Khó đọc:

```html
<section><h2>Dự án</h2><div><h3>Portfolio</h3><p>Website cá nhân</p></div></section>
```

Dễ đọc:

```html
<section>
  <h2>Dự án</h2>

  <div>
    <h3>Portfolio</h3>

    <p>Website cá nhân</p>
  </div>
</section>
```

### Quy tắc đóng thẻ

Thẻ mở sau nên được đóng trước.

Đúng:

```html
<section>
  <div>
    <p>Nội dung</p>
  </div>
</section>
```

Sai:

```html
<section>
  <div>
    <p>Nội dung</div>
  </p>
</section>
```

---

## 3.10. Website nhiều trang

Cấu trúc:

```text
portfolio/
├── index.html
├── about.html
├── projects.html
└── css/
    └── style.css
```

Navigation dùng trong cả ba trang:

```html
<nav>
  <a href="./index.html">
    Trang chủ
  </a>

  <a href="./about.html">
    Giới thiệu
  </a>

  <a href="./projects.html">
    Dự án
  </a>
</nav>
```

### [Mở rộng nhẹ] Đánh dấu trang hiện tại

Trong `about.html`:

```html
<a
  href="./about.html"
  aria-current="page"
>
  Giới thiệu
</a>
```

CSS:

```css
a[aria-current="page"] {
  color: darkorange;
  font-weight: bold;
}
```

---

## 3.11. Bài thực hành Buổi 2

Xây dựng Portfolio gồm ba trang.

### Trang chủ

- Họ tên.
- Ảnh đại diện.
- Giới thiệu ngắn.
- Liên kết đến trang dự án.

### Trang giới thiệu

- Trường đang học.
- Sở thích.
- Mục tiêu.
- Danh sách kỹ năng.

### Trang dự án

- Tên dự án.
- Ảnh dự án.
- Mô tả.
- Liên kết xem chi tiết.

### Thử thách

1. Tạo menu xuất hiện ở cả ba trang.
2. Từ trang nào cũng quay về trang chủ được.
3. Tạo danh sách sở thích có danh sách con.
4. Lưu ảnh trong thư mục `images`.
5. Không dùng đường dẫn ảnh trực tiếp từ ổ đĩa máy tính.

---
