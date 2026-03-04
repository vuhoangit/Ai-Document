# 01 - Bắt đầu với Rust

## 1) Cài đặt

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustc --version
cargo --version
```

- `rustup`: quản lý toolchain (stable/beta/nightly).
- `rustc`: compiler.
- `cargo`: build system + package manager.

## 2) Vòng đời làm việc cơ bản

```bash
cargo new hello_rust
cd hello_rust
cargo run
cargo check
cargo test
cargo build --release
```

- `cargo check` nhanh vì chỉ kiểm tra kiểu và borrow.
- `--release` tối ưu hoá cho production.

## 3) Hello, world và formatting

```rust
fn main() {
    let name = "Rust";
    println!("Hello, {name}!");
}
```

- `println!` là macro.
- Nên format code bằng `cargo fmt`.

## 4) Dự án đoán số (ý tưởng chính)

Bạn sẽ học được:
- Input terminal bằng `std::io`.
- Parse chuỗi sang số với `parse::<u32>()`.
- So sánh số với `cmp`.
- Dùng `match` xử lý `Ordering`.
- Dùng crate `rand` để sinh số ngẫu nhiên.

## 5) Checklist

- [ ] Biết tạo/chạy/build một project Cargo.
- [ ] Phân biệt `cargo check` và `cargo build`.
- [ ] Biết thêm dependency vào `Cargo.toml`.
- [ ] Hiểu Rust compiler bắt lỗi sớm trước runtime.
