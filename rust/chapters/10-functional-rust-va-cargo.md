# 10 - Functional Rust và Cargo/crates.io

## 1) Closure

```rust
let add = |a: i32, b: i32| a + b;
assert_eq!(add(2, 3), 5);
```

- Closure có thể capture môi trường.
- Có 3 trait quan trọng: `Fn`, `FnMut`, `FnOnce`.

## 2) Iterator

```rust
let nums = vec![1,2,3,4,5];
let sum_even: i32 = nums.iter().filter(|x| **x % 2 == 0).sum();
```

- Lazy evaluation.
- Dùng adapter: `map`, `filter`, `take`, `zip`.
- Consumer: `collect`, `sum`, `fold`, `for_each`.

## 3) Cargo nâng cao

- Profiles: `[profile.dev]`, `[profile.release]`.
- Workspace cho mono-repo nhiều crate.
- `cargo doc --open` sinh tài liệu API.
- `cargo install` cài binary crates.

## 4) crates.io

- Chuẩn bị metadata trong `Cargo.toml`.
- SemVer: MAJOR.MINOR.PATCH.
- Viết docs tốt để crate dễ dùng.

## 5) Checklist

- [ ] Viết được pipeline iterator.
- [ ] Hiểu khi nào closure move/capture mutable.
- [ ] Biết publish và versioning crate.
