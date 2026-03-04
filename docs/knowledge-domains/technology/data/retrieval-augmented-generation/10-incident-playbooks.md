# 10. Playbook xử lý sự cố RAG

## Sự cố 1: Trả lời sai dù có dữ liệu đúng
### Dấu hiệu
- Retriever có tài liệu đúng nhưng câu trả lời không dùng.

### Cách xử lý
1. Kiểm tra prompt có ép bám nguồn đủ chặt chưa.
2. Giảm nhiễu context bằng reranker hoặc giảm top_k.
3. Kiểm tra thứ tự tài liệu trong prompt.
4. Đánh giá lại model instruction-following.

## Sự cố 2: Không tìm thấy tài liệu liên quan
### Dấu hiệu
- Recall@k thấp trên truy vấn thực tế.

### Cách xử lý
1. Bổ sung hybrid retrieval nếu đang chỉ dùng dense.
2. Rà soát chunking, metadata và chất lượng OCR.
3. Dùng query rewrite/multi-query.
4. Re-embedding dữ liệu bằng model phù hợp domain.

## Sự cố 3: Latency tăng đột biến
### Cách xử lý
1. Phân rã latency theo từng stage (retrieve/rerank/generate).
2. Bật cache cho truy vấn lặp.
3. Giảm context token và số lượng candidate rerank.
4. Dùng model nhỏ hơn cho truy vấn đơn giản.

## Sự cố 4: Chi phí vượt ngân sách
### Cách xử lý
1. Áp token quota theo tenant.
2. Tối ưu retrieval để giảm context dư.
3. Giới hạn output length mặc định.
4. Theo dõi chi phí theo prompt version để tìm nguyên nhân.

## Sự cố 5: Rò rỉ dữ liệu nhạy cảm
### Cách xử lý khẩn cấp
1. Tạm ngắt endpoint bị ảnh hưởng.
2. Thu hồi credential/secret liên quan.
3. Vá policy lọc retrieval theo ACL.
4. Rà soát log, lập báo cáo sự cố, cập nhật guardrails.
