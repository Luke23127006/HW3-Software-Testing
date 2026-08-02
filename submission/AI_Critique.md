# AI Critique

Trong quá trình thực hiện chuỗi bài tập kiểm thử giao diện và Usability cho hệ thống EMS, AI đã thể hiện rõ những ưu điểm cũng như các mặt hạn chế của mình.

Về mặt tích cực, AI tỏ ra cực kỳ xuất sắc trong việc rà soát và phát hiện các vấn đề UI một cách rất chi tiết. Ví dụ, AI đã dễ dàng chỉ ra việc hệ thống thiếu các tính năng cơ bản nhưng dễ bị bỏ sót như chức năng sort trên các bảng dữ liệu, hay chủ động đề xuất việc bổ sung breadcrumb để cải thiện luồng điều hướng cho người dùng. Khả năng đối chiếu tự động với các tiêu chuẩn quốc tế như WCAG hay các heuristic của Nielsen giúp ích rất nhiều trong việc hình thành những đánh giá khách quan.

Tuy nhiên, trong quá trình cộng tác, tôi nhận thấy sự phụ thuộc hoàn toàn vào AI có thể dẫn đến một số rủi ro. Điểm yếu dễ thấy nhất là hiện tượng hallucination trong việc sinh tài liệu. Khi phân tích ảnh chụp màn hình tĩnh, AI thỉnh thoảng tự suy diễn các trạng thái không có thực, hoặc giả định sai về luồng tương tác thực tế. Do đó, nguyên tắc cộng tác cốt lõi được rút ra là: con người phải luôn giữ vai trò người kiểm duyệt cuối cùng; mọi tài liệu AI sinh ra đều bắt buộc phải được đối chiếu lại với trải nghiệm thực tế trên hệ thống và chỉnh sửa kỹ lưỡng trước khi sử dụng.

Bên cạnh đó, vì AI luôn cố gắng tỏ ra hữu ích tối đa nên nó thường cung cấp lượng thông tin quá mức cần thiết. Sự chi tiết này đôi khi dẫn đến một chút sự dư thừa nhẹ – thay vì đi thẳng vào kết quả phân tích hay đánh giá Pass/Fail, AI lại dành quá nhiều dung lượng để giải thích lại các nguyên lý thiết kế chung chung. Điều này đòi hỏi người sử dụng phải có prompt tốt, đưa ra những ràng buộc rõ ràng để biến AI từ một cỗ máy sinh chữ thành một trợ lý kiểm thử thực sự có kỷ luật và đi thẳng vào trọng tâm.
