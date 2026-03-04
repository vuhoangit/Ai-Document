# Bản đồ tri thức toàn bộ tài liệu

Tài liệu này đóng vai trò là **knowledge map** cho toàn bộ thư mục `docs/`, giúp AI và người đọc:

- xác định nhanh vị trí kiến thức theo chủ đề,
- điều hướng theo nhu cầu học tập hoặc truy vấn,
- thu thập ngữ cảnh theo cụm nội dung liên quan.

## 1) Điểm vào chính

- Tổng quan tài liệu: [docs/index.md](./index.md)
- Tổng quan công nghệ: [docs/technology/index.md](./technology/index.md)

## 2) Bản đồ phân cấp (hierarchy map)

```text
docs/
├── index.md
├── knowledge-map.md
└── technology/
    ├── index.md
    ├── programming/
    ├── network/
    ├── data/
    ├── ai/
    ├── devops/
    ├── operations/
    ├── security/
    └── tester/
```

## 3) Danh mục theo miền kiến thức

### A. Programming

- [Programming overview](./technology/programming/README.md)
- Thành phần stack: [01-programming-stack-components](./technology/programming/01-programming-stack-components.md)
- Language
  - [Language overview](./technology/programming/language/README.md)
  - [HTML](./technology/programming/language/html/README.md)
  - [CSS](./technology/programming/language/css/README.md)
- Engine & Runtime
  - [Engine runtime overview](./technology/programming/engine-runtime/README.md)
  - [JVM](./technology/programming/engine-runtime/jvm/README.md)
  - [CLR](./technology/programming/engine-runtime/clr/README.md)
  - [JavaScript engines](./technology/programming/engine-runtime/javascript-engines/README.md)
  - [JavaScript runtimes](./technology/programming/engine-runtime/javascript-runtimes/README.md)
- Framework
  - [Framework overview](./technology/programming/framework/README.md)
  - Backend: [Spring Boot](./technology/programming/framework/spring-boot/README.md), [Django](./technology/programming/framework/django/README.md), [Laravel](./technology/programming/framework/laravel/README.md), [NestJS](./technology/programming/framework/nestjs/README.md), [Gin](./technology/programming/framework/gin/README.md), [Fiber](./technology/programming/framework/fiber/README.md), [Actix Web](./technology/programming/framework/actix-web/README.md), [Axum](./technology/programming/framework/axum/README.md)
  - Frontend: [React](./technology/programming/framework/react/README.md), [Angular](./technology/programming/framework/angular/README.md), [Vue](./technology/programming/framework/vue/README.md), [Nuxt](./technology/programming/framework/nuxt/README.md)
  - CSS/UI: [Bootstrap](./technology/programming/framework/bootstrap/README.md), [Bulma](./technology/programming/framework/bulma/README.md), [Foundation](./technology/programming/framework/foundation/README.md), [Tailwind CSS](./technology/programming/framework/tailwind-css/README.md)
- [Library](./technology/programming/library/README.md)
- [Tooling](./technology/programming/tooling/README.md)
- [Platform & infrastructure](./technology/programming/platform-infrastructure/README.md)

### B. Network

- [Network overview](./technology/network/README.md)

### C. Data

- [Data overview](./technology/data/README.md)
- Retrieval-Augmented Generation (RAG)
  - [RAG index](./technology/data/retrieval-augmented-generation/index.md)
  - [01-rag-architecture](./technology/data/retrieval-augmented-generation/01-rag-architecture.md)
  - [02-data-and-chunking](./technology/data/retrieval-augmented-generation/02-data-and-chunking.md)
  - [03-embeddings-and-indexing](./technology/data/retrieval-augmented-generation/03-embeddings-and-indexing.md)
  - [04-retrieval-strategies](./technology/data/retrieval-augmented-generation/04-retrieval-strategies.md)
  - [05-response-generation](./technology/data/retrieval-augmented-generation/05-response-generation.md)
  - [06-rag-evaluation](./technology/data/retrieval-augmented-generation/06-rag-evaluation.md)
  - [07-operations-and-monitoring](./technology/data/retrieval-augmented-generation/07-operations-and-monitoring.md)
  - [08-security-and-compliance](./technology/data/retrieval-augmented-generation/08-security-and-compliance.md)
  - [09-system-design-patterns](./technology/data/retrieval-augmented-generation/09-system-design-patterns.md)
  - [10-incident-playbooks](./technology/data/retrieval-augmented-generation/10-incident-playbooks.md)
  - [11-query-transformation](./technology/data/retrieval-augmented-generation/11-query-transformation.md)
  - [12-hybrid-search-and-reranking](./technology/data/retrieval-augmented-generation/12-hybrid-search-and-reranking.md)
  - [13-rag-for-internal-documents](./technology/data/retrieval-augmented-generation/13-rag-for-internal-documents.md)

### D. AI

- [AI overview](./technology/ai/README.md)
- [Machine learning fundamentals](./technology/ai/machine-learning-fundamentals/README.md)
- [Deep learning](./technology/ai/deep-learning/README.md)
- [Natural language processing](./technology/ai/natural-language-processing/README.md)
- [Large language models](./technology/ai/large-language-models/README.md)
- [Prompt engineering](./technology/ai/prompt-engineering/README.md)
- [AI agents](./technology/ai/ai-agents/README.md)

### E. DevOps

- [DevOps overview](./technology/devops/README.md)
- [CI/CD](./technology/devops/ci-cd/README.md)
- [Containers and orchestration](./technology/devops/containers-and-orchestration/README.md)
- [Infrastructure as code](./technology/devops/infrastructure-as-code/README.md)
- [Observability and monitoring](./technology/devops/observability-and-monitoring/README.md)
- [Reliability and incident response](./technology/devops/reliability-and-incident-response/README.md)

### F. Operations

- [Operations overview](./technology/operations/README.md)
- [Runbooks and SOPs](./technology/operations/runbooks-and-sops/README.md)
- [Service operations](./technology/operations/service-operations/README.md)
- [Change and release management](./technology/operations/change-and-release-management/README.md)
- [Capacity and performance management](./technology/operations/capacity-and-performance-management/README.md)
- [On-call and escalation](./technology/operations/on-call-and-escalation/README.md)

### G. Systems

- [Systems overview](./technology/systems/README.md)

### H. Security

- [Security overview](./technology/security/README.md)

### I. Tester

- [Tester overview](./technology/tester/README.md)

## 4) Cách AI nên thu thập tri thức (gợi ý)

1. Bắt đầu từ `docs/index.md` → `docs/technology/index.md` để xác định miền kiến thức.
2. Ưu tiên đọc `README.md` của từng miền để lấy khung khái niệm trước.
3. Với truy vấn chuyên sâu về RAG, đọc theo thứ tự `01` → `13` trong thư mục RAG.
4. Khi xây dựng dữ liệu embedding, dùng liên kết ở mục 3 làm nguồn canonical để tránh bỏ sót tài liệu.

## 5) Gợi ý nhãn metadata cho indexing (tuỳ chọn)

Có thể gắn metadata khi ingest tài liệu:

- `domain`: `programming | network | data | ai | devops | operations | systems | security | tester`
- `subdomain`: ví dụ `rag`, `framework`, `engine-runtime`
- `doc_type`: `overview | guide | architecture | operations | playbook`
- `path`: đường dẫn file gốc trong `docs/`

Bản đồ này được thiết kế để dễ mở rộng: chỉ cần thêm liên kết vào đúng miền kiến thức khi có tài liệu mới.
