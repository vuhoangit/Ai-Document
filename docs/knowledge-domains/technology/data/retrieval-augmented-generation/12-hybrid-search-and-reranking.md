# 12. Hybrid Search và Reranking

## Hybrid Search
Hybrid search kết hợp:
- **Dense retrieval** (embedding/vector search): mạnh về tương đồng ngữ nghĩa.
- **Sparse retrieval** (BM25/keyword): mạnh về từ khóa chính xác, mã lỗi, tên riêng.

Kết hợp hai tín hiệu giúp tăng độ ổn định khi dữ liệu đa dạng.

## Kiến trúc triển khai phổ biến
1. Chạy dense và sparse retrieval song song.
2. Hợp nhất danh sách ứng viên theo điểm hoặc luật ưu tiên.
3. Gửi top N ứng viên vào mô hình reranker.
4. Lấy top K cuối cho bước generation.

## Reranking
Reranker là mô hình chấm điểm lại mức liên quan giữa query và tài liệu, thường cải thiện precision@k.

### Khi nào nên dùng reranker?
- Tài liệu dài, nhiều đoạn tương tự nhau.
- Câu hỏi cần độ chính xác cao.
- Hệ thống có thể chấp nhận thêm 1 tầng latency.

## Chiến lược cân bằng chất lượng - chi phí
- Dùng retrieval rộng (N lớn), rerank sâu cho truy vấn quan trọng.
- Giảm N hoặc tắt reranker cho truy vấn đơn giản để tiết kiệm chi phí.
- Tối ưu theo traffic tier: free, standard, premium.

## Chỉ số cần theo dõi
- Recall@N trước reranking.
- MRR hoặc NDCG sau reranking.
- Latency p95 theo từng tầng retrieval và reranking.
