# 04 - Struct, Enum, Pattern Matching

## 1) Struct

```rust
struct User {
    username: String,
    active: bool,
}

impl User {
    fn new(username: String) -> Self {
        Self { username, active: true }
    }

    fn deactivate(&mut self) {
        self.active = false;
    }
}
```

- Có named field, tuple struct, unit-like struct.
- Method đặt trong `impl`.

## 2) Enum

```rust
enum IpAddr {
    V4(u8, u8, u8, u8),
    V6(String),
}
```

- Mỗi variant có thể có dữ liệu riêng.
- `Option<T>` thay cho `null`.

## 3) Match

```rust
fn plus_one(x: Option<i32>) -> Option<i32> {
    match x {
        Some(v) => Some(v + 1),
        None => None,
    }
}
```

- `match` bắt buộc cover toàn bộ case (exhaustive).
- `if let` để viết ngắn cho một pattern.

## 4) Pattern mở rộng

- Destructuring tuple/struct/enum.
- Match guard: `Some(x) if x > 10`.
- Bỏ qua phần không dùng: `_`, `..`.
- Binding với `@`.

## 5) Checklist

- [ ] Biết chọn struct hay enum theo bài toán.
- [ ] Biết dùng `Option<T>` an toàn.
- [ ] Viết được `match` đầy đủ và dễ đọc.
