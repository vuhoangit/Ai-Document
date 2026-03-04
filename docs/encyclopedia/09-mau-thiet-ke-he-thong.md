# 09. Mẫu thiết kế hệ thống RAG theo quy mô

## Mẫu A: MVP nhanh (nhỏ)
- 1 nguồn dữ liệu chính.
- Ingest theo batch hàng ngày.
- Hybrid retrieval cơ bản.
- Không reranker hoặc chỉ reranker nhẹ.

Phù hợp khi cần ra sản phẩm nhanh để validate nhu cầu.

## Mẫu B: Production trung bình
- Nhiều nguồn dữ liệu và ACL theo phòng ban.
- Ingest near-real-time cho tài liệu quan trọng.
- Hybrid + reranker + caching.
- Dashboard quality/cost/latency.

Phù hợp cho nội bộ doanh nghiệp quy mô vừa.

## Mẫu C: Enterprise lớn
- Kiến trúc multi-tenant, multi-region.
- Event-driven ingest + versioned indexes.
- Router model và policy engine theo tenant.
- Guardrails nâng cao + human-in-the-loop.

Phù hợp khi yêu cầu tuân thủ và SLA cao.

## Tiêu chí chọn mẫu
- Độ quan trọng của độ đúng (accuracy) so với chi phí.
- Tần suất cập nhật dữ liệu.
- Mức độ nhạy cảm dữ liệu.
- Yêu cầu SLA và khả năng mở rộng.
