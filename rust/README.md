# Rust Book (Bản viết lại tiếng Việt)

> Tài liệu này là bản **viết lại ngắn gọn, có hệ thống** từ nội dung chính của *The Rust Programming Language* (rust-lang book), nhằm giúp học nhanh theo lộ trình từ cơ bản đến nâng cao.

## Mục lục

1. [Bắt đầu](#1-bắt-đầu)
2. [Đoán số - dự án đầu tiên](#2-đoán-số---dự-án-đầu-tiên)
3. [Các khái niệm phổ biến](#3-các-khái-niệm-phổ-biến)
4. [Ownership](#4-ownership)
5. [Struct](#5-struct)
6. [Enum và Pattern Matching](#6-enum-và-pattern-matching)
7. [Package, Crate, Module](#7-package-crate-module)
8. [Collections](#8-collections)
9. [Xử lý lỗi](#9-xử-lý-lỗi)
10. [Generic, Trait, Lifetime](#10-generic-trait-lifetime)
11. [Testing](#11-testing)
12. [CLI I/O project](#12-cli-io-project)
13. [Functional features](#13-functional-features)
14. [Cargo và crates.io](#14-cargo-và-cratesio)
15. [Smart Pointers](#15-smart-pointers)
16. [Concurrency](#16-concurrency)
17. [OOP style trong Rust](#17-oop-style-trong-rust)
18. [Pattern & Match chuyên sâu](#18-pattern--match-chuyên-sâu)
19. [Unsafe Rust](#19-unsafe-rust)
20. [Advanced features](#20-advanced-features)
21. [Dự án web server đa luồng](#21-dự-án-web-server-đa-luồng)
22. [Phụ lục](#22-phụ-lục)

---

## 1. Bắt đầu

- Cài Rust bằng `rustup`.
- Công cụ chính:
  - `rustc`: trình biên dịch.
  - `cargo`: build, run, test, quản lý dependency.
- Tạo dự án:
  - `cargo new ten_du_an`
  - `cargo run`, `cargo check`, `cargo test`.

**Tinh thần Rust:** an toàn bộ nhớ, hiệu năng cao, không cần GC, lỗi được phát hiện sớm bởi compiler.

## 2. Đoán số - dự án đầu tiên

Qua dự án đoán số, bạn học:

- `use std::io;`
- Biến mutable: `let mut x = ...`
- `String::new()`, `read_line`.
- Parse chuỗi sang số: `trim().parse::<u32>()`.
- Pattern matching với `match`.
- Sinh số ngẫu nhiên qua crate `rand`.

**Điểm mấu chốt:** Rust ép bạn xử lý trường hợp lỗi (`Result`) ngay từ đầu.

## 3. Các khái niệm phổ biến

### 3.1 Biến và mutability
- Mặc định immutable.
- Dùng `mut` khi cần thay đổi.
- `const` cần kiểu tường minh và có lifetime toàn chương trình.
- Shadowing: tái khai báo cùng tên biến.

### 3.2 Kiểu dữ liệu
- Scalar: `i32`, `u64`, `f32`, `bool`, `char`.
- Compound: tuple, array.

### 3.3 Hàm và biểu thức
- Rust phân biệt **statement** và **expression**.
- Block có thể trả về giá trị (không cần `return` nếu là biểu thức cuối).

### 3.4 Điều khiển luồng
- `if`, `loop`, `while`, `for`.
- `loop` có thể trả về giá trị qua `break expr`.

## 4. Ownership

Ownership là nền tảng của Rust:

1. Mỗi giá trị có một owner.
2. Tại một thời điểm chỉ có một owner.
3. Owner out-of-scope thì giá trị bị drop.

### 4.1 Move và Copy
- Dữ liệu heap (như `String`) khi gán biến khác sẽ **move**.
- Kiểu đơn giản (`i32`, `bool`, tuple chứa kiểu Copy) có thể `Copy`.

### 4.2 Borrowing
- Truyền tham chiếu `&T` để không chuyển ownership.
- Mutable reference `&mut T` cho phép sửa dữ liệu.
- Quy tắc: tại một thời điểm, hoặc nhiều immutable refs, hoặc một mutable ref.

### 4.3 Slice
- `&str`, `&[T]` là view vào dữ liệu, không sở hữu.

**Mục tiêu:** tránh data race và dangling pointer ở compile-time.

## 5. Struct

- Định nghĩa dữ liệu có tên trường.
- Dùng `impl` để thêm method.
- `Self` trong impl.
- Associated function (như constructor): `fn new(...) -> Self`.
- Struct update syntax: `..old_struct`.
- Tuple structs và unit-like structs.

## 6. Enum và Pattern Matching

- `enum` biểu diễn tập trạng thái hữu hạn, mỗi biến thể có thể mang dữ liệu.
- `Option<T>` thay cho null (`Some(T)` / `None`).
- `match` buộc exhaustiveness.
- `if let` để xử lý gọn khi chỉ quan tâm 1 pattern.

## 7. Package, Crate, Module

- **Package** chứa `Cargo.toml`.
- **Crate** là đơn vị biên dịch (binary hoặc library).
- **Module** tổ chức mã và quyền truy cập.

Dùng:
- `mod`, `pub`, `use`, `super`, `crate::...`.
- Tách module theo file/folder.

## 8. Collections

### 8.1 Vector (`Vec<T>`)
- Mảng động, dữ liệu liên tục trong bộ nhớ.
- Truy cập bằng index hoặc `get`.

### 8.2 String
- UTF-8 bytes, không index trực tiếp theo ký tự.
- Duyệt qua `chars()` hoặc `bytes()`.

### 8.3 HashMap
- Lưu cặp key-value.
- Ownership của key/value được chuyển vào map (trừ khi dùng reference hợp lệ).

## 9. Xử lý lỗi

- `panic!`: lỗi không phục hồi.
- `Result<T, E>`: lỗi có thể xử lý.
- Toán tử `?` để propagate error.
- Có thể dùng `main() -> Result<(), E>`.

**Nguyên tắc:** lỗi kỳ vọng thì dùng `Result`, lỗi logic nghiêm trọng mới `panic!`.

## 10. Generic, Trait, Lifetime

### 10.1 Generic
- Viết mã tổng quát cho nhiều kiểu.

### 10.2 Trait
- Tương tự interface.
- Trait bound: `T: Display + Clone`.
- `impl Trait` cho tham số/giá trị trả về.

### 10.3 Lifetime
- Mô tả quan hệ sống của tham chiếu.
- Borrow checker dùng lifetime để ngăn dangling refs.
- Lifetime elision giảm số annotation phải viết.

## 11. Testing

- Unit test trong cùng file (`#[cfg(test)]`).
- Integration test trong `tests/`.
- Dùng `cargo test`.
- Macro assert: `assert!`, `assert_eq!`, `assert_ne!`.
- Kiểm tra panic bằng `#[should_panic]`.

## 12. CLI I/O project

Dự án mini grep (`minigrep`) dạy:

- Đọc args (`std::env::args`).
- Đọc file (`std::fs`).
- Tách logic parse config và run.
- Refactor để testable.
- Biến môi trường để bật tìm kiếm không phân biệt hoa thường.

## 13. Functional features

- Closure: hàm ẩn danh có thể capture môi trường.
- Iterator: xử lý pipeline (`map`, `filter`, `collect`).
- Ưu tiên iterator thay vì vòng lặp thủ công khi phù hợp.
- Khái niệm “zero-cost abstraction”.

## 14. Cargo và crates.io

- Profile build: `dev`, `release`.
- Publish crate: metadata, versioning, API docs.
- Workspace quản lý nhiều crate cùng repo.
- Cài binary từ crate: `cargo install`.
- Extensibility qua subcommand Cargo.

## 15. Smart Pointers

- `Box<T>`: cấp phát trên heap.
- `Deref` trait: hành vi deref custom.
- `Drop` trait: cleanup khi ra khỏi scope.
- `Rc<T>`: nhiều owner (single-thread).
- `RefCell<T>`: interior mutability, kiểm tra borrow lúc runtime.
- Kết hợp `Rc<RefCell<T>>` cho cấu trúc dữ liệu chia sẻ có thể sửa.
- Tránh cycle memory leak với `Weak<T>`.

## 16. Concurrency

- Thread: `std::thread::spawn`.
- Message passing: `std::sync::mpsc`.
- Shared state: `Mutex<T>`, `Arc<T>`.
- Rust type system giúp tránh data race ở compile-time.
- `Send` và `Sync` marker traits cho an toàn đa luồng.

## 17. OOP style trong Rust

Rust không theo OOP cổ điển hoàn toàn, nhưng hỗ trợ:

- Đóng gói qua module + visibility.
- Kế thừa hành vi qua trait.
- Đa hình qua trait objects (`dyn Trait`).
- State pattern có thể viết theo hướng type-safe.

## 18. Pattern & Match chuyên sâu

- Pattern dùng trong `match`, `if let`, `while let`, `let`, tham số hàm.
- Destructuring struct/tuple/enum.
- Match guard (`if condition`).
- Binding với `@`.
- `_` và `..` để bỏ qua phần không quan tâm.

## 19. Unsafe Rust

Unsafe cho phép 5 nhóm năng lực chính:

1. Dereference raw pointer.
2. Gọi hàm unsafe.
3. Truy cập/ghi `static mut`.
4. Triển khai unsafe trait.
5. Truy cập trường union.

**Quan trọng:** vẫn bao bọc unsafe trong API safe tối đa có thể.

## 20. Advanced features

- Lifetime nâng cao.
- Associated types.
- Default generic type parameters.
- Fully qualified syntax khi trùng tên method.
- Supertraits.
- Newtype pattern.
- Type alias.
- Never type `!`.
- Function pointers và closures nâng cao.
- Macro (`macro_rules!`) cho metaprogramming.

## 21. Dự án web server đa luồng

Bạn xây server HTTP tối giản:

- Lắng nghe TCP.
- Parse request cơ bản.
- Trả HTML response.
- Dùng thread pool thay vì tạo thread vô hạn.
- Triển khai graceful shutdown.

**Bài học:** kết hợp ownership + concurrency + error handling trong bài toán thực tế.

## 22. Phụ lục

### A. Từ khóa
Tổng hợp keyword của Rust (`fn`, `let`, `match`, `trait`, `unsafe`, ...).

### B. Toán tử
Danh sách operator và ngữ nghĩa.

### C. Trait trong prelude
Những trait/macro tự động được import.

### D. Công cụ phát triển
- `rustfmt` để format.
- `clippy` để lint.
- `rust-analyzer` để hỗ trợ IDE.

### E. Edition
Sự khác biệt giữa các edition (2018, 2021, ...), đảm bảo nâng cấp dần mà không phá vỡ hệ sinh thái.

### F. Bản dịch
Thông tin cộng đồng dịch Rust Book sang các ngôn ngữ.

---

## Lộ trình học nhanh (gợi ý 4 tuần)

- **Tuần 1:** Chương 1–6 (cú pháp + ownership + enum).
- **Tuần 2:** Chương 7–11 (module, collections, error, generic, test).
- **Tuần 3:** Chương 12–16 (project, iterator, smart pointer, concurrency).
- **Tuần 4:** Chương 17–21 + phụ lục (nâng cao, unsafe, web server).

## Tài nguyên chính thức

- Rust Book: https://doc.rust-lang.org/book/
- Rust by Example: https://doc.rust-lang.org/rust-by-example/
- Rust API docs: https://doc.rust-lang.org/std/

