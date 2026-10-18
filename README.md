# GIỚI THIỆU VÀ HƯỚNG DẪN SỬ DỤNG KHO CODE GITHUB - TEAM FTA

## 1. Mục đích của kho code
Kho code GitHub của nhóm Phân tích Kỹ thuật (FTA) được thiết lập nhằm lưu trữ, quản lý và chia sẻ tập trung các tài nguyên lập trình phục vụ công việc chuyên môn của nhóm, bao gồm:
- Các bộ lọc cổ phiếu (Filter) được xây dựng và sử dụng qua các buổi họp thị trường định kỳ.
- Mã nguồn các chiến lược giao dịch (Trading Strategies), mô hình định lượng và kiểm thử (Backtest).
- Các công cụ, hàm xử lý dữ liệu và chỉ báo kỹ thuật dùng chung (AFL, Python, v.v.).

---

## 2. Ưu điểm của kho code và các tính năng tương ứng

| Ưu điểm | Tính năng GitHub đáp ứng | Mô tả chi tiết |
|:---|:---|:---|
| **Lưu trữ tập trung và đồng bộ** | **Repository (Kho lưu trữ)** | Toàn bộ code bộ lọc và chiến lược của nhóm được lưu tại một nơi duy nhất, tránh thất lạc file rời rạc trên máy cá nhân hoặc trôi tin nhắn trong nhóm chat. |
| **Kiểm soát lịch sử chỉnh sửa** | **Commit & History (Lịch sử phiên bản)** | Ghi nhận chi tiết từng lần cập nhật (ai sửa, sửa dòng nào, vào thời gian nào, lý do sửa). Cho phép khôi phục lại phiên bản bộ lọc hoặc chiến lược cũ bất kỳ lúc nào. |
| **Làm việc nhóm an toàn, không ghi đè** | **Branch (Nhánh) & Pull Request** | Các thành viên có thể phát triển hoặc thử nghiệm điều kiện lọc mới trên nhánh riêng (`Branch`), sau đó gửi yêu cầu gộp code (`Pull Request`) để kiểm tra trước khi đưa vào nhánh chính (`main`). |
| **Tra cứu và tái sử dụng nhanh** | **Search & Directory Structure** | Hỗ trợ tìm kiếm nhanh tên file hoặc đoạn code bên trong file; kết hợp với quy chuẩn đặt tên của FPTS giúp phân loại rõ ràng theo thời gian, tác giả và mục đích. |

---

## 3. Quy tắc đặt tên file code (Theo chuẩn FPTS - FTA)
Mọi file code đưa lên kho lưu trữ phải tuân thủ công thức chuẩn hóa 6 trường của nhóm FTA, phân tách bởi 5 dấu gạch dưới (`_`):

`[Mã thực thể]_[YYYY]_[Kỳ]_[Loại tài liệu]_[Nguồn]_[Mô tả].ext`

### Chi tiết các trường áp dụng cho file code của FTA:
1. **`[Mã thực thể]`** (Chỉ sử dụng 2 mã thực thể dưới đây):
   - `MARKET`: Dùng cho các bộ lọc (Filter) phục vụ họp thị trường.
   - `MOHINH`: Dùng cho code các chiến lược đầu tư, giao dịch.
2. **`[YYYY]` (Năm)**: Ghi 4 chữ số của năm thực hiện (VD: `2026`).
3. **`[Kỳ]` (Kỳ báo cáo/cập nhật)**:
   - Theo tháng: `T01`, `T02`, ..., `T12`.
   - Theo quý: `Q1`, `Q2`, `Q3`, `Q4`.
   - Cả năm: `CN`.
4. **`[Loại tài liệu]`**:
   - `MOHINH`: Áp dụng cho toàn bộ codebase nghiên cứu, bộ lọc, chiến lược giao dịch (`.afl`, `.py`, `.xlsx`...).
   - `DATA`: Áp dụng nếu lưu kèm file dữ liệu thành phẩm xuất ra từ mô hình hoặc kết quả backtest.
5. **`[Nguồn]`**:
   - Đối với file code, mô hình nghiên cứu (`MOHINH`) hoặc dữ liệu backtest (`DATA`), trường `[Nguồn]` luôn ghi **Mã tài khoản FPTS của chuyên viên** viết hoa không dấu (VD: `PHOHG`, `LANNQ`, `DUCNN2`).
6. **`[Mô tả]`**:
   - Viết liền, không dấu tiếng Việt.
   - Không dùng dấu gạch dưới (`_`). Sử dụng dấu gạch ngang (`-`) để ngăn cách các từ.
   - Ghi ngắn gọn tên bộ lọc, tên chiến lược hoặc buổi họp thị trường tương ứng.

### Ví dụ đặt tên đúng chuẩn:
- Code bộ lọc họp thị trường tháng 7/2026:
  `MARKET_2026_T07_MOHINH_LANNQ_FilterHopThiTruong-Tuan1.afl`
- Code chiến lược giao dịch Spike & Ledge:
  `MOHINH_2026_T07_MOHINH_PHOHG_SpikeAndLedge.py`
