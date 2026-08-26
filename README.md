# VÂN HỒ – CHẠM VÀO NÚI RỪNG

Website tĩnh chạy trên **GitHub Pages**, có trang quản trị nội dung trực tiếp qua GitHub API.

## Quản trị

Mở:

`/admin.html`

Lần đầu nhập:
- **GitHub repository:** `tai-khoan/ten-repository`
- **Nhánh:** thường là `main`
- **Fine-grained Personal Access Token:** chỉ cấp quyền **Contents: Read and write** cho đúng repository.

Token chỉ lưu trong `sessionStorage` của trình duyệt trong phiên hiện tại; không ghi vào source code.

### Có thể làm trên trang quản trị

- Thêm bài viết.
- Sửa bài viết.
- Xóa bài viết.
- Tải ảnh đại diện bài viết lên GitHub.
- Tải nhiều ảnh vào thư viện ảnh.
- Website tự đọc dữ liệu từ `content/posts.json` và `content/gallery.json`.
- Ảnh tải lên nằm tại `assets/uploads/`.

## Cấu trúc dữ liệu

```text
content/
  posts.json
  gallery.json
assets/
  uploads/
article.html
admin.html
index.html
```

## Lưu ý GitHub Pages

Đây vẫn là website tĩnh. GitHub Pages không chạy PHP/Node/backend, nên trang `admin.html` sử dụng **GitHub REST API** để ghi trực tiếp vào repository. Sau khi quản trị tạo commit, GitHub Pages sẽ tự triển khai phiên bản mới.

Không dùng Personal Access Token có quyền toàn tài khoản. Nên dùng **Fine-grained token**, giới hạn đúng repository và chỉ cấp `Contents: Read and write`.
