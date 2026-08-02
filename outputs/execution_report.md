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

---

# Phân tích màn hình A2_add_edit_event (Add/Edit Event Form)

Dựa trên HTML (`page.html`) và các ảnh chụp màn hình cho kịch bản A2 (Form tạo sự kiện), dưới đây là kết quả phân tích theo các tiêu chí IA01, IA02, IA03 và IA04:

## IA-01 — General UI Standards

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA01-01** | Pass | Form có layout phân cấp card tốt. Các khối (Thumbnail, Basic Information...) được nhóm bằng khung viền bo tròn, đệm lót (padding) nhất quán. |
| **IA01-02** | Pass | Các icon ở Sidebar và các icon tiện ích (upload ảnh, tệp tin) đều đồng nhất về kích thước (24x24 hoặc 48x48) và độ dày nét vẽ (stroke-width="2"). |
| **IA01-03** | Pass | Nút Call-to-action chính "Publish" sử dụng màu xanh lơ (cyan) làm nổi bật, trong khi nút "Save as Draft" hoặc "Preview Event" chỉ có viền màu. Phân cấp nút rõ ràng. |
| **IA01-04** | Pass | Tiêu đề các vùng (Section headers như "Basic Information", "Location & Organization") được phân biệt rõ với nhãn trường (Field labels như "Event Title *") bằng kích thước font và độ đậm (`text-lg font-semibold` vs `text-sm font-medium`). |
| **IA01-05** | N/A | Người dùng báo cáo hệ thống không hiển thị thẻ trạng thái trên form này (kể cả ở màn hình Edit). |
| **IA01-06** | N/A | Empty states không áp dụng cho cấu trúc của Form tạo mới. |
| **IA01-07** | Pass | Hệ thống có hiển thị spinner ngay tại nút bấm trong lúc chờ tải (đã kiểm chứng thủ công). |
| **IA01-08** | Pass | Tính năng chuyển đổi ngôn ngữ EN/VI hoạt động bình thường, layout ổn định. |
| **IA01-09** | Pass | Định dạng ngày tháng thay đổi tự động và bình thường theo locale ngôn ngữ. |
| **IA01-10** | N/A | Hero Banner chỉ áp dụng cho trang chủ Public. |
| **IA01-11** | N/A | Tính năng mã QR chỉ áp dụng ở màn hình Check-in. |
| **IA01-12** | Pass | Mã nguồn HTML có ghi nhận các lớp CSS xử lý focus (`data-[focus-visible=true]:outline-focus`) cho input, đảm bảo nhận diện khi Tab. |
| **IA01-13** | Pass | Logo ở thanh bên và các ảnh chức năng có thuộc tính `alt` hoặc dùng `aria-hidden="true"` đối với ảnh trang trí. |

