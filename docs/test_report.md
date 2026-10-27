# BÁO CÁO KIỂM THỬ

- **Ngày kiểm thử:** 2026-10-27
- **Phạm vi:** Website tĩnh trong `index.html`, `assets/css/styles.css` và các tài nguyên ảnh.
- **Phương pháp:** Kiểm tra thủ công trên trình duyệt tích hợp, mở trang bằng `file://`; kiểm tra giao diện ở các chiều rộng 390 px, 768 px, 1280 px và 1348 px.
- **Tổng kết:** Đạt một phần. Trang hiển thị và điều hướng nội bộ hoạt động, nhưng còn lỗi cắt nội dung ở màn hình hẹp và các liên kết placeholder cần hoàn thiện.

## 1. Tính đúng đắn

**Kết quả: Đạt một phần.** Tiêu đề trang, bốn khu vực Giới thiệu, Kỹ năng, Dự án, Liên hệ và cả năm ảnh được tải. Nút “Xem dự án” điều hướng đến phần dự án. Tuy nhiên, tên ở logo là “Nguyễn Văn dũng”, không khớp với tên “Nguyễn Văn An” trong phần giới thiệu; liên kết GitHub, LinkedIn và các nút “Xem chi tiết” hiện trỏ đến `#`, chưa dẫn đến nội dung đích.

## 2. UI/UX

**Kết quả: Chưa đạt trên màn hình hẹp.** Ở desktop, bố cục hiển thị đầy đủ. Lưới dự án chuyển lần lượt thành 1, 2 và 3 cột tại các chiều rộng kiểm tra 390 px, 768 px và 1280 px. Tuy vậy, ảnh mobile cho thấy tiêu đề, đoạn giới thiệu và một số hàng nội dung bị cắt ở mép phải. `overflow-x: hidden` đang che phần tràn thay vì làm nội dung vừa màn hình.

## 3. Khả năng vận hành - xử lý lỗi

**Kết quả: Đạt một phần.** Trang tĩnh mở được trực tiếp trong trình duyệt và các ảnh hiện có tải thành công. Không có JavaScript chạy nghiệp vụ hoặc backend; do đó chưa có luồng xử lý lỗi mạng, dữ liệu hay biểu mẫu để kiểm thử. Chưa xác minh việc phục vụ qua HTTP hoặc trên máy chủ triển khai.

## 4. Bảo mật

**Kết quả: Đạt trong phạm vi rà soát tĩnh, chưa phải kiểm toán bảo mật.** Trang không có biểu mẫu nhập liệu, mã JavaScript phía client hay thư viện bên thứ ba được nhúng; không thấy thông tin xác thực hoặc bí mật trong mã đã kiểm tra. Chưa đánh giá cấu hình máy chủ, HTTPS, HTTP security headers hoặc chính sách CSP; các nội dung này phụ thuộc môi trường triển khai.

## 5. Chất lượng mã nguồn

**Kết quả: Đạt một phần.** HTML có cấu trúc ngữ nghĩa với `header`, `nav`, `main`, `section` và `article`; ảnh có văn bản thay thế. CSS dùng biến tùy chỉnh, Flexbox, Grid, breakpoint mobile-first, `:focus-visible` và hỗ trợ `prefers-reduced-motion`. Cần sửa tên hiển thị không nhất quán, các liên kết mẫu và lỗi tràn nội dung mobile. Không tìm thấy bộ kiểm thử tự động hoặc cấu hình lint trong phạm vi dự án.

## 6. Khả năng triển khai

**Kết quả: Đạt một phần.** Đây là website tĩnh, không cần bước build hay backend, nên có thể triển khai trên dịch vụ lưu trữ tệp tĩnh. Việc mở trực tiếp trong trình duyệt đã được xác nhận; chưa kiểm thử bản triển khai qua HTTP, Docker hoặc một nhà cung cấp hosting thực tế. Chưa có minh chứng cho quy trình CI/CD.

## Minh chứng

- [Ảnh giao diện desktop](screenshots/desktop.png)
- [Ảnh giao diện mobile](screenshots/mobile.png)

Ảnh được chụp từ trang đang chạy trong trình duyệt vào ngày kiểm thử. Ảnh mobile ghi nhận tình trạng nội dung bị cắt ngang nêu tại tiêu chí UI/UX.
