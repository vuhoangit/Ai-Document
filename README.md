# AI Document Hub

Kho tài liệu đã được tái cấu trúc theo chuẩn quốc tế để dùng đồng thời cho:

- **Human readers** (học tập, tra cứu, onboarding).
- **AI systems** (RAG ingestion, indexing, retrieval, auditability).

## 1) Chuẩn áp dụng

Repository này áp dụng các thực hành phổ biến trong tài liệu kỹ thuật quốc tế:

- **Diátaxis framework** cho phân loại nội dung theo mục đích sử dụng:
  - Tutorial (hướng dẫn học theo bước)
  - How-to guide (thao tác theo nhiệm vụ)
  - Reference (tra cứu chuẩn xác)
  - Explanation (giải thích khái niệm)
- **Docs-as-Code** cho quy trình phiên bản hóa, review, và cập nhật.
- **Information Architecture (IA)** theo miền kiến thức + phân tầng điều hướng.
- **Metadata-first indexing** để tối ưu chất lượng RAG và giảm hallucination.

## 2) Cấu trúc tài liệu chuẩn hóa

```text
docs/
├── index.md                           # Cổng vào chính cho người đọc + AI
├── knowledge-map.md                   # Bản đồ tri thức canonical cho ingest
├── governance/
│   └── documentation-standard.md      # Chuẩn viết/tổ chức/đặt tên tài liệu
├── templates/
│   └── document-template.md           # Mẫu tài liệu chuẩn
└── technology/
    ├── index.md
    ├── programming/
    ├── network/
    ├── data/
    ├── ai/
    ├── devops/
    ├── operations/
    ├── systems/
    ├── security/
    └── tester/
```

## 3) Điểm bắt đầu nhanh

### Dành cho người đọc

1. Mở `docs/index.md` để chọn mục tiêu đọc theo loại tài liệu.
2. Vào `docs/technology/index.md` để chọn domain.
3. Đọc `README.md` trong domain/subdomain trước khi đọc tài liệu chi tiết.

### Dành cho AI/RAG pipeline

1. Dùng `docs/knowledge-map.md` làm nguồn canonical.
2. Ingest theo thứ tự:
   - `docs/index.md`
   - `docs/governance/documentation-standard.md`
   - `docs/technology/index.md`
   - các `README.md` theo domain/subdomain
   - tài liệu chuyên sâu (`01-`, `02-`...).
3. Bắt buộc gắn metadata tối thiểu: `domain`, `subdomain`, `doc_type`, `audience`, `path`, `last_reviewed`.

## 4) Nguyên tắc quản trị tài liệu

- Thư mục: tiếng Anh, lowercase-kebab-case.
- Mỗi miền kiến thức phải có `README.md` theo template chuẩn.
- Khi thêm tài liệu mới phải cập nhật:
  - `docs/index.md`
  - `docs/knowledge-map.md`
  - mục liên quan trong `docs/technology/index.md`
- Ưu tiên viết rõ phạm vi, giả định, và liên kết chéo để tăng chất lượng truy xuất.

## 5) Tài liệu nền tảng

- Cổng điều hướng: [`docs/index.md`](docs/index.md)
- Knowledge map canonical: [`docs/knowledge-map.md`](docs/knowledge-map.md)
- Chuẩn tài liệu: [`docs/governance/documentation-standard.md`](docs/governance/documentation-standard.md)
- Mẫu viết tài liệu: [`docs/templates/document-template.md`](docs/templates/document-template.md)
