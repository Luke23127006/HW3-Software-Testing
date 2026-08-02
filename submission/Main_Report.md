# Báo cáo chính

## 1. Kịch bản và màn hình
- Kịch bản đã chọn: **A — Admin creates and manages events**
- Màn hình 1: **A1 (Events list)** - Lý do chọn: Bao quát luồng xem danh sách tổng tổng quan, chứa các bộ lọc (filter), chấm thông báo (notification dots) và điều hướng chính của Admin.
- Màn hình 2: **A2 (Add/Edit Event form)** - Lý do chọn: Đây là form nhập liệu phức tạp nhất, chứa upload ảnh (4:3, 24:9), Rich-Text editor và validation ngày/giờ, bao phủ phần lớn các tiêu chí về Forms (IA-02).
- Màn hình 3: **A4 (Participants & Reviews)** - Lý do chọn: Có các thanh trạng thái tiến độ (progress bar), chức năng Export ra Excel và xử lý dữ liệu người dùng, phục vụ tốt cho việc đánh giá Feedback / State (IA-04).

## 2. Kết quả chạy Checklist
- Màn hình A1: Pass [X]/[Y], Fail [Z]/[Y]
- Màn hình A2: Pass [X]/[Y], Fail [Z]/[Y]
- Màn hình A4: Pass [X]/[Y], Fail [Z]/[Y]

*(Ghi chú: Thay [X], [Y], [Z] bằng số liệu thực tế sau khi hoàn thành bảng trong Execution_Report.md)*

## 3. Báo cáo Cross-Platform
Ma trận tối giản Cross-Browser / Cross-Platform (5 Test Cases đáp ứng đủ độ phủ yêu cầu: 3 OS × 5 Browser × 3 Thiết bị).

- Hệ điều hành đã thử: Windows, macOS, iOS, Android
- Browser đã thử: Chrome, Safari, Firefox, Edge, Opera (hoặc Samsung Internet)
- Thiết bị đã thử: Desktop, Tablet, Phone

| Test Case | Thiết bị (Device) | Hệ điều hành (OS) | Trình duyệt (Browser) | Mục tiêu phủ (Coverage) | Màn hình | Pass/Fail | Ghi chú lỗi | Link ảnh |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| TC1 | Desktop (PC) | Windows 11 | Chrome | Phủ: Desktop, Windows, Chrome | A1, A2, A4 | Pass | Bình thường | [windows_chrome.png](./screenshots_gui/task3/windows_chrome.png) |
| TC2 | Desktop (Mac) | macOS (Sonoma) | Safari | Phủ: macOS, Safari | A1, A2, A4 | Pass | Bình thường | [macos_safari.png](./screenshots_gui/task3/macos_safari.png) |
| TC3 | Desktop (PC) | Windows 11 | Edge | Phủ: Edge | A1, A2, A4 | Pass | Bình thường | [windows_edge.png](./screenshots_gui/task3/windows_edge.png) |
| TC4 | Tablet (iPad) | iOS/iPadOS | Firefox | Phủ: Tablet, iOS, Firefox | A1, A2, A4 | Pass | Bình thường | [ipad_firefox.png](./screenshots_gui/task3/ipad_firefox.png) |
| TC5 | Phone (Samsung/Pixel) | Android | Opera (hoặc Samsung Internet) | Phủ: Phone, Android, Opera | A1, A2, A4 | Fail | UI vỡ hoàn toàn, rất khó đăng nhập | [phone_opera.png](./screenshots_gui/task3/phone_opera.png) |

## 4. Các báo cáo khác
- [Usability Report](./Usability_Report.md)
- [Bug & Usability Findings](./Bug_Usability_Findings.md)
- [Execution Report (Chi tiết Checklist)](./Execution_Report.md)
- [AI Audit Report](./AI_Audit_Report.md)
