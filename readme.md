# Portfolio CV - Nguyễn Văn An

Website portfolio cá nhân giới thiệu Nguyễn Văn An, Frontend Developer. Trang trình bày thông tin cá nhân, kỹ năng, các dự án tiêu biểu và kênh liên hệ trong một giao diện responsive.

## Chức năng

- Giới thiệu bản thân và định hướng nghề nghiệp.
- Trình bày kỹ năng và công nghệ sử dụng.
- Hiển thị các dự án tiêu biểu cùng mô tả và nhãn công nghệ.
- Cung cấp thông tin liên hệ qua email, GitHub và LinkedIn.
- Điều hướng đến từng phần bằng menu; hỗ trợ bố cục trên điện thoại, máy tính bảng và máy tính.

## Công nghệ

- HTML5: cấu trúc ngữ nghĩa và nội dung trang.
- CSS3: giao diện, Flexbox, CSS Grid và thiết kế responsive theo hướng mobile-first.
- Không sử dụng framework, thư viện JavaScript, trình quản lý gói hoặc quy trình build.
- Docker tùy chọn: Nginx Alpine phục vụ các tệp tĩnh.

## Yêu cầu môi trường

Để xem trang, chỉ cần một trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari. Không bắt buộc cài Node.js hay công cụ build.

Các lựa chọn bổ sung:

- Python 3 nếu muốn chạy máy chủ HTTP cục bộ.
- Docker Desktop trên Windows/macOS hoặc Docker Engine trên Linux nếu muốn chạy bằng Docker.
- Git nếu muốn clone mã nguồn từ kho lưu trữ.

## Cấu trúc dự án

```text
CV--main/
├── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   └── img/
│       └── avatar.jpg
└── BAOCAO-A2.1.docx
```

## Cài đặt

Nếu đã có mã nguồn trong máy, không cần cài đặt thêm thư viện. Nếu lấy dự án từ Git, thay URL bên dưới bằng URL kho lưu trữ thực tế:

```bash
git clone <URL-kho-luu-tru>
cd CV--main
```

## Cấu hình và tùy chỉnh

Đây là website tĩnh nên hiện không có tệp cấu hình môi trường, biến `.env` hay thông tin bí mật cần thiết.

- Chỉnh nội dung, tiêu đề trang, mô tả SEO và thông tin liên hệ trong `index.html`.
- Thay ảnh đại diện tại `assets/img/avatar.jpg` hoặc sửa đường dẫn ảnh tương ứng trong `index.html`.
- Cập nhật màu sắc, kiểu chữ và bố cục trong `assets/css/styles.css` (các biến giao diện nằm ở phần `:root`).
- Các liên kết GitHub/LinkedIn trong trang hiện là liên kết mẫu; hãy thay bằng địa chỉ hồ sơ thật trước khi công bố. Email trong trang là `an.nguyen@example.com`, cần cập nhật nếu không phải địa chỉ muốn sử dụng.

## Chạy thử

Các lệnh dưới đây giả định thư mục làm việc ban đầu là thư mục chứa `readme.md`; thư mục website nằm trong `CV--main/`.

### Windows

Mở trực tiếp bằng trình duyệt mặc định từ PowerShell:

```powershell
Start-Process .\CV--main\index.html
```

Hoặc chạy máy chủ HTTP bằng Python 3:

```powershell
cd .\CV--main
py -m http.server 8000
```

Mở `http://localhost:8000` trong trình duyệt. Nếu lệnh `py` không có trên máy, thử `python -m http.server 8000`. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở trực tiếp:

```bash
open CV--main/index.html
```

Hoặc chạy máy chủ HTTP:

```bash
cd CV--main
python3 -m http.server 8000
```

Mở `http://localhost:8000` trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở trực tiếp bằng trình duyệt mặc định:

```bash
xdg-open CV--main/index.html
```

Hoặc chạy máy chủ HTTP:

```bash
cd CV--main
python3 -m http.server 8000
```

Mở `http://localhost:8000` trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Docker

Cần Docker đang hoạt động. Không cần tạo image riêng: container Nginx sẽ phục vụ thư mục website được mount ở chế độ chỉ đọc.

Trên macOS/Linux, chạy từ thư mục chứa `readme.md`:

```bash
docker run --rm -d --name cv-portfolio -p 8080:80 -v "$(pwd)/CV--main:/usr/share/nginx/html:ro" nginx:alpine
```

Trên Windows PowerShell, chạy từ thư mục chứa `readme.md`:

```powershell
docker run --rm -d --name cv-portfolio -p 8080:80 -v "${PWD}/CV--main:/usr/share/nginx/html:ro" nginx:alpine
```

Truy cập `http://localhost:8080`. Dừng và xóa container bằng:

```bash
docker stop cv-portfolio
```

Nếu cổng `8080` đã được sử dụng, đổi phần `-p 8080:80` thành một cổng trống khác, ví dụ `-p 8081:80`, rồi truy cập cổng tương ứng. Lần chạy đầu tiên Docker có thể cần tải image `nginx:alpine`.

## Thông tin liên hệ

Thông tin liên hệ được hiển thị trong phần **Liên hệ** của trang:

- Email: [an.nguyen@example.com](mailto:an.nguyen@example.com)
- GitHub: `github.com/nguyenvanan` (liên kết trong trang cần được thay bằng URL hồ sơ thực tế).
- LinkedIn: `linkedin.com/in/nguyenvanan` (liên kết trong trang cần được thay bằng URL hồ sơ thực tế).

Hãy cập nhật các thông tin mẫu trong `index.html` trước khi sử dụng website như portfolio chính thức.
