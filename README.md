# ict — trang tải Preview Builds (GitHub Pages)

Nhánh `gh-pages` phục vụ trang tải APK dùng chung cho nhiều app, **quản lý bởi AFC**.
URL: https://ddpsolution.github.io/ict/

## Cách hoạt động
- `index.html` đọc **GitHub Releases API** của repo này rồi render mỗi app một thẻ + nút **Tải APK**
  (trỏ thẳng `browser_download_url` của asset `.apk` → KHÔNG hiện "Source code").
- **Thêm app = publish một GitHub Release có file `.apk`** (cơ chế sẵn có của AFC/`release`). App tự xuất hiện.

## AFC tùy biến bằng `apps.json` (tùy chọn)
Key = `app_code` (3 ký tự, vd `05j`). Mọi trường đều optional:
```json
{ "apps": {
  "05j": { "name": "Live TV: M3U Player", "icon": "https://…/icon.png", "notes": "Ghi chú ngắn", "order": 1, "hidden": false }
}}
```
- `name` đè tên tự suy; `icon` URL ảnh; `notes` mô tả ngắn; `order` số nhỏ lên trước; `hidden: true` để ẩn app khỏi trang.
- Không khai thì trang tự suy tên/mã từ tiêu đề + tag release, sắp theo ngày publish mới nhất.

## Lưu ý
- `main` chỉ chứa README (không source app). APK nằm ở Releases. Trang chỉ liệt kê `.apk`.
