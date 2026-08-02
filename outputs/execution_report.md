# Báo cáo thực thi (Execution Report) - Phân tích màn hình A1_event_management

Dựa trên HTML (`page.html`) và 2 ảnh chụp màn hình cung cấp cho kịch bản A1 (Events list), dưới đây là kết quả phân tích theo các tiêu chí IA01 và IA02 từ `Shared_GUI_Checklist.md`:

## IA-01 — General UI Standards

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA01-01** | Pass (1 phần) | Tiêu đề trang "Events" có font chữ lớn (`text-2xl font-bold text-gray-900`) và dấu gạch dưới nhấn mạnh (`mt-1 h-1 w-16 bg-[#1bc2f5]`). Card danh sách thiết kế padding chuẩn, vertical rhythm tốt. (Lưu ý: Không thể so sánh với các trang Users Management / Support requests vì không có dữ liệu). |
| **IA01-02** | Pass | Toàn bộ 9 icon trên sidebar đều đồng bộ vì cùng sử dụng SVG của `lucide` với `width="20" height="20"` và `stroke-width="2"`. Mục đang active (Events Management) được làm nổi bật với màu nền khác biệt. |
| **IA01-03** | Pass | Nút Call-to-action chính "+ Add Event" sử dụng màu xanh lơ (`bg-[#1bc2f5]`), đồng bộ với màu highlight mục đang chọn trên sidebar. Màu này được sử dụng đúng mục đích, không bị lạm dụng làm màu trang trí. |
| **IA01-04** | N/A | Tiêu chí này áp dụng cho form Add/Edit Event, không áp dụng cho màn hình danh sách sự kiện A1. |
| **IA01-05** | Pass | Các thẻ trạng thái (status pill) có độ tương phản tốt: <br> - **Published**: chữ xanh đậm (`text-emerald-700`) trên nền xanh nhạt (`bg-emerald-100`), độ tương phản ~4.6:1.<br> - **Draft**: chữ xám đậm (`text-gray-700`) trên nền xám nhạt (`bg-gray-100`), độ tương phản ~6.9:1. |
| **IA01-06** | **Fail** | Dựa trên ảnh chụp mới (trạng thái tìm kiếm không có kết quả), hệ thống chỉ hiển thị dòng chữ trơn "No events found matching your filters." nằm lệch lạc trong bảng mà không có hình minh họa (illustration) hay được căn giữa toàn bộ không gian như thiết kế Empty State chuẩn mực. |
| **IA01-07** | Pass | Khi giả lập mạng Slow 3G, hệ thống có hiển thị spinner chờ tải dữ liệu hợp lý. |
| **IA01-08** | **Fail** | Đổi ngôn ngữ (EN/VI) chỉ có tác dụng với các nhãn tĩnh (static UI), còn nội dung động trong bảng (gọi từ API) không được dịch sang ngôn ngữ tương ứng. |
| **IA01-09** | **Fail** | Tương tự IA01-08, định dạng ngày tháng của dữ liệu động trong bảng không thay đổi theo ngôn ngữ được chọn. |
| **IA01-10** | N/A | "SPOTLIGHT EVENT" hero banner không tồn tại ở màn hình A1 Admin (chỉ có ở trang chủ phía User). |
| **IA01-11** | N/A | Không có tính năng hiển thị QR Code trên màn hình Events list. |
| **IA01-12** | Pass (HTML) | Không thể bấm Tab thực tế, nhưng đọc trong HTML các elements tương tác (nút, row, table head) đều có cấu hình Tailwind classes cho focus ring như `data-[focus-visible=true]:outline-2` và `data-[focus-visible=true]:outline-focus`. Hệ thống có xử lý focus state đầy đủ. |
| **IA01-13** | Pass | Hình ảnh logo ở sidebar có thuộc tính mô tả đầy đủ: `<img alt="FIT" ... src="/_next/image..." />`. |

