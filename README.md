# 📱 Video QR Hub — Hướng dẫn deploy

## Cấu trúc thư mục

```
video-qr-site/
├── index.html        ← Trang quản lý QR (chỉ bạn dùng)
├── video1.html       ← Trang video 1
├── video2.html       ← Trang video 2
├── ...
├── video7.html       ← Trang video 7
└── videos/
    ├── video1.mp4
    ├── video2.mp4
    ├── ...
    └── video7.mp4
```

---

## Bước 1 — Tạo thư mục `videos/` và bỏ file vào

Tạo thư mục `videos` bên trong `video-qr-site`, rồi đặt các file MP4 vào:
- `video1.mp4` → hiện trên `video1.html`
- `video2.mp4` → hiện trên `video2.html`
- ... tương tự đến `video7.mp4`

> ⚠️ Tên file phải khớp chính xác (chữ thường, không dấu cách)

---

## Bước 2 — Deploy lên GitHub Pages (miễn phí)

1. Tạo tài khoản GitHub tại https://github.com (nếu chưa có)
2. Tạo repo mới, đặt tên bất kỳ (ví dụ: `video-site`)
3. Upload toàn bộ thư mục `video-qr-site/` lên repo
4. Vào **Settings → Pages → Branch: main → Save**
5. GitHub sẽ cho URL dạng: `https://ten-ban.github.io/video-site`

> 💡 File MP4 nên dưới 100MB mỗi file để upload lên GitHub bình thường.  
> Nếu file lớn hơn, dùng **Google Drive** hoặc **Cloudinary** rồi thay link `src` trong thẻ `<source>`.

---

## Bước 3 — Tạo QR

1. Mở `index.html` trên browser
2. Nhập URL GitHub Pages vào ô input
3. Nhấn **Tạo QR**
4. In trang hoặc chụp màn hình QR từng video

---

## Chỉnh tiêu đề video

Mở `video1.html`, tìm dòng:
```html
<h1>Video 1</h1>
<p>Tiêu đề video — chỉnh trong file HTML</p>
```
Sửa thành tên thật của video, ví dụ:
```html
<h1>Dự án NEREID</h1>
<p>Demo UI/UX — Graduation Thesis 2025</p>
```

---

## Thay thế video bằng link Google Drive (nếu file lớn)

Thay thẻ `<video>` bằng:
```html
<iframe 
  src="https://drive.google.com/file/d/FILE_ID/preview"
  width="100%" 
  height="480" 
  allow="autoplay"
  style="border:none; display:block;"
></iframe>
```
Lấy `FILE_ID` từ link share Google Drive của bạn.
