# TRƯỜNG THPT QUANG TRUNG
## Hệ Thống Giao Bài Tập & Hoạt Động Nhóm Trực Tuyến Môn Giáo Dục Quốc Phòng và An Ninh

Ứng dụng web tương tác đơn tệp (Single-Page Application) phục vụ hoạt động học tập, thi đua nhóm và đánh giá theo thời gian thực cho học sinh môn Giáo dục Quốc phòng và An ninh (GDQP&AN) tại **Trường THPT Quang Trung**.

---

## 1. Giới thiệu tổng quan

Hệ thống được thiết kế nhằm hiện đại hóa tiết học chuyên đề: **"Phòng, chống vi phạm pháp luật và tội phạm công nghệ cao"**. Ứng dụng tích hợp ngân hàng 10 câu hỏi trắc nghiệm trọng tâm, đồng hồ đếm ngược 5 phút, cơ chế bảo mật phân quyền (học sinh / giáo viên), cùng bảng điều khiển hiển thị biểu đồ điểm số và chi tiết bài làm cập nhật theo thời gian thực.

Toàn bộ ứng dụng được đóng gói thành một tệp HTML duy nhất (`index.html`), hoạt động độc lập trên mọi trình duyệt web (Chrome, Edge, Safari, Firefox, Cốc Cốc) và tối ưu hoàn hảo trên cả máy tính, máy tính bảng lẫn điện thoại thông minh.

---

## 2. Tính năng nổi bật

### Giao diện & Nhận diện thương hiệu
- **Tiêu đề trường**: Dòng chữ lớn **"TRƯỜNG THPT QUANG TRUNG"** màu xanh đậm (`#0b3c60`), trang trọng, nổi bật ở trung tâm thanh tiêu đề.
- **Hào khí Quốc kỳ**: Hình ảnh cờ đỏ sao vàng Việt Nam được thiết kế chìm tinh tế phía sau (watermark), tạo không khí trang nghiêm và tinh thần yêu nước.

### Khu vực Học sinh (8 Nhóm thi đua)
- **8 ô tròn nổi 3D đa sắc**: Mỗi nhóm có một nút tròn 3D mang màu sắc nhận diện riêng biệt:
  - **Nhóm 1**: Đỏ Ruby (`#E53935`)
  - **Nhóm 2**: Cam Rực rỡ (`#FB8C00`)
  - **Nhóm 3**: Vàng Hổ phách (`#FDD835`)
  - **Nhóm 4**: Xanh Lục Bảo (`#43A047`)
  - **Nhóm 5**: Xanh Ngọc Lam (`#00ACC1`)
  - **Nhóm 6**: Xanh Dương Hoàng gia (`#1E88E5`)
  - **Nhóm 7**: Tím Thủy chung (`#8E24AA`)
  - **Nhóm 8**: Hồng Cánh sen (`#D81B60`)
- **Mật khẩu nhóm**: Học sinh nhấp vào ô tròn của nhóm mình và nhập mật khẩu: `vietnam` để vào phòng làm bài.
- **Đồng hồ đếm ngược**: Đếm ngược từ **05:00** về **00:00**. Tự động chuyển màu cảnh báo khi dưới 1 phút (màu cam) và dưới 30 giây (màu đỏ nhấp nháy). Hệ thống tự động thu bài khi hết giờ.
- **Thanh chuyển nhanh câu hỏi**: Giúp các nhóm dễ dàng theo dõi tiến độ (câu đã chọn hiển thị xanh lá, câu chưa chọn hiển thị xám).
- **Xem lại kết quả**: Sau khi nộp bài, nhóm có thể xem điểm số ngay lập tức (thang điểm 10), số câu đúng, số câu sai và phần giải thích kiến thức chi tiết.

### Khu vực Giáo viên (Dashboard thời gian thực)
- **Đăng nhập quản trị**: Nút đăng nhập ở góc trên bên phải, mật khẩu: `giaovien123`.
- **Đồ thị điểm số 8 nhóm (SVG Native)**: Biểu đồ cột thể hiện điểm số từ Nhóm 1 đến Nhóm 8. Màu sắc của từng cột khớp 100% với màu sắc ô tròn của nhóm tương ứng ở màn hình chính.
- **Bảng chi tiết bài làm**:
  - Tình trạng nộp bài, thời gian nộp, điểm số, số câu đúng và số câu sai.
  - Ma trận 10 câu hỏi (từ câu 1 đến câu 10) với màu sắc trực quan (xanh: đúng, đỏ: sai).
  - **Ô nhận xét, đánh giá của giáo viên**: Giáo viên có thể nhập nhận xét trực tiếp cho từng nhóm và lưu lại.
  - Nút **"Xem chi tiết"** để xem toàn bộ bài làm từng câu của nhóm.
  - Nút **"Cho làm lại"** để đặt lại dữ liệu của một nhóm khi cần thi lại.
- **Đồng bộ thời gian thực (Real-time Sync)**: Kết hợp công nghệ `BroadcastChannel`, `localStorage` và `storage event`. Khi học sinh nộp bài ở một thiết bị/tab khác, màn hình giáo viên (chiếu trên máy chiếu) sẽ tự động cập nhật kết quả ngay lập tức mà không cần tải lại trang (F5).

---

## 3. Thông tin tài khoản & Mật khẩu mặc định

| Đối tượng | Mật khẩu truy cập | Ghi chú |
| :--- | :--- | :--- |
| **8 Nhóm học sinh** | `vietnam` | Áp dụng chung cho cả 8 nhóm (không phân biệt chữ hoa/thường) |
| **Giáo viên bộ môn** | `giaovien123` | Dùng để truy cập bảng điều khiển và đồ thị đánh giá |

---