### Kết luận IA-01
Giao diện danh sách sự kiện (A1) tuân thủ rất tốt các chuẩn UI chung theo thiết kế (Design System). Các màu sắc nhấn, độ tương phản của status pill và trạng thái đồng nhất của icon sidebar đều pass. Một số tiêu chí phải đánh giá `N/A` do giới hạn của tài liệu tĩnh (không thể tương tác click/tab hoặc không thuộc phạm vi màn hình này).

---

## IA-02 — Forms

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA02-01** | N/A | Tiêu chí yêu cầu kiểm tra đánh dấu trường bắt buộc trên Form Add/Edit Event, Support Request và Edit User. Không áp dụng cho màn hình danh sách sự kiện A1. |
| **IA02-02** | N/A | Kiểm tra label trên Add/Edit Form và Edit User Dialog. Không áp dụng cho A1. |
| **IA02-03** | N/A | Kiểm tra giới hạn upload (Thumbnail, Event Banner). Không có component upload nào ở màn hình A1. |
| **IA02-04** | N/A | Kiểm tra upload file lỗi. Không áp dụng. |
| **IA02-05** | N/A | Kiểm tra tooltip trong Rich-text editor. Màn hình A1 không có Rich-text editor. |
| **IA02-06** | N/A | Kiểm tra ràng buộc Start Date và End Date. Không áp dụng. |
| **IA02-07** | N/A | Kiểm tra các toggle switches trên form Add/Edit Event. Không áp dụng. |
| **IA02-08** | N/A | Submit form khi thiếu thông tin. Không áp dụng. |
| **IA02-09** | N/A | Nút Submit bị disable nếu form không hợp lệ. Không áp dụng. |
| **IA02-10** | Pass | Hệ thống tự động thực hiện tìm kiếm ngay trong lúc người dùng nhập từ khóa mà không cần phải nhấn phím Enter (Live search). Trải nghiệm này trơn tru và thỏa mãn mục tiêu không cần click chuột. |
| **IA02-11** | N/A | Màn hình A1 không chứa Custom Date Controls hoặc Native Date Controls. Lọc thời gian "All Time" là một popup dropdown menu, không phải là date picker truyền thống. |
| **IA02-12** | **Fail** | Phím Tab có thể điều hướng qua các UI tĩnh có sẵn trên màn hình, tuy nhiên **không hoạt động** đối với các lựa chọn bên trong phần dropdown menu. Điều này vi phạm nghiêm trọng tính khả dụng (Accessibility) đối với người dùng sử dụng bàn phím. |
| **IA02-13** | N/A | Thoát form khi chưa lưu dữ liệu. Không áp dụng. |
| **IA02-14** | N/A | Formatting trong rich text editor. Không áp dụng. |
| **IA02-15** | N/A | Mapping cấu hình "Allow Additional Role" ở trang đăng ký. Không áp dụng cho A1. |

### Kết luận IA-02
Do tính chất của màn hình A1 là một danh sách sự kiện chứa thông tin read-only, chỉ bao gồm thanh công cụ (bộ lọc/tìm kiếm) và không phải là một Form điền liệu hoàn chỉnh, phần lớn tiêu chí (13/15 mục) của IA-02 đều mang trạng thái **N/A**. Chỉ có thanh tìm kiếm (search box) và một số dropdown selection controls (lọc trạng thái, lọc thời gian) có mặt trên màn hình và hỗ trợ cấu trúc accessibility cơ bản qua HTML tĩnh.

---

