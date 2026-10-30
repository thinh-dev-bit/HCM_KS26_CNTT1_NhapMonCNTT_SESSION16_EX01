# 1. Báo cáo phân tích:

**Sơ đồ luồng dữ liệu (Từ Máy tính lên Đám mây):**
Giải pháp Hybrid Workflow (Làm việc lai) giúp Designer không bao giờ mất file, hoạt động theo 3 nhịp đơn giản:
1. **Làm trên máy:** Thiết kế 3D trên ổ cứng máy tính để tận dụng tốc độ cao, không bị giật lag hay phụ thuộc mạng.
2. **Lưu file:** Ngay khi bấm lưu, phần mềm (Google Drive/OneDrive) sẽ tự động bắt lấy phần thay đổi và đẩy ngầm lên Đám mây.
3. **Sao lưu an toàn:** File 3D nằm an toàn trên máy chủ đám mây. Dù ổ cứng máy tính có hỏng, thì chỉ cần đợi máy sửa lại hoặc dùng máy khác để truy cập drive là có thể truy cập lại được

**Cách hệ thống xử lý khi có xung đột phiên bản (File Version Conflict):**

Khi nhiều người cùng sửa một file và lưu cùng lúc, hệ thống sẽ bảo vệ dữ liệu theo 3 cơ chế sau:

1. **Tạo "Bản sao xung đột" (Với file nặng/offline như 3D, Video, PTS)**
* Hệ thống **tuyệt đối không ghi đè** để tránh làm mất công sức của người khác.
* Bản lưu sau sẽ được hệ thống giữ nguyên và tạo thành một file phụ có tên chứa thông tin người lưu (VD: `TenFile (Bản sao xung đột của A).ext`). Nhóm sẽ tự đối chiếu 2 file và gộp thủ công.

2. **Hợp nhất tự động (Với file trực tuyến như Google Docs, Sheets)**
* Ứng dụng **Đồng bộ vi sai (Delta Sync)** để gộp các đoạn thay đổi theo thời gian thực.
* Nếu A sửa dòng 1, B sửa dòng 10, hệ thống sẽ tự động ghép cả hai vào cùng một file duy nhất mà không sinh ra file rác.

3. **Khôi phục bằng Version History (Lịch sử phiên bản)**
* Đây là phao cứu sinh khi một người lỡ tay lưu đè hoặc xóa nhầm dữ liệu của người khác.
* **Cách xử lý:** Mở **Version History** ➔ Tìm lại mốc thời gian (Timestamp) trước khi bị lỗi ➔ Bấm **Restore (Khôi phục)** để lấy lại bản hoàn chỉnh

# 2. Quy trình 3 bước thiết lập chuẩn cho Designer

Để bạn A không lặp lại sai lầm cũ, hãy áp dụng đúng 3 bước sau:

* **Bước 1: Cài đặt Cloud & Đổi chỗ lưu file**
  Cài phần mềm Google Drive for Desktop vào máy. Thay vì lưu file lung tung ngoài Desktop, hãy chuyển toàn bộ thư mục thiết kế 3D vào ổ đĩa ảo của Google Drive.
* **Bước 2: Bật tính năng Tiết kiệm ổ cứng (Files On-Demand)**
  Bật tính năng này để các file cũ, ít dùng chỉ lưu trên mây, không chiếm dụng bộ nhớ ổ SSD của máy tính. Khi nào cần mở mới click vào để tải xuống.
* **Bước 3: Tạo thói quen "Lưu và Chờ tích xanh"**
  Luôn mở file từ thư mục đồng bộ này. Thường xuyên bấm `Ctrl + S` khi làm việc, và luôn nhớ quy tắc: Chờ thư mục báo tích xanh rồi mới tắt máy.