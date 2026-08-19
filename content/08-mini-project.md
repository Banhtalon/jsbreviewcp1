# 7. Mini-project tổng hợp

## 7.1. Yêu cầu dự án

Xây dựng Portfolio Responsive có:

- Header.
- Navbar.
- Hero giới thiệu.
- Ảnh đại diện.
- Danh sách kỹ năng.
- Danh sách dự án.
- Card có badge dùng Position.
- Footer.
- Responsive cho màn hình nhỏ.

## 7.2. Cấu trúc thư mục

```text
portfolio-quang/
├── index.html
├── about.html
├── projects.html
├── css/
│   └── style.css
└── images/
    ├── avatar.jpg
    ├── portfolio.jpg
    ├── product-page.jpg
    └── flag.jpg
```

---

## 7.3. File `index.html`

```html
<!DOCTYPE html>
<html lang="vi">
  <head>
    <meta charset="UTF-8" />

    <meta
      name="viewport"
      content="width=device-width, initial-scale=1.0"
    />

    <title>Portfolio | Quang</title>

    <link
      rel="stylesheet"
      href="./css/style.css"
    />
  </head>

  <body>
    <header class="site-header">
      <div class="container navbar">
        <a
          class="logo"
          href="./index.html"
        >
          Quang.dev
        </a>

        <nav aria-label="Điều hướng chính">
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

            <li>
              <a href="./about.html">
                Trang cá nhân
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </header>

    <main>
      <section
        class="container hero"
        id="about"
      >
        <div class="hero__content">
          <p class="eyebrow">
            HỌC VIÊN JSB
          </p>

          <h1>
            Xin chào, mình là Quang
          </h1>

          <p class="hero__description">
            Mình đang học cách xây dựng website bằng
            HTML và CSS. Mục tiêu của mình là tạo được
            một portfolio đẹp, rõ ràng và responsive.
          </p>

          <a
            class="button"
            href="#projects"
          >
            Xem dự án
          </a>
        </div>

        <img
          class="hero__image"
          src="./images/avatar.jpg"
          alt="Ảnh đại diện của Quang"
          width="320"
          height="320"
        />
      </section>

      <section
        class="skills-section"
        id="skills"
      >
        <div class="container">
          <h2>Kỹ năng đang học</h2>

          <ul class="skill-list">
            <li>HTML5</li>
            <li>Semantic HTML</li>
            <li>CSS Selectors</li>
            <li>Box Model</li>
            <li>Position</li>
            <li>Flexbox</li>
            <li>Responsive</li>
          </ul>
        </div>
      </section>

      <section
        class="container section"
        id="projects"
      >
        <div class="section-heading">
          <p class="eyebrow">
            SẢN PHẨM
          </p>

          <h2>Dự án của mình</h2>
        </div>

        <div class="project-list">
          <article class="project-card">
            <span class="project-card__badge">
              Nổi bật
            </span>

            <img
              class="project-card__image"
              src="./images/portfolio.jpg"
              alt="Giao diện dự án Portfolio cá nhân"
            />

            <div class="project-card__content">
              <h3>Portfolio Website</h3>

              <p>
                Website nhiều trang giới thiệu thông tin,
                kỹ năng và dự án cá nhân.
              </p>

              <a href="./projects.html">
                Xem chi tiết
              </a>
            </div>
          </article>

          <article class="project-card">
            <img
              class="project-card__image"
              src="./images/product-page.jpg"
              alt="Giao diện trang sản phẩm"
            />

            <div class="project-card__content">
              <h3>Product Page</h3>

              <p>
                Trang sản phẩm sử dụng Box Model,
                Flexbox và Responsive.
              </p>

              <a href="./projects.html">
                Xem chi tiết
              </a>
            </div>
          </article>

          <article class="project-card">
            <img
              class="project-card__image"
              src="./images/flag.jpg"
              alt="Sản phẩm The Flag làm bằng HTML và CSS"
            />

            <div class="project-card__content">
              <h3>The Flag</h3>

              <p>
                Bài thực hành CSS Position với
                relative và absolute.
              </p>

              <a href="./projects.html">
                Xem chi tiết
              </a>
            </div>
          </article>
        </div>
      </section>
    </main>

    <footer class="site-footer">
      <div class="container">
        <p>
          © 2026 Quang. Sản phẩm ôn tập JSB.
        </p>
      </div>
    </footer>
  </body>
</html>
```

---

## 7.4. File `css/style.css`