## IA-03 — Navigation

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA03-01** | Pass | Sidebar hiển thị nổi bật mục hiện tại ("Events Management" đổi màu xanh). Nút "Collapse" nằm ở cuối sidebar hiển thị bình thường. DOM có cấu trúc thẻ bọc cho trạng thái gập/mở có thể điều khiển. |
| **IA03-02** | N/A | Không có các nhóm tab Check-in hay Pending/Resolved trên màn hình A1. |
| **IA03-03** | Pass | Mục "Support requests" trên sidebar có hiển thị dấu chấm đỏ báo hiệu với số lượng pending cụ thể ("6" badge màu đỏ `<span class="bg-red-500">6</span>`). |
| **IA03-04** | N/A | Màn hình A1 là danh sách gốc, không phải trang chi tiết (detail page) nên không có nút "← Back". |
| **IA03-05** | N/A | Kiểm tra trạng thái Status filters trên trang sự kiện Public. Màn hình A1 là giao diện Admin nên không áp dụng. |
| **IA03-06** | Pass | Hệ thống có phân trang ở danh sách sự kiện Admin. Nhãn hiển thị đếm số lượng là `1-5 of 49 results`, khớp với thực tế số lượng hàng (rows) đang hiển thị trên màn hình là 5. Bảng có cung cấp đầy đủ: chọn số hàng mỗi trang (`Rows per page: 5`), chuyển đến trang cụ thể ("Go to page [ ] / 10") và các nút điều hướng trang (`< 1 2 ... 10 >`). |
| **IA03-07** | Pass | Thử nghiệm dán URL không hợp lệ (lỗi Deep link) hệ thống xử lý tốt và hiển thị giao diện báo lỗi 404 thân thiện với người dùng. |
| **IA03-08** | **Fail** | Bảng danh sách Event có 18 cột (một phần được hiển thị trong screenshot). Các cột (như `EVENT TYPES`, `TIME`, v.v.) có biểu tượng hình phễu (funnel) để lọc (filter). Tuy nhiên, **hoàn toàn không có tính năng sắp xếp (sorting)** ở bất kỳ cột nào (không tìm thấy mũi tên nào, HTML không chứa thuộc tính `aria-sort`). Việc thiếu chức năng sort trên một bảng lớn là lỗi Usability theo quy định checklist. |
| **IA03-09** | N/A | Kiểm tra tiêu đề header trên các tab chi tiết. Không áp dụng. |
| **IA03-10** | N/A | Không có modal hoặc lightbox nào trên màn hình để kiểm tra phím ESC. |
| **IA03-11** | N/A | Breadcrumb không áp dụng cho danh sách tầng ngoài cùng. |
| **IA03-12** | N/A | Không có danh sách cho phép order (kéo thả) trên giao diện này. |
| **IA03-13** | **Fail** | Khi điều hướng bằng nút Back/Forward của trình duyệt, trạng thái của các bộ lọc (filter state) **không được duy trì**. Người dùng sẽ mất trạng thái tìm kiếm hiện tại. |
| **IA03-14** | N/A | Lọc search + category trên danh sách Support Requests. Không áp dụng. |
| **IA03-15** | N/A | Trải nghiệm duyệt sự kiện trên trang chủ (Public). Không áp dụng. |

### Kết luận IA-03
Màn hình A1 đáp ứng tốt hầu hết các chỉ tiêu về Navigation (Sidebar rõ ràng, có bộ đếm pending, phân trang đầy đủ). Đáng chú ý là phát hiện ra một **lỗi Usability** tương ứng với tiêu chí **IA03-08 (Fail)**: Bảng sự kiện có 18 cột dữ liệu rất rộng nhưng hoàn toàn không hỗ trợ tính năng Sắp xếp (Sorting) ở bất kỳ header nào, chỉ hỗ trợ Lọc (Filtering). Việc thiếu sót này sẽ gây nhiều bất tiện cho admin khi tìm kiếm và duyệt sự kiện theo thời gian hoặc trạng thái.

---