## IA-02 — Forms

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA02-01** | **Fail** | Dấu hoa thị `*` hiển thị trực quan ở nhãn (VD: `Event Title *`, `Campus *`), tuy nhiên thẻ `<input>` trong HTML hoàn toàn thiếu thuộc tính `required` hoặc `aria-required`. Trình đọc màn hình (Screen reader) sẽ không biết đây là trường bắt buộc. |
| **IA02-02** | Pass | Nhãn trường (Label) nằm độc lập phía trên input, không bị biến mất khi người dùng nhập liệu (không lạm dụng placeholder). |
| **IA02-03** | **Fail** | Khu vực Upload thiếu các thông tin quan trọng trước khi tải file: "Thumbnail" / "Banner" chỉ ghi tỉ lệ (ratio) mà không ghi định dạng file (JPG/PNG) hay giới hạn dung lượng (MB). Khu vực "Attachments" có ghi "Supported any file format" nhưng vẫn bỏ ngỏ giới hạn dung lượng và số lượng file. |
| **IA02-04** | Pass | Hệ thống giới hạn chặt ngay từ hộp thoại chọn file của OS (chỉ cho phép chọn ảnh). |
| **IA02-05** | **Fail** | Trình soạn thảo văn bản Rich-text Editor có một loạt các nút bấm chỉ chứa icon (Bold, Italic...), tuy nhiên HTML hoàn toàn không có thuộc tính `title` hay `aria-label` để cung cấp tooltip/chú thích chức năng cho các nút này. |
| **IA02-06** | Pass | Bắt lỗi ngày giờ không hợp lệ bình thường, hiển thị thông báo lỗi ngay tại trường vi phạm (dù không tự cuộn trang đến đó). |
| **IA02-07** | **Fail** | Mục "Additional Options" có công tắc (toggle switch) "Allow Additional Role" nhưng hoàn toàn **thiếu đoạn text mô tả/hướng dẫn (helper text)** bên dưới để giải thích chức năng theo yêu cầu của Checklist. |
| **IA02-08** | Pass | Bắt lỗi để trống trường bắt buộc, hiển thị lỗi trực tiếp tại ô input. |
| **IA02-09** | Pass | Hệ thống ép nhập và ngăn chặn submit khi thiếu trường bắt buộc. |
| **IA02-10** | **Fail** | Tính năng submit bằng phím Enter không hoạt động, người dùng bắt buộc phải dùng chuột bấm nút "Publish". |
| **IA02-11** | **Fail** | Dù hiển thị đúng ngày giờ hiện tại, nhưng bộ chọn (Date picker) chỉ cho click chuột, không cho phép gõ phím trực tiếp (type) gây ảnh hưởng tới Accessibility. |
| **IA02-12** | Pass | Thao tác điều hướng bằng phím (Keyboard Navigation) cho nhóm công tắc/dropdown hoạt động tốt và trơn tru. |
| **IA02-13** | Pass | Không hiển thị cảnh báo khi back, NHƯNG hệ thống tự động lưu nháp (auto-save draft) và cho phép phục hồi khi vào lại, đáp ứng tốt tiêu chí ngăn chặn mất dữ liệu (data loss). |
| **IA02-14** | Pass | Định dạng rich-text (đậm, nghiêng...) được bảo toàn bình thường sau khi lưu và tải lại. |
| **IA02-15** | N/A | Việc mapping cấu hình Additional Role tới form B3 cần luồng tham gia sự kiện. |

## IA-03 — Navigation

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA03-01** | Pass | Sidebar hiển thị nổi bật mục "Events Management". |
| **IA03-02** | N/A | Màn hình không có hệ thống Tab. |
| **IA03-03** | Pass | Sidebar có huy hiệu đếm số thông báo pending (VD: số 7 ở Support requests). |
| **IA03-04** | Pass | Phía trên bên trái của form có nút icon "←" (`lucide-arrow-left`) để quay về trang trước. |
| **IA03-05** | N/A | Không có tính năng status filter trên trang tạo form. |
| **IA03-06** | N/A | Phân trang không áp dụng. |
| **IA03-07** | N/A | Deep-links cần thao tác thủ công. |
| **IA03-08** | N/A | Bảng dữ liệu không áp dụng. |
| **IA03-09** | N/A | Bối cảnh header đa tab không áp dụng. |
| **IA03-10** | N/A | Modal / phím ESC không áp dụng (ảnh không có modal). |
| **IA03-11** | N/A | Đây là màn hình cấp 2 (List -> Form), chưa đến cấp 3 để xuất hiện Breadcrumbs. |
| **IA03-12** | N/A | Không có danh sách order (kéo thả) nào trên form. |
| **IA03-13** | N/A | Browser back button không thể kiểm chứng tĩnh. |
| **IA03-14** | N/A | Không thuộc màn hình Support requests. |
| **IA03-15** | N/A | Trải nghiệm duyệt public không áp dụng. |

## IA-04 — Feedback / State

*(Hầu hết tiêu chí của IA-04 đều yêu cầu tương tác hoặc liên quan đến màn hình khác, do đó đối với ảnh tĩnh của màn hình A2 Add/Edit Form, phần lớn là N/A).*

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA04-04 & IA04-12** | **Fail** | Hoàn toàn không có thông báo Toast nào xuất hiện sau khi thao tác submit/save sự kiện thành công. |
| **IA04-11** | **Fail** | Xử lý mất mạng (Offline) kém thân thiện: hệ thống xoay spinner một lúc rồi báo trực tiếp lỗi kỹ thuật "failed to fetch" ra màn hình. |
| **Các tiêu chí IA04 khác** | N/A | Không áp dụng cho giao diện hoặc chưa có đủ bối cảnh kiểm thử (như IA04-01, IA04-02). |

