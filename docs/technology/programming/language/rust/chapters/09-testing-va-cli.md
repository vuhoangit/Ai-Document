# 09 - Testing và dự án CLI

## 1) Unit test

```rust
#[cfg(test)]
mod tests {
    #[test]
    fn it_works() {
        assert_eq!(2 + 2, 4);
    }
}
```

## 2) Integration test

- Đặt trong thư mục `tests/`.
- Kiểm thử public API như người dùng thật.

## 3) Mẹo test hữu ích

- `cargo test -- --nocapture` để xem output.
- `#[should_panic]` cho case panic mong đợi.
- Test theo tên: `cargo test name_fragment`.

## 4) Dự án CLI `minigrep`

Bạn nên tách:
- Parse config.
- Logic tìm kiếm.
- Hàm `run` trả `Result`.

Điều này giúp:
- Test độc lập.
- Main gọn.
- Quản lý lỗi rõ ràng.

## 5) Checklist

- [ ] Viết được unit + integration tests.
- [ ] Tách business logic khỏi I/O để test.
- [ ] Thiết kế CLI với cấu hình qua args/env.
