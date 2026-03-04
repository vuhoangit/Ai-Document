# 13. Use case: RAG cho tài liệu nội bộ doanh nghiệp

## Bài toán
Doanh nghiệp có nhiều nguồn tri thức rời rạc:
- Wiki nội bộ.
- Tài liệu quy trình (SOP).
- Biên bản họp, email hướng dẫn.
- Tài liệu chính sách và tuân thủ.

Người dùng khó tìm đúng tài liệu và mất thời gian xác minh thông tin.

## Thiết kế khuyến nghị
1. Gom dữ liệu theo miền nghiệp vụ: HR, pháp chế, vận hành, kỹ thuật.
2. Mỗi miền có metadata chuẩn: owner, phiên bản, mức độ nhạy cảm.
3. Áp dụng ACL theo vai trò người dùng.
4. Trả lời có trích dẫn nguồn và đường dẫn tài liệu gốc.

## Rủi ro thường gặp
- Truy cập sai quyền do metadata ACL không đầy đủ.
- Tài liệu cũ nhưng vẫn được retrieve do thiếu versioning.
- Trả lời “đúng ngữ nghĩa nhưng sai chính sách hiện hành”.

## Kế hoạch vận hành
- Thiết lập lịch đồng bộ dữ liệu theo từng nguồn.
- Có quy trình review nội dung lỗi do người dùng báo cáo.
- Theo dõi câu hỏi chưa trả lời được để mở rộng kho tri thức.
