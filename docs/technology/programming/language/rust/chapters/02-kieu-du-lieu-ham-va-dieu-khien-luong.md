# 02 - Kiểu dữ liệu, hàm và điều khiển luồng

## 1) Biến, hằng, shadowing

```rust
let x = 5;      // immutable
let mut y = 10; // mutable
const MAX: u32 = 100;
let x = x + 1;  // shadowing
```

- Mặc định immutable giúp code an toàn hơn.
- `const` cần kiểu tường minh và là compile-time constant.

## 2) Kiểu dữ liệu

### Scalar
- Signed/unsigned integers: `i8..i128`, `u8..u128`, `isize`, `usize`.
- Float: `f32`, `f64`.
- `bool`, `char` (Unicode scalar value).

### Compound
- Tuple: `(i32, f64, u8)`.
- Array: `[T; N]`.

## 3) Hàm và expression

```rust
fn add(a: i32, b: i32) -> i32 {
    a + b // expression trả về
}
```

- Rust phân biệt statement và expression.
- Nhiều lỗi logic được tránh nhờ yêu cầu kiểu trả về rõ ràng.

## 4) Điều khiển luồng

- `if/else`: điều kiện phải là `bool`.
- `loop`: lặp vô hạn, dùng `break` để thoát.
- `while`: lặp có điều kiện.
- `for`: duyệt collection, range.

```rust
let mut n = 0;
let res = loop {
    n += 1;
    if n == 3 { break n * 2; }
};
assert_eq!(res, 6);
```

## 5) Checklist

- [ ] Nắm kiểu dữ liệu thường dùng.
- [ ] Biết viết hàm có kiểu trả về.
- [ ] Hiểu `loop` có thể trả giá trị.
