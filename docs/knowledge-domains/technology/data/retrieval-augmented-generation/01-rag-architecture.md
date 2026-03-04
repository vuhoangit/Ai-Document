# 01. Kiến trúc RAG: Nền tảng và thành phần

## RAG là gì?
**Retrieval-Augmented Generation (RAG)** là kiến trúc kết hợp:
1. **Retrieval**: truy hồi tài liệu liên quan từ kho tri thức.
2. **Generation**: dùng LLM sinh câu trả lời dựa trên ngữ cảnh đã truy hồi.

Mục tiêu chính của RAG là tăng độ đúng thực tế (factuality), giảm hallucination và cho phép cập nhật tri thức mà không cần fine-tune mô hình thường xuyên.

## Thành phần cốt lõi
- **Nguồn dữ liệu**: PDF, wiki nội bộ, FAQ, ticket, code, database.
- **Pipeline ingest**: làm sạch, chuẩn hóa, chia nhỏ văn bản, gắn metadata.
- **Embedding model**: chuyển chunk thành vector số học.
- **Vector store / search engine**: lưu vector và truy hồi theo độ tương đồng.
- **Retriever**: lấy top-k ngữ cảnh liên quan với truy vấn người dùng.
- **Reranker (tùy chọn)**: sắp xếp lại kết quả để tăng độ chính xác.
- **Prompt builder**: ghép câu hỏi + ngữ cảnh + chỉ dẫn hệ thống.
- **LLM generator**: sinh câu trả lời có trích dẫn nguồn.
- **Guardrails**: lọc nội dung nguy hiểm, kiểm tra định dạng, policy.
- **Observability**: log, tracing, metrics để theo dõi chất lượng.

## Luồng xử lý chuẩn
1. Người dùng gửi câu hỏi.
2. Hệ thống tiền xử lý truy vấn (rewrite, language detect, spell fix).
3. Retriever thực hiện tìm kiếm trên index.
4. (Tùy chọn) Reranker chọn ra ngữ cảnh tốt nhất.
5. Prompt builder dựng prompt có hướng dẫn trích dẫn.
6. LLM tạo câu trả lời có căn cứ theo ngữ cảnh.
7. Post-processing: kiểm tra format, lọc thông tin nhạy cảm.
8. Trả kết quả + nguồn tham chiếu.

## Thiết kế “grounded answer”
Một câu trả lời được coi là grounded khi:
- Mọi khẳng định quan trọng có thể truy vết về tài liệu nguồn.
- Không suy diễn vượt quá phạm vi ngữ cảnh đã cung cấp.
- Nêu rõ mức độ chắc chắn khi tài liệu thiếu hoặc mâu thuẫn.

## Các lỗi kiến trúc phổ biến
- Chỉ dùng dense retrieval, bỏ qua từ khóa hiếm -> mất ngữ cảnh.
- Chunk quá dài -> giảm precision khi truy hồi.
- Không version hóa index -> dữ liệu cũ gây trả lời sai.
- Không tách môi trường staging/production -> khó kiểm soát chất lượng.