## 4. Hướng dẫn đưa trang web lên GitHub & Kích hoạt GitHub Pages

GitHub Pages cung cấp dịch vụ lưu trữ trang web miễn phí, giúp giáo viên có ngay một đường link (URL) để gửi cho học sinh hoặc trình chiếu trên lớp học.

### Cách 1: Sử dụng giao diện Web GitHub (Đơn giản nhất, không cần cài phần mềm)

1. **Đăng nhập GitHub**:
   - Truy cập [https://github.com](https://github.com) và đăng nhập tài khoản (hoặc đăng ký miễn phí nếu chưa có).

2. **Tạo Kho lưu trữ (Repository) mới**:
   - Nhấp vào dấu **`+`** ở góc trên bên phải màn hình, chọn **New repository**.
   - Tại mục **Repository name**, đặt tên dự án: ví dụ `gdqp-thpt-quang-trung`.
   - Chọn chế độ **Public** (để sử dụng tính năng GitHub Pages miễn phí).
   - Đánh dấu chọn **Add a README file**.
   - Nhấp nút **Create repository**.

3. **Tải tệp tin lên Repository**:
   - Trong trang Repository vừa tạo, nhấp vào nút **Add file** -> chọn **Upload files**.
   - Kéo thả 2 tệp tin sau vào trình duyệt:
     - `index.html` (được đổi tên từ `web_gdqp_thpt_quang_trung.html`).
     - `README.md`.
   - Nhấp nút **Commit changes** màu xanh ở phía dưới để lưu lại.

4. **Kích hoạt GitHub Pages (Tạo link web trực tiếp)**:
   - Trên thanh menu của Repository, nhấp vào tab **Settings** (biểu tượng bánh răng).
   - Ở cột danh mục bên trái, chọn mục **Pages** (trong phần Code and automation).
   - Tại mục **Build and deployment** -> **Branch**:
     - Chọn nhánh: **`main`** (hoặc `master`).
     - Chọn thư mục: **`/(root)`**.
     - Nhấp nút **Save**.
   - Đợi khoảng 1 đến 2 phút, tải lại trang Settings -> Pages. Bạn sẽ thấy dòng thông báo màu xanh:
     > **Your site is live at https://&lt;tên-tài-khoản&gt;.github.io/gdqp-thpt-quang-trung/**
   - Đây chính là đường link trực tiếp của trang web. Giáo viên có thể chia sẻ link này hoặc tạo mã QR để học sinh quét bằng điện thoại vào làm bài.

---

### Cách 2: Sử dụng dòng lệnh Git (Dành cho người dùng quen thuộc với Git CLI)

Nếu máy tính đã cài đặt Git, bạn có thể đẩy toàn bộ mã nguồn lên GitHub theo các bước sau:

```bash
# 1. Khởi tạo kho lưu trữ git
git init

# 2. Thêm các tệp tin vào danh sách theo dõi
git add index.html README.md

# 3. Tạo commit đầu tiên
git commit -m "feat: Khoi tao ung dung hoat dong nhom GDQP THPT Quang Trung"

# 4. Đổi tên nhánh chính thành main
git branch -M main

# 5. Kết nối với kho lưu trữ từ xa trên GitHub (thay URL của bạn vào)
git remote add origin https://github.com/<ten-tai-khoan>/gdqp-thpt-quang-trung.git

# 6. Đẩy mã nguồn lên GitHub
git push -u origin main
```

Sau khi đẩy mã nguồn thành công, bạn vào **Settings** -> **Pages** trên GitHub và chọn nhánh `main` để kích hoạt trang web tương tự như Cách 1.

---

## 5. Quy trình tổ chức hoạt động nhóm trên lớp

1. **Chuẩn bị**:
   - Giáo viên mở đường link trang web trên máy tính giảng dạy, kết nối với máy chiếu hoặc màn hình tương tác.
   - Nhấp vào **"Giáo Viên Đăng Nhập"**, nhập mật khẩu `giaovien123` để mở sẵn Bảng điều khiển thời gian thực.
   - Tạo mã QR dẫn đến đường link trang web để học sinh trong lớp quét bằng điện thoại.

2. **Tiến hành làm bài**:
   - Lớp học được chia thành 8 nhóm tương ứng với 8 ô tròn trên màn hình.
   - Đại diện nhóm sử dụng điện thoại/máy tính truy cập vào trang web, nhấp vào ô tròn của nhóm mình.
   - Nhập mật khẩu `vietnam`, nhập tên nhóm trưởng / thành viên rồi nhấn **"Vào Làm Bài"**.
   - Cả nhóm cùng thảo luận và hoàn thành 10 câu trắc nghiệm trong thời gian đếm ngược 5 phút.

3. **Thu bài và Đánh giá**:
   - Nhóm nộp bài xong, kết quả và điểm số sẽ ngay lập tức xuất hiện trên Đồ thị cột và Bảng chi tiết của Giáo viên trên màn hình chiếu.
   - Giáo viên dựa vào ma trận câu đúng/sai để nhận xét trực tiếp, ghi chú đánh giá vào hệ thống và tuyên dương các nhóm có kết quả xuất sắc.

---

## 6. Cấu trúc tệp tin trong dự án

```text
├── index.html       # Ứng dụng web hoàn chỉnh (HTML5, CSS3, JavaScript đóng gói đơn tệp)
└── README.md        # Hướng dẫn chi tiết triển khai và tổ chức dạy học
```

---

## 7. Bản quyền & Thông tin liên hệ

- **Đơn vị phát triển & Ứng dụng**: Bộ môn Giáo dục Quốc phòng và An ninh - Trường THPT Quang Trung.
- **Mục đích**: Ứng dụng công nghệ thông tin và chuyển đổi số trong dạy học phát triển phẩm chất, năng lực học sinh.
