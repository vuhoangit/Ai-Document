# Programming stack components

Tài liệu này chia các thành phần trong programming theo mô tả: **language, engine/runtime, framework, library, tooling, platform/infrastructure**.

## 1) Language (Ngôn ngữ lập trình)

Ngôn ngữ để viết source code.

Ví dụ:
- JavaScript, TypeScript
- Python
- Java
- C#
- Go
- Rust

## 2) Engine / Runtime (Bộ máy thực thi)

Thành phần dùng để chạy code.

- **Engine** thường là bộ thông dịch/JIT ở mức thấp.
- **Runtime** thường bao gồm engine + API hệ thống + thư viện chuẩn mở rộng.

Ví dụ:
- JavaScript engine: V8, SpiderMonkey
- JavaScript runtime: Node.js, Deno, Bun
- Java runtime: JVM
- .NET runtime: CLR

## 3) Framework

Bộ khung phát triển ứng dụng theo cấu trúc có sẵn.

Ví dụ:
- Frontend: React, Vue, Angular
- Backend: Django, Spring Boot, Laravel, NestJS

Đặc điểm:
- Có convention rõ ràng
- Tăng tốc phát triển dự án lớn
- Thường tích hợp routing, DI, validation, lifecycle, v.v.

## 4) Library

Gói chức năng chuyên biệt, gọi khi cần.

Ví dụ:
- Axios (HTTP)
- Lodash (utility)
- NumPy/Pandas (Python data)

Khác biệt thường dùng:
- **Library**: ứng dụng gọi thư viện
- **Framework**: framework điều phối luồng chạy và gọi code của ứng dụng

## 5) Tooling

Các công cụ phục vụ vòng đời phát triển phần mềm.

Ví dụ:
- Build/bundle: Vite, Webpack, Maven, Gradle
- Test: Jest, Pytest, JUnit
- Lint/format: ESLint, Prettier, Black
- CI/CD: GitHub Actions, GitLab CI

## 6) Platform / Infrastructure

Môi trường triển khai, vận hành và lưu trữ.

Ví dụ:
- Docker, Kubernetes
- Cloud: AWS, GCP, Azure
- Data layer: PostgreSQL, MySQL, Redis
- OS/Linux và tài nguyên hạ tầng

## Ví dụ tổng hợp cho web backend (Node.js)

- **Language**: TypeScript
- **Engine**: V8
- **Runtime**: Node.js
- **Framework**: NestJS/Express
- **Library**: Axios, Zod
- **Tooling**: ESLint, Jest, pnpm
- **Platform**: Docker + PostgreSQL + AWS
