# 11 - Smart Pointer, Concurrency, OOP, Pattern nâng cao

## 1) Smart Pointer

- `Box<T>`: heap allocation.
- `Rc<T>`: shared ownership single-thread.
- `RefCell<T>`: interior mutability (borrow check runtime).
- `Arc<T>`: shared ownership multi-thread.
- `Mutex<T>`/`RwLock<T>`: đồng bộ truy cập dữ liệu.

```rust
use std::rc::Rc;
let a = Rc::new(String::from("data"));
let _b = Rc::clone(&a);
```

## 2) Drop và Deref

- `Drop` để cleanup tài nguyên tự động.
- `Deref` cho deref coercion giúp API ergonomic.

## 3) Concurrency

- Thread: `std::thread::spawn`.
- Kênh message: `std::sync::mpsc`.
- Shared state: `Arc<Mutex<T>>`.
- `Send`/`Sync` là marker trait quan trọng cho thread safety.

## 4) OOP trong Rust

Rust hỗ trợ “OOP style” qua:
- Encapsulation bằng module + visibility.
- Polymorphism qua trait objects `dyn Trait`.
- Reuse hành vi qua default method trong trait.

## 5) Pattern nâng cao

- `if let`, `while let`, `let-else`.
- Match guard.
- Ignore/binding pattern (`_`, `..`, `@`).

## 6) Checklist

- [ ] Chọn đúng smart pointer theo ownership model.
- [ ] Tránh deadlock và lock quá rộng.
- [ ] Dùng trait object khi cần runtime polymorphism.