### Kết luận A2
Màn hình A2 đảm bảo tốt tính đồng nhất về nhận diện hình ảnh (UI Standards - IA01) như font chữ phân cấp, icon và màu nút bấm. Tuy nhiên, tồn tại **nhiều lỗi nghiêm trọng về biểu mẫu (Forms - IA02)**:
1. Thiếu cảnh báo dung lượng/định dạng khi upload file (IA02-03).
2. Thiếu thuộc tính trợ năng `required` cho các trường bắt buộc (IA02-01) và `title` cho các nút ở trình soạn thảo Rich-text (IA02-05).
3. Thiếu văn bản hướng dẫn bổ sung cho các công tắc chức năng (IA02-07).

---

# Phân tích màn hình A4_review (Participants & Reviews - Review Students tab)

Dựa trên HTML (`page.html`) và ảnh chụp màn hình cho kịch bản A4 (quản lý người tham gia - tab Review Students), dưới đây là kết quả phân tích theo các tiêu chí kiểm thử UI/UX:

## IA-01 — General UI Standards

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA01-01** | Pass | Bố cục danh sách rõ ràng, khoảng cách dòng (padding/margin) trong bảng được giữ hợp lý. |
| **IA01-02** | Pass | Các icon (sidebar, search, chevron) đồng nhất về kích thước và nét vẽ so với các màn hình khác. |
| **IA01-03** | Pass | Nút Call-to-action chính "Apply" (hoặc "Events Management" đang active ở sidebar) sử dụng màu xanh lơ đặc trưng, các nút phụ sử dụng nền nhạt (như Reject All, Approve All). |
| **IA01-04** | N/A | Không có cấu trúc Form với Section Headers trên giao diện này. |
| **IA01-05** | Pass | Thẻ trạng thái "PUBLISHED" sử dụng nền xanh lá nhạt với chữ xanh lá đậm, đảm bảo độ tương phản (Contrast) tốt cho văn bản. Thẻ "Pending Review" dùng màu vàng cam đậm chữ trắng cũng tương phản tốt. |
| **IA01-06** | Pass | Hệ thống có hiển thị Empty state khi danh sách rỗng (đã xác nhận qua ảnh chụp bổ sung). |
| **IA01-07** | **Fail** | Hoàn toàn không có Loading state (spinner/skeleton) trong lúc chờ tải dữ liệu, bảng chỉ trống trơn gây khó hiểu cho người dùng. |
| **IA01-08** | Pass | Tính năng chuyển ngữ EN/VI hoạt động mượt mà với các nội dung tĩnh. |
| **IA01-09** | Pass | Định dạng locale hoạt động mượt mà (cùng với tính năng i18n). |
| **IA01-10** | N/A | Hero Banner không áp dụng. |
| **IA01-11** | N/A | QR Code không có mặt trên tab Review Students này. |
| **IA01-12** | Pass | Mã nguồn có các class outline focus (đã chứng minh được trên A1/A2). |
| **IA01-13** | Pass | Ảnh đại diện (avatar) của sinh viên có thuộc tính `aria-label="Lam Truong Hoang"`, đảm bảo screen reader có thể đọc tên thay vì bỏ qua, trong khi các text rút gọn bên trong (LTH) nằm trong thẻ nội dung. |

## IA-02 — Forms
*(Giao diện A4 chủ yếu là một data table với các action inline, phần lớn các tiêu chí của Form Validation không áp dụng được trên ảnh tĩnh)*

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA02-10** | Pass | Hệ thống tự động tìm kiếm ngay khi người dùng nhập từ khóa mà không cần nhấn Enter, rất tiện lợi. |
| **IA02-12** | **Fail** | Tính năng điều hướng bằng bàn phím (Keyboard Accessibility) bị lỗi nghiêm trọng: không thể dùng phím để chọn các action quan trọng (Reject, Pending, Approved) cho từng học sinh, dù các vùng khác vẫn tab được. |
| **Các tiêu chí IA02 khác** | N/A | Không áp dụng cho bảng dữ liệu này. |

