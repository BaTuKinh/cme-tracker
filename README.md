# CME Tracker

Công cụ web để lưu thông tin, chứng nhận CME và tự tính giờ tín chỉ cập nhật kiến thức y khoa liên tục trong chu kỳ 5 năm (mặc định yêu cầu tối thiểu 120 giờ tín chỉ theo Thông tư 32/2023/TT-BYT).

**Tác giả / Bản quyền:** © 2026 Bá Tử Kinh | Tường Vi. Bảo lưu mọi quyền.

## Tính năng

- Chạy chỉ với một file `index.html`, không cần máy chủ, không cần cài đặt.
- Dữ liệu lưu ngay trong trình duyệt của bạn (localStorage và IndexedDB cho file scan), không gửi đi đâu.
- Tự cộng giờ tín chỉ trong chu kỳ, báo còn thiếu, số ngày còn lại, mức cần học mỗi tháng và phân bổ theo từng năm.
- Đính kèm bản scan chứng nhận (PDF/ảnh, tối đa 8 MB mỗi file), xem ngay trong trang, kể cả trên điện thoại.
- Biểu mẫu nhập chia 3 nhóm theo đúng giấy chứng nhận CME: **Hoạt động** (chủ đề, hình thức, đơn vị tổ chức, ngày), **Giờ tín chỉ** (ưu tiên số ghi trên chứng nhận, hoặc tự tính) và **Chứng nhận** (đơn vị cấp, số, số lưu sổ, ngày cấp, mã cơ sở, file scan).
- Ô **Nội dung / chủ đề** lớn, tự giãn nhiều dòng; có nút đổi chữ in hoa toàn bộ sang chữ thường. **Hình thức** chọn bằng các nút bấm, không bị cắt chữ. Thanh dưới cùng luôn hiện số giờ tín chỉ sắp lưu và cho biết hoạt động có tính vào chu kỳ hiện tại không. Danh sách tự chuyển thành dạng thẻ trên điện thoại.
- **Kỹ năng, đào tạo nội bộ** (vận hành thiết bị, quy trình mới theo ISO 15189:2022, đánh giá năng lực… dùng được cho mọi khoa): chọn nhóm này hoặc chế độ **Không tính tín chỉ**. Chỉ cần nội dung và ngày; số chứng nhận, số lưu sổ, thời lượng, người đánh giá, kết quả, “Hiệu lực đến” đều tùy chọn. Không cộng vào 120 giờ; có hạn hiệu lực thì app nhắc khi cần đánh giá lại. Có thể thêm nhóm riêng ở mục Hệ số quy đổi.
- **Hồ sơ quan trọng** ngay đầu trang: chứng chỉ hành nghề, bằng cấp, chứng chỉ chuyên môn, giấy tờ khác, kèm bản scan xem một chạm và nhãn còn hạn / sắp hết hạn (trong 90 ngày) / hết hạn. Được sao lưu, gộp giữa các máy và xuất Excel. Lưu ý đây là giấy tờ cá nhân, hãy cất kỹ file sao lưu JSON.
- **Danh sách dễ tìm:** ô tìm kiếm không cần gõ dấu và gõ nhiều từ cùng lúc (tên, số chứng nhận, đơn vị, năm…); sắp xếp mới nhất / cũ nhất / A→Z / nhiều tín chỉ nhất; lọc theo năm, hình thức, tình trạng (trong hoặc ngoài chu kỳ, có hoặc chưa có bản scan, sắp hết hiệu lực); danh sách trình bày như **sổ theo từng năm**: mỗi năm là một dòng gọn (số hoạt động, tổng giờ tín chỉ), bấm vào để mở các hoạt động của năm đó; mỗi hoạt động chỉ hiện một dòng (ngày, tên, giờ), bấm vào mới xổ ra chi tiết, số chứng nhận, file scan, Sửa/Xóa. Hoạt động hoặc hồ sơ chưa có bản scan sẽ hiện “Chưa có bản scan” kèm nút **Đính kèm file** để chụp hoặc chọn file ngay, không cần vào Sửa. Có nút “Mở hết / Thu gọn các năm”; khi đang tìm hoặc lọc thì các năm có kết quả tự mở.
- Xuất **Excel (.xlsx)** gồm các sheet: `Hoạt động` (danh sách có tín chỉ, bộ lọc, công thức, dòng tổng trong chu kỳ), `Kỹ năng, đào tạo nội bộ`, `Hồ sơ quan trọng` (hai sheet này chỉ xuất hiện khi có dữ liệu), `Tổng hợp` và `Hệ số quy đổi`.
- Xuất CSV, và xuất/nhập sao lưu JSON (kèm file scan) để chuyển sang thiết bị khác, có **chế độ gộp dữ liệu** để dùng cả máy tính lẫn điện thoại.
- **Cài như ứng dụng và dùng khi mất mạng** (PWA): thêm vào màn hình chính điện thoại hoặc cài trên máy tính; sau lần mở đầu tiên có mạng, vẫn xem, nhập và xuất dữ liệu được khi ngoại tuyến.
- Có sẵn khối **Lưu ý quan trọng**, **Hướng dẫn sử dụng**, thanh điều hướng nhanh và **cảnh báo nhắc sao lưu** (khi chưa từng sao lưu hoặc quá 30 ngày).

