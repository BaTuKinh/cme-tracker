# CME Tracker

Công cụ web để lưu thông tin, chứng nhận CME và tự tính giờ tín chỉ cập nhật kiến thức y khoa liên tục trong chu kỳ 5 năm (mặc định yêu cầu tối thiểu 120 giờ tín chỉ theo Thông tư 32/2023/TT-BYT).

**Tác giả / Bản quyền:** © 2026 Bá Tử Kinh | Tường Vi. Bảo lưu mọi quyền.

## Tính năng

- Chạy chỉ với một file `index.html`, không cần máy chủ, không cần cài đặt.
- Dữ liệu lưu ngay trong trình duyệt của bạn (localStorage và IndexedDB cho file scan), không gửi đi đâu.
- Tự cộng giờ tín chỉ trong chu kỳ, báo còn thiếu, số ngày còn lại, mức cần học mỗi tháng và phân bổ theo từng năm.
- Đính kèm bản scan chứng nhận (PDF/ảnh, tối đa 8 MB mỗi file).
- Xuất **Excel (.xlsx)** gồm 3 sheet: `Hoạt động` (đầy đủ danh sách, có bộ lọc, giờ tín chỉ là công thức, dòng tổng trong chu kỳ), `Tổng hợp` (hồ sơ, chu kỳ, giờ tích lũy, còn thiếu) và `Hệ số quy đổi`.
- Xuất CSV, và xuất/nhập sao lưu JSON (kèm file scan) để chuyển sang thiết bị khác.

---

## Hướng dẫn từ đầu

### Bước 1. Tạo repository trên GitHub

1. Đăng nhập GitHub, bấm **New repository**.
2. Điền:
   - **Repository name:** `cme-tracker`
   - **Description** (tùy chọn): `Theo dõi giờ tín chỉ CME theo Thông tư 32/2023/TT-BYT`
   - **Visibility:** **Public** (GitHub Pages miễn phí chỉ chạy với repository public)
   - **Add README:** Off, **.gitignore:** No, **License:** No license
3. Bấm **Create repository**.

### Bước 2. Tải file lên

1. Trong repository vừa tạo, chọn liên kết **uploading an existing file** (hoặc **Add file → Upload files**).
2. Kéo thả hai file `index.html` và `README.md` vào, giữ nguyên tên file.
3. Bấm **Commit changes** (nhánh `main`).

### Bước 3. Bật GitHub Pages

1. Vào **Settings → Pages**.
2. Ở mục *Build and deployment*, **Source:** chọn *Deploy from a branch*.
3. **Branch:** chọn `main`, thư mục `/ (root)`, bấm **Save**.
4. Chờ 1–2 phút rồi mở: `https://batukinh.github.io/cme-tracker/`
   (dạng chung: `https://<tên-github>.github.io/<tên-repository>/`).

Có thể lưu địa chỉ này vào màn hình chính điện thoại hoặc đánh dấu trang để dùng hằng ngày.

### Bước 4. Thiết lập lần đầu trong app

1. Ở mục **Hồ sơ & chu kỳ 5 năm**, nhập họ tên, số chứng chỉ hành nghề, **ngày bắt đầu chu kỳ** (ngày cấp hoặc gia hạn) và số giờ yêu cầu (mặc định 120). Hãy đối chiếu cách tính thời điểm bắt đầu với cơ quan cấp phép của bạn.
2. Ở mục **Hệ số quy đổi theo hình thức**, mặc định 1 tiết = 1 giờ tín chỉ. Với hội nghị, biên soạn tài liệu, nghiên cứu, giảng dạy, tự học, hãy chỉnh hệ số theo **Phụ lục I Thông tư 32/2023/TT-BYT**.
3. Ở mục **Thêm hoạt động CME**, nhập từng khóa học: ngày hoàn thành, tên, đơn vị, mã cơ sở đào tạo, hình thức, số tiết, số chứng nhận, đính kèm bản scan. Giờ tín chỉ tự tính theo số tiết × hệ số.
4. Xem mục **Tổng quan** để biết đã tích lũy bao nhiêu giờ, còn thiếu bao nhiêu và còn bao nhiêu ngày.

### Bước 5. Xuất dữ liệu và sao lưu

Vào mục **Sao lưu & khôi phục**:

- **Xuất Excel (.xlsx):** lấy toàn bộ danh sách và tổng hợp để lưu, in hoặc nộp hồ sơ. File Excel không kèm ảnh scan.
- **Xuất bảng (CSV):** bản bảng tính đơn giản.
- **Xuất sao lưu (JSON):** đầy đủ dữ liệu kèm file scan, dùng để chuyển sang máy khác hoặc phòng khi mất dữ liệu trình duyệt. Dùng **Nhập sao lưu…** để khôi phục.

Nên xuất sao lưu JSON định kỳ (ví dụ mỗi lần thêm vài chứng nhận mới) và cất ở nơi an toàn như Google Drive.

### Bước 6. Cập nhật phiên bản mới của app

1. Vào repository, bấm vào file `index.html`, chọn biểu tượng bút chì (Edit) hoặc quay lại trang chính chọn **Add file → Upload files**.
2. Tải `index.html` mới lên với **đúng tên cũ** để ghi đè, rồi **Commit changes**.
3. Chờ 1–2 phút, mở lại trang và nhấn **Ctrl+F5** (hoặc kéo tải lại trên điện thoại) để xóa bộ nhớ đệm.

Dữ liệu của bạn nằm trong trình duyệt nên **không bị mất** khi cập nhật app, miễn là vẫn dùng đúng địa chỉ và trình duyệt cũ.

---

## Xử lý sự cố

| Tình huống | Cách xử lý |
|---|---|
| Mở địa chỉ báo 404 | Kiểm tra `index.html` nằm ở thư mục gốc của repository và Pages đã bật ở Bước 3; chờ vài phút. |
| Mở trên máy khác không thấy dữ liệu | Dữ liệu chỉ nằm trên trình duyệt đã nhập. Xuất sao lưu JSON ở máy cũ rồi nhập vào máy mới. |
| Mất dữ liệu sau khi xóa lịch sử trình duyệt | Nhập lại từ file sao lưu JSON gần nhất. |
| Không xem được file scan | Trình duyệt có thể chặn cửa sổ bật lên; cho phép pop-up cho trang này. |
| Dùng chế độ ẩn danh | Dữ liệu bị xóa khi đóng cửa sổ; hãy dùng cửa sổ thường. |

## Lưu ý quan trọng

- Repository để Public nên mã nguồn ai cũng xem được; dữ liệu cá nhân và chứng nhận của bạn **không** nằm trong repository.
- Đây là công cụ hỗ trợ cá nhân, không thay thế xác nhận chính thức của cơ quan quản lý hay cơ quan cấp chứng chỉ hành nghề.
- Hệ số quy đổi do người dùng tự nhập; hãy đối chiếu với văn bản quy phạm pháp luật hiện hành.

## Bản quyền

© 2026 Bá Tử Kinh | Tường Vi. Bảo lưu mọi quyền. Mã nguồn không kèm giấy phép mã nguồn mở; việc sao chép, sửa đổi hoặc phân phối lại ngoài phạm vi điều khoản sử dụng của GitHub cần có sự đồng ý của tác giả.