```css
:root {
  --primary: #f97316;
  --primary-dark: #c2410c;
  --text: #1f2937;
  --muted: #6b7280;
  --surface: #ffffff;
  --surface-soft: #fff7ed;
  --border: #e5e7eb;
}

*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;

  color: var(--text);
  background-color: #f8fafc;

  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.6;
}

img {
  display: block;
  max-width: 100%;
}

a {
  color: var(--primary-dark);
}

a:hover {
  color: var(--primary);
}

.container {
  width: calc(100% - 32px);
  max-width: 1100px;
  margin: 0 auto;
}

/* HEADER */

.site-header {
  position: sticky;
  top: 0;
  z-index: 10;

  background-color: rgb(255 255 255 / 95%);
  border-bottom: 1px solid var(--border);
}

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;

  min-height: 68px;
}

.logo {
  color: var(--primary-dark);

  font-size: 1.4rem;
  font-weight: 700;
  text-decoration: none;
}

.nav-list {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  gap: 20px;

  margin: 0;
  padding: 0;

  list-style: none;
}

.nav-list a {
  color: var(--text);
  font-weight: 600;
  text-decoration: none;
}

.nav-list a:hover {
  color: var(--primary);
}

/* HERO */

.hero {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 48px;

  min-height: 560px;
  padding-top: 64px;
  padding-bottom: 64px;
}

.hero__content {
  flex: 1 1 420px;
}

.hero h1 {
  max-width: 700px;

  margin-top: 8px;
  margin-bottom: 16px;

  font-size: 3rem;
  line-height: 1.15;
}

.hero__description {
  max-width: 620px;

  color: var(--muted);
  font-size: 1.1rem;
}

.hero__image {
  flex: 0 1 320px;

  width: 320px;
  height: 320px;

  object-fit: cover;

  border: 8px solid white;
  border-radius: 50%;

  box-shadow: 0 20px 50px rgb(0 0 0 / 15%);
}

.eyebrow {
  margin: 0;

  color: var(--primary-dark);

  font-size: 0.85rem;
  font-weight: 700;
  letter-spacing: 0.12em;
}

.button {
  display: inline-block;

  margin-top: 16px;
  padding: 12px 20px;

  color: white;
  background-color: var(--primary);
  border-radius: 10px;

  font-weight: 700;
  text-decoration: none;

  transition:
    background-color 0.2s ease,
    transform 0.2s ease;
}

.button:hover {
  color: white;
  background-color: var(--primary-dark);

  transform: translateY(-2px);
}

/* SKILLS */

.skills-section {
  padding: 56px 0;

  background-color: var(--surface-soft);
}

.skill-list {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;

  margin-top: 24px;
  margin-bottom: 0;
  padding: 0;

  list-style: none;
}

.skill-list li {
  padding: 10px 16px;

  background-color: white;
  border: 1px solid #fed7aa;
  border-radius: 999px;
}

/* PROJECTS */

.section {
  padding-top: 72px;
  padding-bottom: 72px;
}

.section-heading {
  margin-bottom: 32px;
}

.section-heading h2 {
  margin-top: 8px;
  margin-bottom: 0;

  font-size: 2rem;
}

.project-list {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
}

.project-card {
  position: relative;
  flex: 1 1 280px;

  overflow: hidden;

  background-color: var(--surface);
  border: 1px solid var(--border);
  border-radius: 18px;

  box-shadow: 0 10px 30px rgb(0 0 0 / 8%);
}

.project-card__image {
  width: 100%;
  height: 190px;

  object-fit: cover;
}

.project-card__content {
  padding: 24px;
}

.project-card__content h3 {
  margin-top: 0;
  margin-bottom: 8px;
}

.project-card__content p {
  color: var(--muted);
}

.project-card__badge {
  position: absolute;
  top: 16px;
  right: 16px;

  padding: 6px 10px;

  color: white;
  background-color: var(--primary);
  border-radius: 999px;

  font-size: 0.8rem;
  font-weight: 700;
}

/* FOOTER */

.site-footer {
  padding: 24px 0;

  color: white;
  background-color: #111827;

  text-align: center;
}

/* RESPONSIVE */

@media screen and (max-width: 720px) {
  .navbar {
    flex-direction: column;
    justify-content: center;

    padding-top: 16px;
    padding-bottom: 16px;
  }

  .nav-list {
    justify-content: center;
  }

  .hero {
    flex-direction: column;

    min-height: auto;

    text-align: center;
  }

  .hero__content {
    flex-basis: auto;
  }

  .hero h1 {
    font-size: 2.25rem;
  }

  .hero__description {
    margin-right: auto;
    margin-left: auto;
  }

  .hero__image {
    order: -1;

    width: 240px;
    height: 240px;
  }

  .skill-list {
    justify-content: center;
  }
}
```

---

## 7.5. Kiến thức được sử dụng

| Phần dự án                     | Kiến thức      |
| ------------------------------ | -------------- |
| Bộ khung HTML                  | Buổi 1         |
| Thẻ semantic                   | Buổi 2         |
| Danh sách, ảnh và link         | Buổi 2         |
| External CSS                   | Buổi 3         |
| Class selector                 | Buổi 3         |
| Box Model                      | Buổi 3         |
| Relative và Absolute           | Buổi 4         |
| Sticky và z-index              | Mở rộng Buổi 4 |
| Inline-block                   | Buổi 5         |
| Flexbox                        | Buổi 5         |
| Flex-wrap                      | Buổi 5         |
| Media Query                    | Buổi 5         |
| CSS Variables, gap, transition | Mở rộng nhẹ    |

---

## 7.6. Cách luyện với mini-project

### Lần 1: Chạy đúng

- Tạo đúng file.
- Thêm ảnh.
- Chạy Live Server.
- Kiểm tra đường dẫn.

### Lần 2: Thay nội dung

- Đổi họ tên.
- Đổi đoạn giới thiệu.
- Đổi kỹ năng.
- Đổi danh sách dự án.

### Lần 3: Thay giao diện

- Đổi màu chủ đạo.
- Đổi bo góc.
- Đổi khoảng cách.
- Đổi kích thước ảnh.

### Lần 4: Tự viết lại

Không nhìn code cũ, tự làm:

1. Container.
2. Navbar.
3. Hero.
4. Card.
5. Badge.
6. Responsive.

---
