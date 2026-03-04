# 02. Dữ liệu và chiến lược chia nhỏ (Chunking)

## Vai trò của chất lượng dữ liệu
Trong RAG, chất lượng dữ liệu thường ảnh hưởng lớn hơn việc thay đổi LLM. Dữ liệu tốt cần:
- Đúng và cập nhật.
- Ít nhiễu (boilerplate, trùng lặp, lỗi OCR).
- Có cấu trúc rõ ràng để chunk hợp lý.

## Pipeline chuẩn hóa dữ liệu
1. **Thu thập**: xác định nguồn tin “đáng tin cậy” theo domain.
2. **Làm sạch**: loại header/footer lặp, script, tracking text.
3. **Chuẩn hóa encoding**: UTF-8, chuẩn dấu tiếng Việt.
4. **Tách cấu trúc**: tiêu đề, mục, bảng, chú thích, phụ lục.
5. **Gắn metadata**: nguồn, thời gian, phiên bản, quyền truy cập.
6. **Khử trùng lặp**: exact + near-duplicate.

## Chiến lược chunking
### 1) Fixed-size chunking
- Chia theo số token cố định (ví dụ 300–800 token).
- Dùng overlap (10–20%) để bảo toàn ngữ cảnh.
- Ưu điểm: đơn giản, dễ vận hành.
- Nhược điểm: dễ cắt ngang ý nếu tài liệu dài và phức tạp.

### 2) Semantic chunking
- Chia theo đoạn/ý nghĩa (heading, paragraph, section).
- Phù hợp tài liệu có cấu trúc tốt.
- Tăng precision nhưng xử lý ingest phức tạp hơn.

### 3) Hybrid chunking
- Ưu tiên semantic, fallback fixed-size khi cần.
- Cân bằng giữa chất lượng retrieval và chi phí xử lý.

## Metadata nên có cho mỗi chunk
- `doc_id`, `chunk_id`, `title`, `section_path`.
- `created_at`, `updated_at`, `version`.
- `language`, `domain`, `acl_tags`.
- `source_url` hoặc định danh tài liệu gốc.

## Best practices
- Chunk “đủ nhỏ để chính xác”, “đủ lớn để đủ ngữ nghĩa”.
- Tránh trộn nhiều chủ đề vào một chunk.
- Với FAQ, mỗi Q/A là một chunk tự nhiên.
- Với quy trình nhiều bước, giữ đầy đủ bước trong cùng cụm chunk.