## IA-04 — Feedback / State

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA04-01** | Pass | Các nhãn trạng thái (badges/pills) tuân thủ hệ thống màu quy định: "Published" màu xanh ngọc (tích cực/hoàn thành), "Draft" màu xám, "Upcoming" màu tím nhạt. Việc map ý nghĩa trạng thái sang màu sắc hợp lý và trực quan. |
| **IA04-02** | N/A | Không có dialog (ví dụ Modal Edit User) trên màn hình A1 để kiểm tra nền tối (dimmed) hoặc tương tác phía sau lớp nền. |
| **IA04-03** | Pass | Bảng có cột ACTIONS với biểu tượng hình thùng rác (xóa event). Khi nhấn vào, hệ thống **có xuất hiện** hộp thoại cảnh báo (Confirmation Dialog) đúng chuẩn để tránh xóa nhầm. |
| **IA04-04** | **Fail** | Sau khi xác nhận xóa dữ liệu thành công, hệ thống **không hiển thị** bất kỳ thông báo Toast nào để phản hồi trạng thái với người dùng. |
| **IA04-05** | N/A | Real-time update của các slot counter khi đăng ký. Không áp dụng. |
| **IA04-06** | N/A | Phía Admin có tính năng gửi "Important Update" đến người tham gia, tuy nhiên cờ báo (flag) này lại không hiển thị trực tiếp trên danh sách sự kiện A1 nên không thể đánh giá độ tương tác màu sắc trên màn hình này. |
| **IA04-07** | N/A | Tương quan số lượng Pending/Resolved card và dữ liệu bảng. Không áp dụng (chỉ dành cho trang Support requests). |
| **IA04-08** | N/A | Banner cảnh báo (màu hổ phách - amber). Không có trường hợp này trên ảnh tĩnh. |
| **IA04-09** | N/A | Phản hồi khi check-in bằng mã QR. Không áp dụng. |
| **IA04-10** | **Fail** | Bảng danh sách hiển thị sức chứa (capacity) ở cột "LECTURERS" (VD: `0 / 1`) và "STUDENTS" (VD: `16 / 100`) dưới dạng **Văn bản trơn (Text-only)** mà không cung cấp thanh tiến trình (Progress Bar / Bar meters). Theo Checklist, việc bắt người dùng phải tự nhẩm tính tỷ lệ sức chứa từ một chuỗi "A / B" là một **lỗi Usability** (Thiếu tính trực quan). Cần bổ sung thanh Bar hiển thị độ đầy. |
| **IA04-11** | **Fail** | Xử lý lỗi mất mạng rất kém: Giao diện không load được trang và hiển thị lỗi kỹ thuật khó hiểu cho người dùng cuối ("Application error: a client-side exception has occurred..."). |
| **IA04-12** | **Fail** | Do hệ thống không hiển thị Toast (phát hiện ở IA04-04) nên vi phạm luôn yêu cầu cơ bản về Accessibility cho Toast (thời gian hiển thị và aria-live). |
| **IA04-13** | N/A | Tính năng xuất Excel (Export to Excel) không xuất hiện trên giao diện A1 theo mô tả checklist (chỉ áp dụng ở Registrants tab). |
| **IA04-14** | N/A | Ranh giới ghi chú nội bộ (internal note) và phản hồi chính thức (official response). Không áp dụng. |
| **IA04-15** | N/A | Trạng thái đồng nhất giữa Requester (D2) và Admin (D3/D4). Không áp dụng. |
| **IA04-16** | N/A | Trải nghiệm đăng ký vào Waitlist. Không áp dụng. |
| **IA04-17** | N/A | Lỗi hiển thị dữ liệu cũ (stale data) khi thay đổi URL ID. Không thể kiểm thử. |

### Kết luận IA-04
Chỉ một số ít tiêu chí về Feedback/State có thể quan sát được trên màn hình danh sách sự kiện A1 do hạn chế của ảnh tĩnh:
- **Điểm sáng**: Màu sắc của các trạng thái Event (Published, Draft...) được gán đúng theo ý nghĩa. Các action phá hủy có sẵn màu báo động.
- **Điểm yếu (Fail - Usability)**: Ở cột LECTURERS và STUDENTS (ảnh Screenshot 2), dung lượng người đăng ký chỉ được hiển thị dưới dạng chữ (VD: `16 / 100`), buộc người quản trị phải tự tính nhẩm tỷ lệ lấp đầy. Hệ thống bắt buộc nên sử dụng thanh ProgressBar (thanh phần trăm) để nâng cao độ trực quan theo yêu cầu của tiêu chí **IA04-10**.
