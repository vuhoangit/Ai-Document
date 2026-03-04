# 07 - Xử lý lỗi

## 1) `panic!` vs `Result`

- `panic!`: dừng chương trình (unrecoverable error).
- `Result<T, E>`: lỗi có thể xử lý.

## 2) Đọc file an toàn

```rust
use std::fs::File;
use std::io::{self, Read};

fn read_username(path: &str) -> Result<String, io::Error> {
    let mut f = File::open(path)?;
    let mut s = String::new();
    f.read_to_string(&mut s)?;
    Ok(s)
}
```

- Toán tử `?` giúp propagate lỗi.
- Có thể trả `Result` từ `main`.

## 3) Khi nào panic?

- Khi trạng thái “không thể xảy ra” bị vi phạm.
- Khi invariant nội bộ bị phá vỡ và không thể recovery hợp lý.

## 4) Custom error

- Dùng enum để gom nhiều loại lỗi.
- Implement `std::error::Error`/`Display` khi làm library.
- Ứng dụng thực tế thường dùng `thiserror` hoặc `anyhow`.

## 5) Checklist

- [ ] Không lạm dụng `unwrap`/`expect` trong production path.
- [ ] Dùng `?` để code gọn và rõ.
- [ ] Chọn panic hay Result dựa trên khả năng recovery.
