# AI Document Hub

Kho tài liệu này được thiết kế để dùng chung cho **người học/kỹ sư** và **hệ thống AI (đặc biệt là RAG)**.

- Người dùng có thể đọc theo lộ trình chủ đề để học nhanh.
- AI có thể ingest theo cấu trúc phân cấp rõ ràng để truy xuất tri thức chính xác hơn.

## 1) Mục tiêu của repository

- Tập trung tri thức kỹ thuật theo từng miền (Programming, Data, AI, DevOps, Security...).
- Chuẩn hoá cấu trúc và cách đặt tên để dễ mở rộng.
- Tối ưu cho cả:
  - **Human-readable**: dễ điều hướng, có overview trước khi đi sâu.
  - **Machine-readable**: thuận tiện chunking, indexing, retrieval cho RAG.

## 2) Điểm bắt đầu nhanh

### Dành cho người đọc

1. Mở trang tổng quan: `docs/index.md`.
2. Chọn miền kiến thức cần học (ví dụ `technology/data`, `technology/ai`).
3. Đọc file `README.md` trong miền đó trước, sau đó đọc các tài liệu đánh số (`01`, `02`, ...).

### Dành cho AI/RAG pipeline

1. Dùng `docs/knowledge-map.md` làm tài liệu điều hướng canonical.
2. Ingest theo thứ tự:
   - `docs/index.md`
   - `docs/technology/index.md`
   - các `README.md` theo miền
   - tài liệu chuyên sâu theo thứ tự số
3. Gắn metadata tối thiểu khi index:
   - `domain`
   - `subdomain`
   - `doc_type`
   - `path`

## 3) Cấu trúc thư mục chính

```text
docs/
├── index.md
├── knowledge-map.md
└── technology/
    ├── programming/
    ├── network/
    ├── data/
    │   └── retrieval-augmented-generation/
    ├── ai/
    ├── devops/
    ├── operations/
    ├── systems/
    ├── security/
    └── tester/
```

## 4) Hướng dẫn sử dụng tài liệu cho RAG

- **Scope rõ ràng**: chia retrieval theo `domain/subdomain` trước khi semantic search.
- **Ưu tiên tài liệu khung**: đọc `README.md` để xây context trước khi trích đoạn chuyên sâu.
- **Hybrid retrieval khuyến nghị**:
  - Bước 1: filter theo metadata (`domain`, `subdomain`).
  - Bước 2: vector search + keyword/BM25.
  - Bước 3: rerank theo mức liên quan với truy vấn.
- **Giảm hallucination**:
  - Chỉ trả lời từ tài liệu đã index.
  - Trả kèm `path` nguồn tài liệu trong câu trả lời.

## 5) Quy ước nội dung khi bổ sung tài liệu mới

- Thư mục dùng tiếng Anh, lowercase-kebab-case.
- Tên file mô tả theo chủ đề; dùng tiền tố số (`01-`, `02-`...) khi cần thể hiện thứ tự học.
- Mỗi miền nên có `README.md` để tóm tắt khái niệm và liên kết tài liệu con.
- Cập nhật `docs/knowledge-map.md` khi thêm miền hoặc tài liệu quan trọng.

## 6) Tài liệu tham chiếu quan trọng

- Tổng quan tài liệu: [`docs/index.md`](docs/index.md)
- Bản đồ tri thức ingest cho AI: [`docs/knowledge-map.md`](docs/knowledge-map.md)

---

Nếu bạn là **người mới**, hãy bắt đầu từ `docs/index.md`.
Nếu bạn đang xây **RAG system**, hãy bắt đầu từ `docs/knowledge-map.md` và ingest theo thứ tự từ tổng quan đến chuyên sâu.
