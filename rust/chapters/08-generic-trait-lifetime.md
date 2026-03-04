# 08 - Generic, Trait, Lifetime

## 1) Generic

```rust
fn largest<T: PartialOrd + Copy>(list: &[T]) -> T {
    let mut largest = list[0];
    for &item in list {
        if item > largest { largest = item; }
    }
    largest
}
```

## 2) Trait

```rust
trait Summary {
    fn summarize(&self) -> String;
}
```

- Trait giống interface hành vi.
- Trait bound: `fn f<T: Summary>(x: &T)`.
- `impl Trait` giúp chữ ký ngắn gọn.

## 3) Lifetime

```rust
fn longest<'a>(x: &'a str, y: &'a str) -> &'a str {
    if x.len() > y.len() { x } else { y }
}
```

- Lifetime mô tả quan hệ sống giữa references.
- Không kéo dài tuổi thọ dữ liệu, chỉ mô tả ràng buộc.
- Lifetime elision rules giảm nhu cầu annotate thủ công.

## 4) Checklist

- [ ] Dùng generic để loại bỏ lặp mã an toàn kiểu.
- [ ] Viết và dùng trait như contract hành vi.
- [ ] Hiểu lỗi borrow checker liên quan lifetime cơ bản.
