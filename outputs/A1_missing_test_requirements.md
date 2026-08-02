# Các tiêu chí cần bổ sung dữ liệu kiểm thử - Kịch bản A1

Dưới đây là danh sách các tiêu chí đánh giá Usability (thuộc IA01 - IA04) cho màn hình **A1 (Events list)** không thể hoàn thành thông qua phân tích tĩnh, do đó yêu cầu phải có thêm dữ liệu hoặc kịch bản tương tác động để đánh giá.

## 1. Các tiêu chí cần thêm dữ liệu hình ảnh (Visual Evidence)
Đây là các trạng thái thiết kế có thể thuộc phạm vi màn hình A1, nhưng bộ ảnh chụp (screenshots) hiện tại không bao phủ tới. Cần yêu cầu Designer hoặc PO cung cấp thêm mockup/ảnh chụp cho:

- **IA01-06 (Empty states):** Cần ảnh chụp giao diện danh sách sự kiện khi không có kết quả nào (do tìm kiếm không khớp hoặc hệ thống rỗng). Yêu cầu xem thông báo trạng thái trống có thân thiện và rõ ràng hay không.
- **IA04-06 (Important Update flag):** Cần ảnh chụp một dòng sự kiện có chứa cờ báo "Important Update" (nếu có hỗ trợ hiển thị ở màn hình danh sách) để đảm bảo không bị trùng lặp hoặc mâu thuẫn về màu sắc với các nhãn trạng thái (Status badge) bình thường.

## 2. Các tiêu chí cần kiểm thử tương tác thủ công (Manual / Dynamic Testing)
Đây là các tính năng đã hiện diện trên mã HTML của màn hình A1, nhưng bắt buộc phải thao tác trực tiếp trên môi trường chạy thực tế (trình duyệt) để quan sát phản hồi của hệ thống:

- **IA01-07 (Loading states):**
  - *Hành động:* Sử dụng DevTools để bật chế độ mạng chậm ("Slow 3G") và tải lại trang.
  - *Kiểm chứng:* Giao diện trong lúc chờ tải dữ liệu có xuất hiện spinner hoặc skeleton loading hợp lý không, hay bị trắng trang.
- **IA01-08 & IA01-09 (i18n EN/VI):**
  - *Hành động:* Bấm vào icon lá cờ trên top bar để chuyển ngôn ngữ sang Tiếng Việt.
  - *Kiểm chứng:* Các dòng văn bản có bị vỡ bố cục (wrap/overflow) không. Định dạng ngày tháng trên danh sách sự kiện có tự động đổi cho phù hợp với ngữ cảnh địa phương không.
- **IA02-10 (Bấm phím Enter tìm kiếm):**
  - *Hành động:* Nhập từ khóa vào ô "Search events..." và trực tiếp nhấn phím `Enter` trên bàn phím.
  - *Kiểm chứng:* Hệ thống tự động thực hiện lệnh tìm kiếm mà không bắt buộc người dùng phải dùng chuột nhấn vào nút "Search".
- **IA02-12 (Điều hướng bằng phím - Keyboard Navigation):**
  - *Hành động:* Dùng phím `Tab`, `Shift + Tab`, phím Space/Enter và các phím mũi tên.
  - *Kiểm chứng:* Đảm bảo có thể di chuyển qua lại, mở/đóng và chọn giá trị trên các dropdown filter ("All Status", "All Time", "Rows per page") một cách trơn tru hoàn toàn bằng bàn phím.
- **IA03-07 (Deep links):**
  - *Hành động:* Cố tình sao chép và dán một URL (có thể chứa query id lỗi hoặc không tồn tại) trực tiếp vào thanh địa chỉ của trình duyệt.
  - *Kiểm chứng:* Hệ thống không bị crash mà điều hướng hoặc hiển thị giao diện báo lỗi 404 thân thiện.
- **IA03-13 (Browser Back/Forward):**
  - *Hành động:* Áp dụng bộ lọc (ví dụ: chỉ hiện sự kiện "Draft"), sau đó bấm vào sự kiện, hoặc qua trang 2, rồi nhấn nút "Back" của trình duyệt.
  - *Kiểm chứng:* Trạng thái lọc "Draft" ở trang A1 phải được duy trì, không bị reset trắng.
- **IA04-03 (Confirmation dialogs - Xóa dữ liệu):**
  - *Hành động:* Bấm vào biểu tượng Thùng rác ở cột "ACTIONS".
  - *Kiểm chứng:* Phải xuất hiện hộp thoại xác nhận (Confirmation Dialog) mang tính cảnh báo nguy hiểm (Ví dụ: "This cannot be undone") trước khi tiến hành xóa.
- **IA04-04 & IA04-12 (Toasts feedback):**
  - *Hành động:* Bấm xóa một sự kiện và xác nhận thành công.
  - *Kiểm chứng:* Thông báo Toast góc màn hình hiện lên rõ ràng, thông báo nội dung thành công và phải tồn tại đủ lâu (ít nhất 5 giây) để người dùng kịp đọc.
- **IA04-11 (Lỗi kết nối máy chủ - Offline):**
  - *Hành động:* Ngắt kết nối mạng của thiết bị hoặc bật chế độ Offline trong DevTools, sau đó bấm chuyển trang (phân trang).
  - *Kiểm chứng:* Hệ thống hiện thông báo lỗi mất kết nối máy chủ một cách nhẹ nhàng, không gây kẹt cứng toàn bộ giao diện.
