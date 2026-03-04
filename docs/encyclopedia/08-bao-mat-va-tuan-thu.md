# 08. Bảo mật và tuân thủ trong RAG

## Phân loại dữ liệu
- Public, Internal, Confidential, Restricted.
- Mỗi mức dữ liệu cần policy truy cập và retention riêng.

## Kiểm soát truy cập
- Áp dụng RBAC/ABAC cho tài liệu và API truy vấn.
- Lọc kết quả retrieval theo quyền người dùng trước khi prompt.
- Tách tenant rõ ràng trong kiến trúc multi-tenant.

## Bảo vệ dữ liệu nhạy cảm
- Dò tìm và gắn nhãn PII trước khi index.
- Mã hóa dữ liệu at-rest và in-transit.
- Redaction hoặc tokenization thông tin nhạy cảm.

## Tuân thủ và kiểm toán
- Lưu audit log: ai truy cập gì, khi nào, mục đích nào.
- Định kỳ rà soát quyền truy cập và dữ liệu lưu trữ.
- Hỗ trợ quy trình xóa dữ liệu theo yêu cầu pháp lý.

## Rủi ro cần kiểm soát
- Prompt injection từ nguồn dữ liệu không tin cậy.
- Data exfiltration qua câu trả lời của mô hình.
- Leakage giữa các tenant do filter thiếu chặt.
