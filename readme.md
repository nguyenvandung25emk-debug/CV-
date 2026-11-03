# Portfolio CV - Nguyễn Văn dung

Website tĩnh giới thiệu các điểm đến và trải nghiệm du lịch tại Việt Nam. Trang có nội dung tiếng Việt, bố cục responsive và điều hướng đến các phần giới thiệu, điểm đến, gợi ý trải nghiệm và liên hệ.

## Chức năng

- Giới thiệu chủ đề khám phá cảnh quan, văn hóa và ẩm thực Việt Nam.
- Điều hướng nhanh giữa các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Giới thiệu các điểm đến như Hà Nội, Vịnh Hạ Long, Sa Pa, Đà Nẵng, Hội An và Thành phố Hồ Chí Minh.
- Hiển thị các thẻ gợi ý trải nghiệm tại Vịnh Hạ Long, Hội An, Đà Nẵng và miền Tây.
- Tự điều chỉnh bố cục theo kích thước màn hình điện thoại, máy tính bảng và máy tính.

## Công nghệ

- **HTML5:** cấu trúc và nội dung trang.
- **CSS3:** giao diện, Flexbox, CSS Grid, breakpoint responsive và hiệu ứng trình bày.
- **Nginx Alpine (tùy chọn):** phục vụ các tệp tĩnh khi chạy bằng Docker.

Trang không dùng JavaScript, framework, backend, cơ sở dữ liệu hoặc quy trình build.

## Yêu cầu môi trường

Để mở trang trực tiếp, cần một trình duyệt hiện đại như Chrome, Edge, Firefox hoặc Safari. Không cần cài thêm thư viện hay Node.js.

Các công cụ sau chỉ cần cho cách chạy tương ứng:

- **Python 3:** chạy máy chủ HTTP cục bộ.
- **Docker Desktop** (Windows/macOS) hoặc **Docker Engine** (Linux): chạy bằng Docker.
- **Git:** chỉ cần nếu lấy mã nguồn bằng Git.

## Cài đặt

Nếu đã tải mã nguồn về máy, mở terminal tại thư mục `KT A2.1`. Không cần cài dependency.

Nếu mã nguồn được lấy từ Git, thay `<URL-kho-luu-tru>` bằng URL thực tế:

```bash
git clone <URL-kho-luu-tru>
cd "CV--main/KT A2.1"
```

Sau khi giải nén hoặc clone, thư mục chạy trang cần có cấu trúc như sau:

```text
KT A2.1/
├── index.html
├── assets/
│   └── css/
│       └── styles.css
├── images.jpg
├── avatar1.jpg
├── avatar2.jpg
├── avatar3.jpg
└── avarta4.jpg
```

## Cấu hình và tùy chỉnh

Website hiện không có tệp cấu hình, biến môi trường hay thông tin bí mật.

- Sửa nội dung, tiêu đề, mô tả và thông tin liên hệ trong `index.html`.
- Thay ảnh hoặc cập nhật đường dẫn ảnh trong `index.html`; giữ các tệp ảnh trong đúng vị trí tương đối để ảnh hiển thị.
- Chỉnh màu sắc, bố cục, kiểu chữ và breakpoint trong `assets/css/styles.css`.
- Email đang hiển thị là `dung.nguyen@example.com`. Liên kết GitHub, LinkedIn và các nút “Xem chi tiết” hiện là liên kết mẫu (`#`); hãy thay bằng thông tin và địa chỉ thực tế trước khi công bố.

## Chạy thử

Các lệnh dưới đây giả định terminal đang mở tại thư mục `KT A2.1` (thư mục chứa `index.html`).

### Windows

Mở trang trực tiếp bằng trình duyệt mặc định trong PowerShell:

```powershell
Start-Process .\index.html
```

Hoặc chạy máy chủ HTTP bằng Python 3:

```powershell
py -m http.server 8000
```

Nếu không có lệnh `py`, thử:

```powershell
python -m http.server 8000
```

Mở `http://localhost:8000` trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở trang trực tiếp:

```bash
open index.html
```

Hoặc chạy máy chủ HTTP:

```bash
python3 -m http.server 8000
```

Mở `http://localhost:8000` trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở trang trực tiếp bằng trình duyệt mặc định:

```bash
xdg-open index.html
```

Hoặc chạy máy chủ HTTP:

```bash
python3 -m http.server 8000
```

Mở `http://localhost:8000` trong trình duyệt. Dừng máy chủ bằng `Ctrl+C`.

### Docker

Cần Docker đang hoạt động. Chạy các lệnh tại thư mục `KT A2.1`. Không cần Dockerfile; container Nginx sẽ phục vụ thư mục hiện tại ở chế độ chỉ đọc.

**Windows PowerShell:**

```powershell
docker run --rm -d --name vietnam-travel-site -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

**macOS/Linux:**

```bash
docker run --rm -d --name vietnam-travel-site -p 8080:80 -v "$(pwd):/usr/share/nginx/html:ro" nginx:alpine
```

Truy cập `http://localhost:8080`. Dừng container bằng:

```bash
docker stop vietnam-travel-site
```

Nếu cổng `8080` đang được sử dụng, đổi `-p 8080:80` thành cổng trống khác, chẳng hạn `-p 8081:80`, rồi truy cập cổng đó. Lần đầu chạy, Docker có thể cần tải image `nginx:alpine`.

## Thông tin liên hệ

Thông tin liên hệ hiện có trong trang:

- **Email:** [dung.nguyen@example.com](mailto:dung.nguyen@example.com) (địa chỉ mẫu).
- **GitHub:** `github.com/nguyenvandung` (liên kết chưa được cấu hình).
- **LinkedIn:** `linkedin.com/in/nguyenvandung` (liên kết chưa được cấu hình).

Đây là thông tin được lấy từ nội dung hiện tại của trang; vui lòng cập nhật trong `index.html` nếu muốn sử dụng cho liên hệ thực tế.ử dụng website như portfolio chính thức.
