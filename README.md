# CME Tracker

Web app một file (`index.html`) để lưu thông tin và chứng nhận CME, tự tính giờ tín chỉ trong chu kỳ 5 năm (mục tiêu mặc định 120 giờ tín chỉ theo Thông tư 32/2023/TT-BYT).

- Không cần máy chủ, không cần cài đặt.
- Dữ liệu lưu trong trình duyệt (localStorage + IndexedDB cho file scan), không gửi đi đâu.
- Tự cộng giờ tín chỉ trong chu kỳ, báo còn thiếu, số ngày còn lại, phân bổ theo từng năm.
- Xuất/nhập sao lưu JSON (kèm file scan) và xuất CSV.

## Đưa lên GitHub Pages

1. Tạo repository mới trên GitHub (ví dụ `cme-tracker`).
2. Tải `index.html` và `README.md` lên nhánh `main` (Add file → Upload files).
3. Vào **Settings → Pages**, mục *Build and deployment* chọn **Deploy from a branch**, nhánh `main`, thư mục `/ (root)`, bấm Save.
4. Sau 1–2 phút truy cập `https://<tên-github>.github.io/cme-tracker/`.

Lưu ý: nếu repository để public thì chỉ mã nguồn công khai; dữ liệu cá nhân của bạn vẫn chỉ nằm trên trình duyệt của bạn. Mỗi trình duyệt/thiết bị có kho dữ liệu riêng, hãy dùng chức năng **Xuất sao lưu** để chuyển sang thiết bị khác.

## Hệ số quy đổi

Mặc định 1 tiết = 1 giờ tín chỉ. Với hội nghị, biên soạn tài liệu, nghiên cứu, giảng dạy, tự học… hãy chỉnh hệ số ở mục "Hệ số quy đổi theo hình thức" theo **Phụ lục I Thông tư 32/2023/TT-BYT**. Ứng dụng chỉ là công cụ hỗ trợ cá nhân, không thay thế xác nhận chính thức của cơ quan quản lý.
