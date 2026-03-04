# 06. Đánh giá hệ thống RAG

## Vì sao cần đánh giá đa tầng?
RAG thất bại có thể do retrieval, prompt hoặc generation. Cần tách tầng đo để xác định nguyên nhân gốc.

## Chỉ số retrieval
- **Recall@k**: tỷ lệ câu hỏi có tài liệu đúng trong top-k.
- **Precision@k**: tỷ lệ tài liệu liên quan trong top-k.
- **MRR / nDCG**: đánh giá chất lượng thứ hạng.

## Chỉ số generation
- Faithfulness (mức độ bám nguồn).
- Answer relevance (mức độ trả lời đúng câu hỏi).
- Factual consistency (nhất quán với tài liệu tham chiếu).
- Format compliance (đúng định dạng yêu cầu).

## Đánh giá end-to-end
- Task success rate theo use-case thực tế.
- Latency p50/p95/p99.
- Cost per query theo mô hình và độ dài context.
- Tỷ lệ escalation sang human agent.

## Bộ dữ liệu đánh giá (eval set)
Nên bao gồm:
- Câu hỏi phổ biến, câu hỏi biên, câu hỏi đánh đố.
- Trường hợp thiếu dữ liệu để test khả năng “không bịa”.
- Trường hợp tài liệu mâu thuẫn để test cảnh báo độ chắc chắn.

## Quy trình cải tiến liên tục
1. Thu thập truy vấn thực tế + phản hồi người dùng.
2. Gắn nhãn lỗi theo taxonomy (retrieval miss, hallucination, policy violation).
3. Tối ưu retriever/prompt/index theo nhóm lỗi lớn nhất.
4. Chạy regression eval trước khi phát hành.