## Các file của dự án

| File | Vai trò |
|---|---|
| `index.html` | Toàn bộ ứng dụng |
| `manifest.webmanifest` | Khai báo để cài thành ứng dụng (tên, biểu tượng, màu) |
| `sw.js` | Service worker, giúp chạy khi mất mạng |
| `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png` | Biểu tượng ứng dụng |
| `README.md` | Hướng dẫn này |

**Phải tải lên đủ cả 8 file, giữ nguyên tên và cùng một thư mục.**

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
2. Kéo thả **đủ 8 file** trong bảng "Các file của dự án" ở trên vào, giữ nguyên tên file. Thiếu `sw.js`, `manifest.webmanifest` hoặc các file biểu tượng thì không cài được và không dùng được khi mất mạng.
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
2. Ở mục **Thêm hoạt động CME**, nhập từng chứng nhận theo bảng đối chiếu bên dưới. Phần **Giờ tín chỉ** chọn “Theo chứng nhận” và nhập đúng số ở dòng “Quy đổi tương đương”.
3. Chỉ khi chứng nhận **không ghi** giờ tín chỉ (ví dụ giấy xác nhận tham dự chỉ ghi số tiết) mới chọn “Tự tính: số tiết × hệ số”, và khi đó phải chỉnh mục **Hệ số quy đổi** theo **Phụ lục I Thông tư 32/2023/TT-BYT** (mặc định 1 tiết = 1 giờ tín chỉ).

**Đối chiếu giấy chứng nhận với các ô nhập**

| Trên giấy chứng nhận | Ô trong app |
|---|---|
| Số: …/…/GCN-… | Số chứng nhận |
| Cơ quan, trường hoặc bệnh viện ở đầu giấy, dấu và người ký | Đơn vị cấp chứng nhận |
| 1. Hình thức (hội nghị, khóa học…) | Hình thức |
| 2. Nội dung / chủ đề | Nội dung / chủ đề |
| 3. Đơn vị / cá nhân chịu trách nhiệm | Đơn vị / cá nhân chịu trách nhiệm tổ chức |
| 4. Thời gian | Ngày tham dự (và “Đến ngày” nếu kéo dài nhiều ngày) |
| Quy đổi tương đương: … giờ tín chỉ | Số giờ tín chỉ ghi trên chứng nhận |
| Ngày … tháng … năm … (cạnh phần ký) | Ngày cấp chứng nhận |
| Lưu số: … | Số lưu sổ |
| Họ tên, ngày sinh, đơn vị công tác của người được chứng nhận | Không cần nhập; đã có trong ảnh scan để đối chiếu |
4. Xem mục **Tổng quan** để biết đã tích lũy bao nhiêu giờ, còn thiếu bao nhiêu và còn bao nhiêu ngày.

### Bước 5. Cài như ứng dụng trên điện thoại hoặc máy tính (khuyên dùng)

