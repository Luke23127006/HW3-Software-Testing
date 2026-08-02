# Các tiêu chí cần bổ sung dữ liệu kiểm thử - Kịch bản A2

Dưới đây là danh sách các tiêu chí đánh giá Usability (thuộc IA01 - IA04) cho màn hình **A2 (Add/Edit Event Form)** không thể hoàn thành thông qua phân tích tĩnh, do đó yêu cầu phải có thêm dữ liệu ảnh chụp hoặc kịch bản tương tác động để đánh giá.

## 1. Các tiêu chí cần thêm dữ liệu hình ảnh (Visual Evidence)
Đây là các trạng thái thiết kế có thể thuộc phạm vi màn hình A2 nhưng ảnh chụp (chỉ chứa trạng thái Create Event) hiện tại không bao phủ tới:

- **IA01-05 (Status pill - Nhãn trạng thái):** Cần ảnh chụp giao diện Form ở trạng thái **Chỉnh sửa (Edit Event)** của một sự kiện đã tạo, để kiểm tra xem hệ thống có hiển thị thẻ trạng thái (ví dụ: Published, Draft) ở vị trí nào đó trên form không, từ đó mới đánh giá được độ tương phản màu sắc.

## 2. Các tiêu chí cần kiểm thử tương tác thủ công (Manual / Dynamic Testing)
Đây là các tính năng bắt buộc phải thao tác trực tiếp trên môi trường chạy thực tế (trình duyệt) để quan sát luồng xử lý và phản hồi (Validation/Feedback) của form:

- **IA01-07 (Loading states):** 
  - *Hành động:* Mô phỏng mạng chậm (Slow 3G) và tải lại form, hoặc bấm nút "Publish".
  - *Kiểm chứng:* Giao diện có bị vô hiệu hóa (disabled) các ô input và hiện spinner chờ hay không.
- **IA01-08 & IA01-09 (i18n EN/VI):**
  - *Hành động:* Bấm vào icon cờ trên Header để chuyển đổi qua lại giữa tiếng Việt/Anh.
  - *Kiểm chứng:* Đảm bảo layout các nhãn (label) không bị vỡ. Định dạng placeholder ngày tháng ở phần Date & Time thay đổi theo locale phù hợp.
- **IA02-04 (File validation):**
  - *Hành động:* Cố tình đính kèm tệp tin không được phép (VD: file `.pdf` vào vùng Thumbnail) hoặc file dung lượng cực lớn (>5MB).
  - *Kiểm chứng:* Form từ chối lập tức, hiển thị thông báo lỗi rõ ràng nêu đích danh tên file vi phạm.
- **IA02-06 (Date validation):**
  - *Hành động:* Cố tình cài đặt "End Date & Time" diễn ra **trước** "Start Date & Time".
  - *Kiểm chứng:* Input báo lỗi đỏ inline ngay lập tức, không cho phép lưu cấu hình phi logic.
- **IA02-08 & IA02-09 (Required field validation):**
  - *Hành động:* Để trống các trường bắt buộc (Event Title, Campus) và trực tiếp bấm "Publish" hoặc "Save as Draft".
  - *Kiểm chứng:* Hệ thống ngăn chặn submit, hiển thị viền đỏ và dòng thông báo lỗi cụ thể (inline error) dưới chính trường bị bỏ trống đó.
- **IA02-10 (Bấm phím Enter để Submit):**
  - *Hành động:* Đứng ở ô input dạng text cuối cùng của form và nhấn phím `Enter`.
  - *Kiểm chứng:* Hệ thống tự động kích hoạt hành động "Publish".
- **IA02-11 (Date control navigation):**
  - *Hành động:* Dùng bàn phím tương tác với bộ chọn ngày tháng (Date & Time Picker).
  - *Kiểm chứng:* Kiểm tra ngày mặc định khi popup mở lên (có phải là ngày hiện tại hay không) và việc người dùng có thể nhập chữ trực tiếp từ bàn phím thay vì bấm chuột hay không.
- **IA02-12 (Keyboard Accessibility):**
  - *Hành động:* Dùng phím `Tab`, `Space`, `Enter` để tương tác với nhóm công tắc (Toggles) trong phần Additional Options/Registration và phần Categories.
  - *Kiểm chứng:* Có thể gạt bật/tắt công tắc và mở dropdown một cách trơn tru hoàn toàn bằng bàn phím.
- **IA02-13 (Cảnh báo Unsaved Warning):**
  - *Hành động:* Nhập thông tin vài ô trên form, sau đó bấm nút "← Back" hoặc phím back của trình duyệt.
  - *Kiểm chứng:* Phải xuất hiện Dialog cảnh báo mất dữ liệu (data loss) trước khi cho phép rời trang.
- **IA02-14 (Rich-text persistence):**
  - *Hành động:* Nhập nội dung Content, áp dụng định dạng đậm/nghiêng/list, bấm lưu, rồi tải lại trang.
  - *Kiểm chứng:* Toàn bộ định dạng cấu trúc nội dung được lưu trữ và tải lại chính xác, không sinh ra các thẻ HTML thô.
- **IA02-15 (Mapping cấu hình B3):**
  - *Hành động:* Bật công tắc "Allow Additional Role" và lưu. Sau đó đóng vai là sinh viên để mở form đăng ký sự kiện đó.
  - *Kiểm chứng:* Form phía người tham gia phải hiển thị trường chọn vai trò phụ (đáp ứng đúng theo cấu hình của Admin).
- **IA04-04 & IA04-12 (Toasts feedback):**
  - *Hành động:* Lưu/Publish sự kiện thành công.
  - *Kiểm chứng:* Thông báo Toast thành công hiện ra ở góc phải, giữ đủ 5 giây, có thể đọc qua Screen reader.
- **IA04-11 (Offline error):**
  - *Hành động:* Ngắt kết nối mạng ngay trước khi bấm "Publish".
  - *Kiểm chứng:* Form không bị kẹt cứng mà hiển thị thông báo "Vui lòng kiểm tra lại kết nối".
