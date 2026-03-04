# 05. Sinh câu trả lời: Prompting và kiểm soát chất lượng

## Prompt template khuyến nghị
Một prompt cho RAG nên có:
1. Vai trò hệ thống (system role) rõ ràng.
2. Nguyên tắc bắt buộc bám sát nguồn.
3. Khung trả lời (format) nhất quán.
4. Danh sách ngữ cảnh đã truy hồi.
5. Quy tắc xử lý khi thiếu thông tin.

## Kỹ thuật giảm hallucination
- Yêu cầu “chỉ trả lời từ ngữ cảnh cung cấp”.
- Nếu không đủ bằng chứng, phải nói “không đủ thông tin”.
- Bắt buộc trích dẫn nguồn theo từng luận điểm chính.
- Không cho phép suy đoán vượt phạm vi dữ liệu.

## Mẫu chính sách trả lời an toàn
- Không tiết lộ thông tin nhạy cảm (PII, secret nội bộ).
- Từ chối nội dung vi phạm pháp luật/chính sách.
- Escalate sang con người khi truy vấn vượt phạm vi cho phép.

## Hậu xử lý (post-processing)
- Kiểm tra định dạng JSON/Markdown nếu yêu cầu cấu trúc.
- Chuẩn hóa style và độ dài câu trả lời.
- Chèn danh mục nguồn tham chiếu ở cuối câu trả lời.

## Mẫu output gợi ý
- **Kết luận ngắn**: 1–2 câu.
- **Chi tiết**: các ý chính có trích dẫn.
- **Nguồn**: danh sách tài liệu/chunk liên quan.
- **Lưu ý**: mức độ chắc chắn, điểm chưa rõ.