Mở địa chỉ của app **một lần khi có mạng**, đợi trang tải xong, rồi:

- **Android (Chrome):** bấm nút **Cài đặt ứng dụng** ở đầu trang, hoặc menu ⋮ → *Cài đặt ứng dụng* / *Thêm vào màn hình chính*.
- **iPhone, iPad (Safari):** bấm nút Chia sẻ → *Thêm vào Màn hình chính*. Nên làm bước này vì iOS có thể tự xóa dữ liệu của trang web nếu lâu không mở.
- **Máy tính (Chrome, Edge):** bấm biểu tượng cài đặt ở cuối thanh địa chỉ.

Sau đó mở app từ biểu tượng trên màn hình. Khi mất mạng, góc trên hiện "Ngoại tuyến – dữ liệu vẫn lưu trên máy" và mọi chức năng vẫn dùng bình thường. Khi có mạng trở lại, app tự lấy bản mới nếu bạn đã cập nhật trên GitHub.

### Bước 6. Xuất dữ liệu và sao lưu

Vào mục **Sao lưu & khôi phục**:

- **Xuất Excel (.xlsx):** lấy toàn bộ danh sách và tổng hợp để lưu, in hoặc nộp hồ sơ. File Excel không kèm ảnh scan.
- **Xuất bảng (CSV):** bản bảng tính đơn giản.
- **Xuất sao lưu (JSON):** đầy đủ dữ liệu kèm file scan, dùng để chuyển sang máy khác hoặc phòng khi mất dữ liệu trình duyệt.
- **Nhập & gộp dữ liệu (khuyên dùng):** thêm hoạt động mới từ file sao lưu vào máy này mà không làm mất dữ liệu đang có.
- **Nhập & ghi đè:** thay hoàn toàn dữ liệu máy này bằng file sao lưu (dùng khi khôi phục máy mới hoặc muốn hai máy giống hệt nhau).

#### Dùng cả máy tính và điện thoại

Mỗi thiết bị giữ dữ liệu riêng, nên chuyển qua lại bằng sao lưu:

1. Ở máy A: **Xuất sao lưu (JSON)**, gửi file sang máy B (Zalo, email, Google Drive…).
2. Ở máy B: **Nhập & gộp dữ liệu** và chọn file đó. Làm tương tự theo chiều ngược lại khi cần.

Cách gộp hoạt động như sau:

- Hoạt động chỉ có ở một máy sẽ được thêm vào.
- Hoạt động có ở cả hai máy nhưng đã được sửa: giữ bản **sửa sau cùng** (so theo giờ trên thiết bị, nên để đồng hồ hai máy đúng).
- Hoạt động đã **xóa ở máy kia** sẽ bị xóa ở máy này, trừ khi bạn đã sửa lại sau thời điểm xóa.
- Hoạt động trùng nội dung (cùng ngày, cùng tên, cùng số lượng) nhưng nhập riêng ở hai máy sẽ chỉ giữ một bản, nên bản scan đính kèm của mục bị bỏ qua sẽ không được thêm vào.
- **Hồ sơ và hệ số quy đổi giữ theo máy nhận**, chỉ điền vào chỗ còn trống. Muốn đổi hệ số hoặc ngày chu kỳ, hãy sửa ở từng máy.
- Gộp xong, app báo số hoạt động đã thêm, cập nhật, xóa và bỏ qua.

Trước khi gộp lần đầu, nên **xuất sao lưu máy nhận** để có bản dự phòng.

Nên xuất sao lưu JSON định kỳ (ví dụ mỗi lần thêm vài chứng nhận mới) và cất ở nơi an toàn như Google Drive.

### Bước 7. Cập nhật phiên bản mới của app

1. Vào repository, chọn **Add file → Upload files**.
2. Tải các file mới lên với **đúng tên cũ** để ghi đè (luôn tải cả `index.html` và `sw.js` cùng lúc), rồi **Commit changes**.
3. Chờ 1–2 phút. Mở app khi có mạng; nếu vẫn thấy bản cũ, đóng hẳn app rồi mở lại một lần nữa (trên máy tính nhấn **Ctrl+F5**).

