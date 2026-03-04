# 03. Embedding và Index trong RAG

## Embedding là gì?
Embedding là biểu diễn văn bản dưới dạng vector trong không gian nhiều chiều, cho phép đo độ tương đồng ngữ nghĩa giữa truy vấn và tài liệu.

## Tiêu chí chọn embedding model
- Hỗ trợ ngôn ngữ mục tiêu (đặc biệt tiếng Việt).
- Hiệu năng retrieval thực tế trên dữ liệu domain.
- Kích thước vector và chi phí lưu trữ/tra cứu.
- Tốc độ encode khi ingest và khi query-time.

## Vector index phổ biến
- **HNSW**: độ chính xác cao, latency tốt, memory tương đối lớn.
- **IVF/IVFPQ**: tiết kiệm bộ nhớ, phù hợp dữ liệu rất lớn.
- **Flat index**: chính xác tuyệt đối, nhưng chậm khi quy mô lớn.

## Thiết kế index lifecycle
1. Index theo phiên bản (`index_v1`, `index_v2`, ...).
2. Rebuild định kỳ hoặc incremental update theo nguồn.
3. Blue/green deployment cho index để tránh downtime.
4. Rollback nhanh khi phát hiện suy giảm chất lượng.

## Những quyết định quan trọng
- Chọn `top_k` retrieval (thường 3–20 tùy domain).
- Cân bằng precision và recall bằng threshold score.
- Duy trì chiến lược re-embedding khi đổi model.
- Theo dõi “embedding drift” khi dữ liệu đổi theo thời gian.
