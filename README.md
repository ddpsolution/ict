# ict — ICT App Builds (GitHub Pages)

Nhánh `gh-pages` phục vụ trang quản lý & tải bản build các app của partner **ICT**.
URL: https://ddpsolution.github.io/ict/

## Cách hoạt động
- `index.html` đọc **`apps.json`** (do AFC quản lý) → mỗi app một thẻ: **Tải APK** (file trong `builds/<code>/`) + **Xem artifact**.
- **KHÔNG dùng GitHub Releases** → không có "Source code (zip/tar.gz)".
- APK host thẳng trên Pages tại `builds/<code>/<ten>.apk` (chỉ giữ **version mới nhất** mỗi app).

## apps.json (AFC quản lý)
```json
{ "brand": {"name":"ICT"},
  "apps": [
    { "code":"05j", "name":"Live TV: M3U Player", "package":"com.m3uplay.livetv.player",
      "order":5, "artifact":"https://claude.ai/artifact/…", "apk":"builds/05j/….apk", "size":58093390 }
  ] }
```
- `apk: null` → thẻ hiện "APK sắp có". `hidden: true` → ẩn app. `order` nhỏ lên trước. `icon` optional.
- Thêm/đổi build: thay file trong `builds/<code>/` + cập nhật `apk`/`size` trong `apps.json` (giữ 1 file mới nhất).

> `main` chỉ chứa README (không source app).
