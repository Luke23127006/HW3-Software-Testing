# Các tiêu chí cần bổ sung dữ liệu kiểm thử - Kịch bản A4

Dưới đây là danh sách các tiêu chí đánh giá Usability (thuộc IA01 - IA04) cho màn hình **A4 (Participants & Reviews - tab Review Students)** không thể hoàn thành thông qua phân tích tĩnh, do đó yêu cầu phải có thêm dữ liệu ảnh chụp hoặc kịch bản tương tác động để đánh giá.

## 1. Các tiêu chí cần thêm dữ liệu hình ảnh (Visual Evidence)
Đây là các trạng thái thiết kế có thể thuộc phạm vi màn hình A4 nhưng ảnh chụp hiện tại không bao phủ tới:

- **IA01-06 (Empty states):** Cần ảnh chụp giao diện danh sách "Review Students" khi **không có sinh viên nào đăng ký** (hoặc khi tìm kiếm không ra kết quả). Mục đích để kiểm tra xem thông báo trạng thái rỗng có thân thiện và rõ ràng hay không.

## 2. Các tiêu chí cần kiểm thử tương tác thủ công (Manual / Dynamic Testing)
Đây là các tính năng bắt buộc phải thao tác trực tiếp trên môi trường chạy thực tế (trình duyệt) để quan sát luồng xử lý và phản hồi của hệ thống:

- **IA01-07 (Loading states):**
  - *Hành động:* Bật chế độ mạng chậm (Slow 3G) và tải lại trang, hoặc chuyển đổi giữa các tab "Review Lecturers" và "Review Students".
  - *Kiểm chứng:* Hệ thống có hiển thị spinner hoặc skeleton loading tại khu vực bảng dữ liệu trong lúc chờ tải không, hay bị treo trắng trang.
- **IA01-08 & IA01-09 (i18n EN/VI):**
  - *Hành động:* Sử dụng nút chuyển đổi ngôn ngữ (icon lá cờ) trên Header để chuyển qua Tiếng Việt.
  - *Kiểm chứng:* Định dạng ngày tháng tại cột "REGISTERED AT" có thay đổi phù hợp không. Bố cục bảng và các nút bấm có bị vỡ chữ hay không.
- **IA02-10 (Bấm phím Enter tìm kiếm):**
  - *Hành động:* Nhập nội dung vào ô "Search by name, email, member code..." và nhấn phím `Enter`.
  - *Kiểm chứng:* Hệ thống có thực hiện tìm kiếm ngay lập tức (hoặc tự động tìm kiếm trong lúc gõ) mà không bắt buộc dùng chuột bấm tìm không.
- **IA02-12 (Keyboard Accessibility):**
  - *Hành động:* Dùng phím `Tab`, `Space`, `Enter` để di chuyển qua các nút tác vụ trên từng dòng (Reject, Pending Review, Approved) và ô nhập "Add note...".
  - *Kiểm chứng:* Đảm bảo có thể thực hiện việc đánh giá sinh viên hoàn toàn bằng bàn phím một cách trơn tru.
- **IA03-07 (Deep-links):**
  - *Hành động:* Copy URL hiện tại và dán vào tab ẩn danh, hoặc sửa đổi ID trên URL thành một mã không tồn tại.
  - *Kiểm chứng:* Hệ thống điều hướng đúng (hoặc bắt login nếu chưa đăng nhập), báo lỗi 404 thân thiện nếu ID sai.
- **IA03-13 (Browser Back Button):**
  - *Hành động:* Chọn trạng thái "Approved" cho một vài sinh viên, sau đó bấm phím Back của trình duyệt rồi bấm Forward trở lại.
  - *Kiểm chứng:* Trạng thái công việc đang làm dở có bị reset hay không.
- **IA04-03 (Confirmation dialogs - Thao tác phá hủy/rủi ro):**
  - *Hành động:* Bấm vào nút "Reject" (của 1 sinh viên) hoặc nút "Reject All" / "Cancel All".
  - *Kiểm chứng:* Phải hiển thị hộp thoại xác nhận (Confirmation Dialog) với cảnh báo rõ ràng trước khi thực thi hành động từ chối. Nút đồng ý trong hộp thoại phải dùng màu cảnh báo (đỏ).
- **IA04-04 & IA04-12 (Toasts feedback):**
  - *Hành động:* Bấm nút "Apply" để lưu kết quả đánh giá (Approved/Rejected).
  - *Kiểm chứng:* Phải hiện Toast thông báo thành công ở góc màn hình. Toast phải tự biến mất sau khoảng 5 giây và nội dung có thể đọc được bằng Screen reader.
- **IA04-11 (Lỗi kết nối máy chủ - Offline):**
  - *Hành động:* Ngắt kết nối mạng của thiết bị rồi bấm "Apply" hoặc "Approve All".
  - *Kiểm chứng:* Hệ thống báo lỗi mất kết nối thân thiện, không báo mã lỗi kỹ thuật khó hiểu (như "failed to fetch").
- **IA04-06 (Important update flag):**
  - *Hành động:* Bấm vào nút "Important Update" màu vàng trên góc phải.
  - *Kiểm chứng:* Kiểm tra xem cờ cập nhật quan trọng này hoạt động như thế nào, nó có sinh ra cảnh báo gì đặc biệt tới danh sách sinh viên hay không.
