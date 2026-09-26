# Peer feedback + owner response

Phần 1 ghi nhận phản hồi nhóm peer do owner chuyển lại; phần 2 phân loại phản hồi và các decision sai dựa trên export.

- **Nhóm peer:** 1000
- **Người label blind:** Nguyễn Chí Bằng
- **Export:** `peer_output/rat_chuan.zip`

## 1. Peer trả lời

Nhận xét của Nguyễn Chí Bằng: bài của nhóm 4changlinhngulam được chuẩn bị rất chỉn chu, guideline rõ ràng và dễ làm theo; mình có thể hoàn tất phần gắn nhãn thuận lợi. Các bước và ví dụ giúp người mới nắm cách xử lý mà không cần owner giải thích thêm.

1. Rule nào rõ nhất / giúp quyết định nhanh nhất? Cây quyết định 5.1–5.4 trình bày từng bước rõ ràng, giúp phân biệt đèn cần gắn nhãn với đèn đi bộ, đèn quay ngang và đèn ở xa.
2. Rule nào mơ hồ hoặc phải tự suy diễn? Nhìn chung các rule dễ hiểu; trong lúc làm, mình không gặp điểm nào buộc phải dừng lại để hỏi owner.
3. Sample nào khiến guideline "vỡ"? Không có sample nào khiến mình không biết áp dụng guideline như thế nào.
4. Attribute / default nào trong CVAT dễ gây thao tác sai? Các attribute và giá trị lựa chọn được mô tả rõ; mình không gặp trở ngại đáng kể khi điền.
5. Một thay đổi cụ thể giúp annotator mới ít hỏi hơn? Guideline hiện tại đã dễ theo. Có thể thêm checklist ngắn trước khi export để người gắn nhãn rà lại attribute và tag cho từng ảnh.

## 2. Owner phân loại

Owner không tranh luận để bảo vệ guideline. Decision sai dưới đây được so với gold đã freeze; execution error hiện tại chưa đủ bằng chứng để kết luận guideline gap.

| Feedback / decision sai | Nguyên nhân (guideline gap / data ambiguity / execution error) | Xử lý (accept + revise / reject with evidence / add escalation rule) | Bằng chứng |
|---|---|---|---|
| Đánh giá tích cực: guideline chỉn chu, dễ theo; cây quyết định hữu ích | Phản hồi tích cực, không phải defect | Accept; giữ guideline hiện tại | Peer feedback của Nguyễn Chí Bằng, nhóm 1000 |
| Gợi ý checklist trước khi export để rà attribute và tag | execution_error (biện pháp phòng ngừa) | Accept làm bước QA cuối; không thay đổi gold đã freeze | Peer feedback câu 5; export thiếu tag frame ở 4/4 ảnh |
| BDD07/d2: giữ lại 2 đèn nhỏ/xa, tổng 4 box thay vì 2 | execution_error | Coaching; giữ rule 5.3 | `transfer_score.csv` d2 và export: 2 box extra có state=unknown, relevance=ego |
| BDD07/d4: thiếu tag `frame` | execution_error | Coaching; nhắc kiểm tag từng ảnh khi hoàn tất | `transfer_score.csv` d4; export BDD07 không có tag |
| BDD07/g1: box geometry vượt tolerance ở cạnh phải | execution_error | Coaching; nhắc box visible extent và tolerance đã ghi | `transfer_score.csv` g1; cạnh phải x261.18 so với gold khoảng x240, lệch khoảng 21 px |
| BDD26/d4: thiếu tag `frame` | execution_error | Coaching; nhắc kiểm tag từng ảnh khi hoàn tất | `transfer_score.csv` d4; export BDD26 không có tag |
| BDD21/d2: gắn ego cho đèn xanh nhỏ dưới ngưỡng 1/3 | execution_error | Coaching; giữ rule 5.3 | `transfer_score.csv` d2; export có 2 box ego thay vì 1 |
| BDD21/d4: thiếu tag `frame` | execution_error | Coaching; nhắc kiểm tag từng ảnh khi hoàn tất | `transfer_score.csv` d4; export BDD21 không có tag |
| BDD12/d2: thiếu tag `frame [ego_signal=out_of_view]` | execution_error | Coaching; nhắc tag cả ảnh kể cả khi không có box | `transfer_score.csv` d2; export BDD12 không có tag |
