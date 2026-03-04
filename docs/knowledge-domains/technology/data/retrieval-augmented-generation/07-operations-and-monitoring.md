# 07. Vận hành và giám sát RAG trong production

## Quan sát hệ thống (observability)
Theo dõi tối thiểu các nhóm chỉ số:
- **Traffic**: QPS, loại truy vấn, tần suất theo domain.
- **Retrieval**: score phân phối, top_k thực tế, cache hit.
- **Generation**: token in/out, latency model, lỗi timeout.
- **Quality**: faithfulness score, user feedback, complaint rate.

## Logging và tracing
- Lưu truy vết mỗi request với `trace_id` xuyên suốt pipeline.
- Ghi riêng: query gốc, query rewrite, tài liệu truy hồi, prompt, output.
- Masking dữ liệu nhạy cảm trong log.

## Tối ưu hiệu năng
- Cache kết quả retrieval cho truy vấn lặp lại.
- Cache prompt-template và precomputed context khi phù hợp.
- Giảm context token bằng reranking/summary.
- Dùng model tiering: model nhỏ cho câu dễ, model lớn cho câu khó.

## Tối ưu chi phí
- Đặt ngân sách token theo tenant/use-case.
- Giới hạn chiều dài output mặc định.
- Theo dõi chi phí theo phiên bản prompt và index.
- Ưu tiên cải thiện retrieval để giảm context dư thừa.

## Quản trị thay đổi
- Mọi thay đổi prompt/retriever/index cần có changelog.
- A/B test trước rollout toàn bộ.
- Có cơ chế rollback tự động khi quality giảm.
