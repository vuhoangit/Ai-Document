# 12 - Unsafe, advanced features, web server, phụ lục

## 1) Unsafe Rust

5 khả năng chính trong `unsafe`:
1. Dereference raw pointers.
2. Gọi hàm unsafe.
3. Truy cập `static mut`.
4. Implement unsafe trait.
5. Truy cập field của `union`.

Nguyên tắc:
- Giữ vùng unsafe nhỏ nhất có thể.
- Cung cấp API safe bọc ngoài vùng unsafe.
- Document rõ invariants.

## 2) Tính năng nâng cao

- Associated types.
- Default type parameters.
- Fully qualified syntax.
- Supertraits.
- Newtype pattern.
- Type alias.
- Never type `!`.
- Function pointers.
- Declarative macro `macro_rules!`.

## 3) Dự án web server đa luồng (chapter project)

Mục tiêu:
- Lắng nghe TCP.
- Parse request HTTP tối giản.
- Trả response tĩnh.
- Dùng thread pool để giới hạn tài nguyên.
- Hỗ trợ graceful shutdown.

Kiến trúc gợi ý:
- `main`: khởi động listener + thread pool.
- `pool`: quản lý workers.
- `http`: parse request/response tối thiểu.
- `handler`: route request thành hành động.

## 4) Phụ lục quan trọng

- Keywords thường gặp (`fn`, `let`, `match`, `trait`, `unsafe`...).
- Operator và precedence.
- Prelude (những thứ được import mặc định).
- Công cụ: `rustfmt`, `clippy`, `rust-analyzer`.
- Editions (2018/2021/2024) và tương thích.

## 5) Lộ trình học đề xuất

- Tuần 1: chương 01-04.
- Tuần 2: chương 05-08.
- Tuần 3: chương 09-10.
- Tuần 4: chương 11-12 + làm project nhỏ.

## 6) Tiêu chí “đủ kiến thức nền Rust”

Bạn được xem là nắm nền tảng khi có thể:
- Viết CLI có test, xử lý lỗi rõ ràng.
- Giải thích ownership/borrowing bằng ví dụ cụ thể.
- Dùng trait + generic + lifetime cho API vừa an toàn vừa tái sử dụng.
- Dùng `Arc<Mutex<_>>` đúng ngữ cảnh trong bài toán đa luồng.
- Đọc/viết code có `Result`, iterator, pattern matching tự tin.