Dữ liệu của bạn nằm trong trình duyệt nên **không bị mất** khi cập nhật app, miễn là vẫn dùng đúng địa chỉ và trình duyệt cũ.

---

## Xử lý sự cố

| Tình huống | Cách xử lý |
|---|---|
| Mở địa chỉ báo 404 | Kiểm tra `index.html` nằm ở thư mục gốc của repository và Pages đã bật ở Bước 3; chờ vài phút. |
| Mở trên máy khác không thấy dữ liệu | Dữ liệu chỉ nằm trên trình duyệt đã nhập. Xuất sao lưu JSON ở máy cũ rồi dùng **Nhập & gộp dữ liệu** (hoặc Nhập & ghi đè nếu máy mới còn trống) ở máy mới. |
| Gộp xong thiếu một hoạt động | Có thể nó đã bị xóa ở máy kia, hoặc bị coi là trùng nội dung với mục đã có (cùng ngày, tên, số lượng). Kiểm tra thông báo kết quả gộp và nhập lại nếu cần. |
| Mất dữ liệu sau khi xóa lịch sử trình duyệt | Nhập lại từ file sao lưu JSON gần nhất. |
| Bấm "Xem file" không thấy gì | Bản mới mở file trong một cửa sổ ngay trong trang (có nút Mở trong tab mới, Tải về, Chia sẻ). Hãy cập nhật app lên bản mới nhất (đủ 3 file `index.html`, `sw.js`, `README.md`) rồi tải lại. |
| Hoạt động có nhãn "thiếu file" sau khi nhập sao lưu | File sao lưu không chứa file đính kèm của mục đó (thường do xuất từ bản app cũ hoặc file gốc đã bị mất). Bấm Sửa để đính kèm lại, rồi xuất sao lưu mới. Khi xuất, app báo "file đính kèm x/y" để bạn biết có thiếu không. |
| Sao lưu JSON rất nặng hoặc gửi qua Zalo không được | Mỗi ảnh/PDF được mã hóa nên file lớn hơn bản gốc khoảng một phần ba. Hãy chụp ảnh nhỏ hơn hoặc gửi qua Google Drive/email. |
| Dùng chế độ ẩn danh | Dữ liệu bị xóa khi đóng cửa sổ; hãy dùng cửa sổ thường. |
| Không thấy nút "Cài đặt ứng dụng" | Chỉ hiện trên Chrome/Edge khi trang chạy qua https và đủ 8 file. Trên iPhone dùng Chia sẻ → Thêm vào Màn hình chính. |
| Mất mạng không mở được app | Bạn cần mở app ít nhất một lần khi có mạng để tải về máy. Nếu vẫn lỗi, mở lại khi có mạng rồi thử lại. |
| iPhone/iPad: nhập trong app rồi mở bằng Safari không thấy dữ liệu | Trên iOS, app đã thêm vào Màn hình chính và Safari có thể là hai kho dữ liệu riêng. Hãy chọn một nơi dùng cố định (khuyên dùng app đã cài), hoặc chuyển qua lại bằng sao lưu JSON. |
| Cảnh báo "chưa sao lưu" | Vào mục Sao lưu, bấm "Xuất sao lưu (JSON)"; cảnh báo tự tắt. |

## Lưu ý quan trọng

- Repository để Public nên mã nguồn ai cũng xem được; dữ liệu cá nhân và chứng nhận của bạn **không** nằm trong repository.
- Đây là công cụ hỗ trợ cá nhân, không thay thế xác nhận chính thức của cơ quan quản lý hay cơ quan cấp chứng chỉ hành nghề.
- Hệ số quy đổi do người dùng tự nhập; hãy đối chiếu với văn bản quy phạm pháp luật hiện hành.

## Bản quyền

© 2026 Bá Tử Kinh | Tường Vi. Bảo lưu mọi quyền. Mã nguồn không kèm giấy phép mã nguồn mở; việc sao chép, sửa đổi hoặc phân phối lại ngoài phạm vi điều khoản sử dụng của GitHub cần có sự đồng ý của tác giả.
