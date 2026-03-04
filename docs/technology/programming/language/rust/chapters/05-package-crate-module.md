# 05 - Package, Crate, Module

## 1) Khái niệm

- **Package**: thư mục có `Cargo.toml`.
- **Crate**: đơn vị biên dịch.
  - Binary crate: có `src/main.rs`.
  - Library crate: có `src/lib.rs`.
- **Module**: tổ chức namespace/visibility.

## 2) Tổ chức mã

```rust
// src/lib.rs
pub mod math;

// src/math.rs
pub fn add(a: i32, b: i32) -> i32 { a + b }
```

## 3) Visibility

- Mặc định private.
- Dùng `pub` để export.
- `use` để rút gọn đường dẫn.
- `crate::`, `super::` để điều hướng module tree.

## 4) Thực hành tốt

- Chia module theo domain thay vì theo loại file.
- API public tối thiểu, ẩn implementation details.
- Viết doc comments cho phần `pub`.

## 5) Checklist

- [ ] Hiểu package/crate/module khác nhau thế nào.
- [ ] Tổ chức được project đa module.
- [ ] Kiểm soát truy cập bằng `pub` hợp lý.