## IA-03 — Navigation

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA03-01** | Pass | Mục "Events Management" trên Sidebar được highlight nổi bật đúng ngữ cảnh. |
| **IA03-02** | Pass | Chức năng Tabs (Details, Check-in...) hiển thị rõ ràng, tab "Review Students" đang active có màu nền xanh nổi bật và thẻ HTML sử dụng đúng chuẩn `role="tab"` và `aria-selected="true"`. |
| **IA03-03** | Pass | Xuất hiện huy hiệu (dot) thông báo màu đỏ trên các tab "Review Lecturers" và "Review Students", cũng như huy hiệu số đếm "7" ở sidebar Support requests, báo hiệu có mục cần xử lý. |
| **IA03-04** | **Fail** | Có nút mũi tên "←" quay lại nằm ở cạnh tên sự kiện, tuy nhiên kiểm tra HTML cho thấy thẻ `<a>` này chỉ chứa SVG (với `aria-hidden="true"`) mà hoàn toàn **không có `aria-label`** (thiếu tên trợ năng). Screen reader sẽ chỉ đọc là "Link" mà không hiểu chức năng là gì. |
| **IA03-05** | N/A | Tính năng Status filter (Upcoming/Ended) không áp dụng ở bảng Review này. |
| **IA03-06** | Pass | Bảng dữ liệu có phân trang hiển thị label chính xác ("1-3 of 3 results") và đầy đủ dropdown chọn Rows per page cũng như nút điều hướng (giống A1). |
| **IA03-07** | **Fail** | Xử lý Deep-links kém: dán link vào tab ẩn danh bị văng ra trang login. Khi mở link, hệ thống mặc định nhảy về tab đầu tiên và không highlight trạng thái tab, cũng không có trang 404 thân thiện. |
| **IA03-08** | **Fail** | Bảng có các cột dữ liệu ("STUDENT", "REGISTERED AT") nhưng **hoàn toàn không có chức năng Sorting (sắp xếp)**. Theo chuẩn Checklist, việc thiếu vắng hoàn toàn tính năng sắp xếp trên các danh sách dữ liệu dài là một lỗi về Usability. |
| **IA03-09** | Pass | Tên sự kiện ("Machine Learning Hands-On Workshop") luôn được ghim cố định ở Header khi chuyển qua các sub-tab, giúp Admin không bị quên ngữ cảnh đang xử lý cho sự kiện nào. |
| **IA03-10** | N/A | Modal / phím ESC không áp dụng. |
| **IA03-11** | **Fail** | Màn hình này nằm ở cấp bậc thứ 3 trong kiến trúc thông tin (Events list -> Event Detail -> Review Students tab), tuy nhiên **hệ thống không cung cấp Breadcrumbs** nào để người dùng có thể nhảy vọt về các cấp tổ tiên ngoài nút Back 1 cấp. Đây là một điểm trừ lớn về định vị. |
| **IA03-13** | **Fail** | Nút Browser Back Button gây mất dữ liệu (reset trạng thái) khi thao tác, không lưu lại ngữ cảnh dở dang. |

## IA-04 — Feedback / State

| Item ID | Trạng thái | Notes / Phân tích chi tiết |
| :--- | :--- | :--- |
| **IA04-01** | Pass | Màu sắc trạng thái gán rất chuẩn: "PUBLISHED" (màu xanh dương nhạt/lục nhạt mang tính ổn định), "Pending Review" (màu cam vàng mang ý nghĩa chờ xử lý/cần chú ý). |
| **IA04-03** | Pass | Hệ thống có hiển thị Confirmation dialog sau khi người dùng chọn action và nhấn nút Apply. |
| **IA04-04 & IA04-12** | **Fail** | Hoàn toàn không có thông báo Toast (feedback) nào hiển thị sau khi thực hiện thao tác thành công. |
| **IA04-11** | **Fail** | Khi mất kết nối (Offline), hệ thống không báo lỗi gì và bị kẹt cứng (không thể thao tác chuyển tab). |
| **Các tiêu chí IA04 khác** | N/A | Không áp dụng cho giao diện này. |

### Kết luận A4
Màn hình A4 (Participants & Reviews) làm rất tốt ở khâu hiện thị trạng thái thông báo (Pending badges) và thẻ tab rõ ràng. Tuy nhiên, các lỗi về Điều hướng (Navigation - IA-03) lại hiện rõ:
1. Thiếu mất thuộc tính trợ năng (`aria-label`) cho nút Back, gây khó khăn cho người khiếm thị (IA03-04).
2. Hoàn toàn không có khả năng Sắp xếp (Sorting) cho bảng danh sách người đăng ký, vốn rất cần thiết khi sự kiện có hàng trăm sinh viên (IA03-08).
3. Đã đi sâu vào cấp độ 3 của phân cấp trang nhưng lại thiếu Breadcrumbs (IA03-11).
