# AI Audit Report

Tôi có sử dụng công cụ AI cho các tác vụ sau:

| Ngày giờ | Công cụ | Tác vụ | Prompt | Output của AI |
| --- | --- | --- | --- | --- |
| 02/08/2026 | Antigravity AI | Đánh giá Usability màn hình A1 | "dựa vào html và các ảnh chụp màn hình của A1, hãy phân tích dựa trên các tiêu chí IA01..." | AI đã phân tích tài liệu tĩnh, tạo file `execution_report.md` chứa kết quả đánh giá Pass/Fail cho màn hình A1. |
| 02/08/2026 | Antigravity AI | Trích xuất tiêu chí N/A của A1 | "bây giờ, hãy rà soát lại phần này đối với A1, đối với các tiêu chỉ NA, hãy xác định xem..." | Tạo file `A1_missing_test_requirements.md` phân loại các tiêu chí cần ảnh bổ sung và test tay. |
| 02/08/2026 | Antigravity AI | Đánh giá Usability màn hình A2 | "dựa vào html và các ảnh chụp màn hình của A2, hãy phân tích..." | Cập nhật báo cáo A2 vào `execution_report.md` và tạo file `A2_missing_test_requirements.md`. |
| 02/08/2026 | Antigravity AI | Tổng hợp kết quả test tay A2 | (Người dùng cung cấp kết quả Pass/Fail của A2 cho từng mã IA...) | AI dùng lệnh replace để cập nhật kết quả đè lên các dòng N/A của A2 trong `execution_report.md`. |
| 02/08/2026 | Antigravity AI | Đánh giá Usability màn hình A4 | "tôi đã cung cấp các màn hình cho A4, hãy phân tích... trước khi thực hiện, hãy từ chối nếu không hợp lệ" | AI xác thực màn hình A4, sau đó viết kết quả phân tích A4 vào `execution_report.md`. |
| 02/08/2026 | Antigravity AI | Trích xuất tiêu chí N/A của A4 | "hãy trích xuất luôn danh sách các tiêu chí N/A cần cung cấp thêm..." | Tạo file `A4_missing_test_requirements.md` yêu cầu kiểm thử thủ công cho A4. |
| 02/08/2026 | Antigravity AI | Tổng hợp kết quả test tay A4 | (Người dùng cung cấp kết quả tương tác thủ công đối với màn hình A4...) | AI cập nhật lỗi phát hiện từ test tay vào `execution_report.md` cho màn hình A4. |
| 02/08/2026 | Antigravity AI | Xuất báo cáo Bug và Audit | "hãy đọc lại file và xem có lỗi nào được tim ra không, cập nhật file bug_findings_log.csv... sử dụng skill 04..." | Đọc toàn bộ lỗi Fails, xuất ra file `bug_findings_log.csv` và điền lịch sử AI vào `AI_Audit_Report.md`. |
