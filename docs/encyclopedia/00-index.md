# Bách khoa toàn thư RAG (Retrieval-Augmented Generation)

## Mục tiêu bộ tài liệu
Bộ tài liệu này được thiết kế để làm **nguồn tri thức chuẩn hóa** cho hệ thống RAG, giúp:
- Đồng nhất định nghĩa, thuật ngữ và thực hành tốt.
- Hỗ trợ truy hồi chính xác khi người dùng đặt câu hỏi kỹ thuật.
- Dễ chunking, embedding và trích dẫn nguồn trong câu trả lời.

## Cách tổ chức nội dung
- `01-kien-truc-rag.md`: Khái niệm nền tảng, thành phần và luồng xử lý.
- `02-du-lieu-va-chia-nho.md`: Chuẩn hóa dữ liệu, chunking và metadata.
- `03-embedding-va-index.md`: Embedding, vector index, chiến lược cập nhật.
- `04-chien-luoc-retrieval.md`: BM25, dense retrieval, hybrid, reranking.
- `05-sinh-cau-tra-loi.md`: Prompting, grounding, kiểm soát hallucination.
- `06-danh-gia-rag.md`: Chỉ số đánh giá retrieval, generation và end-to-end.
- `07-van-hanh-va-giam-sat.md`: Vận hành production, giám sát, tối ưu chi phí.
- `08-bao-mat-va-tuan-thu.md`: Bảo mật dữ liệu, phân quyền, tuân thủ.
- `09-mau-thiet-ke-he-thong.md`: Mẫu kiến trúc tham chiếu theo quy mô.
- `10-playbook-su-co.md`: Playbook xử lý sự cố thường gặp trong RAG.

## Quy ước biên soạn cho RAG
1. Mỗi mục nên có tiêu đề rõ ràng, tập trung một chủ đề.
2. Ưu tiên đoạn văn ngắn + danh sách gạch đầu dòng để dễ chunk.
3. Tối ưu cho truy hồi: lặp lại từ khóa quan trọng có chủ đích.
4. Tránh nội dung mơ hồ, luôn nêu điều kiện áp dụng và đánh đổi.
5. Với khuyến nghị kỹ thuật, ghi rõ “khi nào nên dùng / không nên dùng”.

## Từ khóa cốt lõi
`RAG`, `retrieval`, `embedding`, `vector database`, `reranker`, `grounding`, `hallucination`, `evaluation`, `latency`, `cost optimization`, `security`, `PII`.
