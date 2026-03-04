# 04. Chiến lược Retrieval: từ cơ bản đến nâng cao

## Dense retrieval
- Dựa trên embedding similarity (cosine/dot product).
- Mạnh ở truy vấn ngữ nghĩa, diễn đạt linh hoạt.
- Yếu với từ khóa hiếm, mã định danh, chuỗi ký tự đặc thù.

## Sparse retrieval (BM25)
- Dựa trên tần suất từ khóa và độ hiếm từ.
- Hiệu quả với keyword exact match và technical terms.
- Không mạnh ở truy vấn diễn đạt khác biệt từ vựng.

## Hybrid retrieval
Kết hợp dense + BM25 để tận dụng ưu điểm cả hai.
- Dùng weighted fusion hoặc reciprocal rank fusion.
- Thường cải thiện đáng kể recall trong hệ thống production.

## Query transformation
- **Rewrite**: chuẩn hóa câu hỏi, làm rõ ý.
- **Decompose**: tách câu hỏi phức thành nhiều câu hỏi con.
- **Expand**: thêm từ đồng nghĩa/thuật ngữ liên quan.
- **Multi-query**: tạo nhiều biến thể truy vấn và hợp nhất kết quả.

## Reranking
Sau khi có candidate (ví dụ top 50), dùng cross-encoder hoặc LLM reranker để chọn top-N chất lượng cao nhất đưa vào prompt.

## Khi nào cần tăng top_k?
- Câu hỏi có ngữ cảnh phân tán nhiều tài liệu.
- Truy vấn mơ hồ hoặc đa nghĩa.
- Dữ liệu domain nhiều thuật ngữ tương đương.

## Khi nào cần giảm top_k?
- Latency cao.
- Prompt vượt token budget.
- Nhiễu ngữ cảnh làm giảm độ chính xác câu trả lời.