- File kết quả backtest chiến lược quý 3/2026:
  `MOHINH_2026_Q3_DATA_PHOHG_BacktestSpikeAndLedge.xlsx`

---

## 4. Hướng dẫn sử dụng cơ bản (Thao tác trên giao diện Web GitHub)

### Bước 1: Tải toàn bộ kho code hoặc từng file về máy tính
- **Cách 1 - Tải toàn bộ kho code**:
  1. Truy cập vào trang chính của kho code (Repository) trên trình duyệt web.
  2. Nhấn vào nút **`<> Code`** (màu xanh lá ở góc trên bên phải danh sách thư mục).
  3. Chọn **`Download ZIP`** để tải toàn bộ thư mục code về máy tính và giải nén.
- **Cách 2 - Tải một file lẻ (Filter hoặc Chiến lược cụ thể)**:
  1. Nhấn vào thư mục chứa file, sau đó nhấn vào tên file cần lấy.
  2. Ở góc phải khung hiển thị nội dung code, nhấn biểu tượng **`Download raw file`** (biểu tượng mũi tên tải xuống) hoặc biểu tượng **`Copy raw file`** để sao chép trực tiếp nội dung code.

### Bước 2: Xem và lấy bản cập nhật mới nhất từ nhóm
Trước buổi họp thị trường hoặc trước khi sử dụng code:
1. Truy cập vào kho code trên trình duyệt web, đảm bảo nhánh đang chọn ở góc trái trên cùng là **`main`**.
2. Nhấn vào mục **`Commits`** (biểu tượng đồng hồ lịch sử ở góc phải phía trên danh sách file) để kiểm tra các thay đổi hoặc các bộ lọc mới nhất vừa được thành viên trong nhóm tải lên.
3. Chọn vào file mới cập nhật và tải về theo thao tác ở Bước 1.

### Bước 3: Thêm file mới hoặc cập nhật code lên kho (Upload & Commit)
Sau khi viết xong bộ lọc hoặc chỉnh sửa code chiến lược trên máy cá nhân:

- **Trường hợp A - Tải file từ máy tính lên kho**:
  1. Đặt tên file trên máy tính đúng quy chuẩn 6 trường ở Mục 3.
  2. Trên web GitHub, mở đúng thư mục cần lưu, nhấn nút **`Add file`** (góc trên bên phải) -> chọn **`Upload files`**.
  3. Kéo thả file từ máy tính vào khung tải lên hoặc nhấn **`choose your files`** để chọn file.
  4. Tại mục **Commit changes** phía dưới, nhập ghi chú ngắn gọn về nội dung cập nhật (VD: *"Thêm filter họp thị trường tuần 1 tháng 7"*).
  5. Chọn **`Commit directly to the main branch`** và nhấn nút **`Commit changes`** để hoàn tất.

- **Trường hợp B - Tạo file mới hoặc sửa trực tiếp trên web**:
  1. Để tạo mới: Nhấn **`Add file`** -> **`Create new file`**, nhập tên file theo chuẩn 6 trường vào ô `Name your file...` và dán nội dung code vào khung soạn thảo.
  2. Để sửa file sẵn có: Mở file cần sửa trên web -> nhấn biểu tượng **cây bút (`Edit this file`)** ở góc phải -> thực hiện chỉnh sửa.
  3. Nhấn nút **`Commit changes...`** (màu xanh lá ở góc trên bên phải), nhập ghi chú mô tả thay đổi và nhấn **`Commit changes`**.

### Bước 4: Quy trình khi chỉnh sửa chung một chiến lược (Sử dụng Branch & Pull Request trên Web)
Khi cần thử nghiệm điều kiện mới hoặc sửa đổi lớn trên một code chiến lược đang dùng chung mà không làm ảnh hưởng ngay đến bản gốc trên nhánh `main`:

1. **Tạo nhánh thử nghiệm mới (`Branch`)**:
   - Tại trang chính của kho code, nhấn vào nút chọn nhánh **`main`** (góc trên bên trái).
   - Nhập tên nhánh mới vào ô tìm kiếm (VD: `test-filter-tuan2`) và nhấn **`Create branch: test-filter-tuan2 from 'main'`**.
2. **Chỉnh sửa hoặc tải code lên nhánh mới**:
   - Đảm bảo giao diện web đang hiển thị tên nhánh mới vừa tạo.
   - Thực hiện tải file lên hoặc sửa code tương tự Bước 3, sau đó nhấn **`Commit changes`** (lúc này thay đổi chỉ lưu trên nhánh thử nghiệm, nhánh `main` giữ nguyên).
3. **Tạo yêu cầu gộp code (`Pull Request`)**:
   - Chuyển sang tab **`Pull requests`** trên thanh menu ngang của kho code -> nhấn nút **`New pull request`**.
   - Tại mục `base:`, chọn **`main`**; tại mục `compare:`, chọn **tên nhánh thử nghiệm** vừa sửa -> nhấn **`Create pull request`**.
   - Ghi tóm tắt nội dung thử nghiệm và nhấn **`Create pull request`** để các thành viên khác xem xét. Sau khi thống nhất, nhấn **`Merge pull request`** để cập nhật chính thức vào nhánh `main`.
