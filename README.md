# EduHub Web — Ch02 (starter)

Bài thực hành chương 2 môn **IN4529 — Lập trình Front End**: tạo kiểu cho 4 trang EduHub Web của Ch01 bằng **CSS thuần hiện đại**, chạy đẹp trên điện thoại, máy tính bảng, máy tính, có cả dark mode.

HTML đã xong (nội dung Ch01 + class + `<link rel="stylesheet" href="css/main.css">`). Em **chỉ viết CSS** trong thư mục `css/`, theo các dòng `/* TODO(ch2-Tk) */`.

## Chạy

- Mở thư mục bằng VS Code → chuột phải `index.html` → **Open with Live Server** (tự tải lại khi lưu CSS).
- Hoặc: `npx -y http-server . -p 8080` rồi mở <http://localhost:8080>.

Lúc đầu trang trông như Ch01 (chưa có CSS) — đó là bình thường.

## Thứ tự làm gợi ý

1. `ch2-T2` trong `main.css` (khai báo `@layer` + `@import`) — làm trước để các tệp khác được nạp.
2. `ch2-T1` trong `tokens.css` → `ch2-T2` trong `base.css`.
3. `ch2-T3` → `ch2-T4` → `ch2-T5` → `ch2-T6` trong `layout.css` và `components.css`.
4. (Challenge) `ch2-T7`: tạo thư mục `challenge-tailwind/`, viết lại `events.html` bằng Tailwind CSS v4 (xem đề bài).

Tìm nhanh mọi việc cần làm: VS Code → Ctrl+Shift+F → `TODO(ch2-`.

## Kiểm tra

```bash
npx -y html-validate@latest "*.html"     # kỳ vọng: không in lỗi (đừng sửa làm hỏng HTML)
```

- DevTools → Toggle device toolbar → thử 375 / 768 / 1280 px. Trong Console gõ
  `document.documentElement.scrollWidth <= innerWidth` → phải ra `true` (không cuộn ngang).
- Dark mode: DevTools → ⋮ → More tools → **Rendering** → *prefers-color-scheme* → `dark`.
- Giảm chuyển động: cũng ở Rendering → *prefers-reduced-motion* → `reduce`.

## Class có sẵn trong HTML

| Trang | Class |
|---|---|
| Mọi trang | `skip-link`, `site-header`, `site-header__inner`, `container`, `brand`, `brand__logo`, `brand__name`, `site-nav`, `site-nav__list`, `site-nav__link` (trang hiện tại có `aria-current="page"`), `site-footer`, `site-footer__inner`, `page`, `page__intro`, `section`, `section__head`, `btn`, `btn--primary`, `btn--accent`, `btn--ghost`, `btn-row`, `cta` |
| `index.html` | `hero`, `hero__eyebrow`, `hero__lead`, `hero__media`, `card-grid`, `club-card`, `faq`, `faq__item` |
| Card sự kiện (`index.html`, `events.html`) | `card`, `event-card`, `card__media`, `card__body`, `card__meta`, `tag`, `badge`, `badge--hot`, `card__title`, `event-card__info`, `card__text`, `event-card__seats` |
| `events.html` | `table-wrap`, `table` |
| `event-detail.html` | `detail`, `detail__head`, `back-link`, `detail__organizer`, `detail__media`, `detail__info`, `info-card`, `detail__content`, `detail__prep`, `prose`, `detail__foot` |
| `register.html` | `page--narrow`, `form`, `form__grid`, `field`, `field--full`, `field--check`, `choice-group`, `choice-group__options`, `choice` |

## Cấu trúc

```
starter/
├── index.html, events.html, event-detail.html, register.html   # đã có class, không cần sửa
├── css/
│   ├── main.css         # ch2-T2: @layer + @import
│   ├── tokens.css       # ch2-T1: design token + dark mode
│   ├── base.css         # ch2-T2: reset, thẻ HTML trần, focus, reduced motion
│   ├── layout.css       # ch2-T3, T4, T5: container, header, footer, hero, lưới
│   └── components.css   # ch2-T3…T6: nút, card, badge, FAQ, bảng, form
├── assets/              # Ảnh SVG
└── README.md
```

## Nộp bài

Chép thư mục `starter/` thành repo mới **`EduHubWeb-Ch02-<MSSV>`** (public), commit ≥ 3 lần với message rõ nghĩa, bật GitHub Pages và ghi link vào README.
