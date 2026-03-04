# 06 - Collections và xử lý chuỗi

## 1) Vector

```rust
let mut v = vec![1, 2, 3];
v.push(4);
let first = v.get(0);
```

- Dùng `get` khi cần an toàn (`Option<&T>`).
- Tránh giữ reference vào phần tử rồi lại `push` gây reallocation.

## 2) String

```rust
let mut s = String::from("Xin");
s.push_str(" chào");
for c in s.chars() { println!("{c}"); }
```

- `String` là UTF-8 bytes.
- Không index string bằng `s[i]`.

## 3) HashMap

```rust
use std::collections::HashMap;
let mut scores = HashMap::new();
scores.insert(String::from("Alice"), 10);
```

- Key cần `Eq + Hash`.
- `entry` API giúp insert/update gọn.

## 4) Checklist

- [ ] Biết chọn `Vec`, `String`, `HashMap` đúng ngữ cảnh.
- [ ] Tránh sai lầm Unicode khi xử lý chuỗi.
- [ ] Dùng `entry` cho bài toán đếm tần suất.
