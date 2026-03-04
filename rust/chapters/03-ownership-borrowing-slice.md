# 03 - Ownership, Borrowing, Slice

## 1) 3 quy tắc ownership

1. Mỗi giá trị có một owner.
2. Chỉ có một owner tại một thời điểm.
3. Owner ra khỏi scope thì giá trị bị drop.

## 2) Move vs Copy

- `String`, `Vec<T>`: move khi gán/truyền hàm.
- `i32`, `bool`, `char`...: `Copy`.

```rust
let s1 = String::from("hi");
let s2 = s1; // move
// println!("{s1}"); // lỗi
```

## 3) Borrowing

```rust
fn len_of(s: &String) -> usize { s.len() }
fn push_ex(s: &mut String) { s.push('!'); }
```

Quy tắc mượn:
- Nhiều immutable reference **hoặc** 1 mutable reference.
- Reference luôn phải hợp lệ (no dangling reference).

## 4) Slice

```rust
let s = String::from("hello");
let h = &s[0..2]; // "he"
```

- `&str` là slice string UTF-8.
- Cần cẩn thận index byte vs ký tự Unicode.

## 5) Vì sao quan trọng?

Ownership + borrowing giúp Rust đạt:
- An toàn bộ nhớ không cần GC.
- Tránh data race từ compile-time.
- Hiệu năng gần C/C++.

## 6) Checklist

- [ ] Giải thích được move, copy, clone.
- [ ] Phân biệt `&T` và `&mut T`.
- [ ] Hiểu tại sao Rust cấm dangling reference.
