# 11. Query Transformation trong RAG

## Query transformation là gì?
Query transformation là bước biến đổi câu hỏi người dùng trước khi retrieval để tăng khả năng tìm đúng tài liệu liên quan.

## Vì sao cần query transformation?
- Người dùng có thể hỏi quá ngắn, thiếu ngữ cảnh hoặc dùng từ mơ hồ.
- Một câu hỏi phức tạp thường chứa nhiều ý nhỏ cần tách riêng.
- Từ khóa trong tài liệu và từ khóa người dùng dùng có thể khác nhau.

## Các kỹ thuật phổ biến
### 1) Query rewriting
- Viết lại câu hỏi theo ngôn ngữ rõ ràng hơn, giữ nguyên ý nghĩa.
- Ví dụ: “lỗi timeout API” -> “nguyên nhân và cách xử lý timeout khi gọi API nội bộ”.

### 2) Multi-query expansion
- Tạo nhiều biến thể truy vấn từ một câu hỏi.
- Mỗi biến thể nhắm vào một góc nhìn (định nghĩa, nguyên nhân, cách làm, cảnh báo).
- Tăng recall nhưng cần kiểm soát chi phí retrieval.

### 3) Decomposition
- Tách câu hỏi lớn thành nhiều sub-question.
- Retrieval theo từng sub-question rồi tổng hợp kết quả.
- Phù hợp câu hỏi dạng “so sánh”, “nguyên nhân + giải pháp”.

## Best practices
- Giới hạn số query biến thể (ví dụ 3–5) để tránh tăng latency quá mức.
- Log query gốc + query sau biến đổi để phục vụ debug.
- Dùng guardrail để ngăn query rewrite làm lệch ý người dùng.
