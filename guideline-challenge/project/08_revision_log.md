# Revision log

Guideline v1 = bản nháp đầu; v2 = sau calibration nội bộ; v3 = sau blind handoff. Mỗi lần tăng `Version` trong
`02_guideline.md`, thêm một hoặc nhiều dòng vào bảng: đổi gì và vì sao, kèm bằng chứng (sample_id, dòng
calibration report, câu hỏi trong clarification log, feedback của peer).

Cột Version ghi dạng `v1`, `v2`, `v3` — `make status` tìm dòng bảng có `v2` và dòng có `v3`.

| Version | Đổi gì | Vì sao | Bằng chứng |
|---|---|---|---|
| v1 | Bản nháp đầu: class `traffic_light` (state, relevance) + tag `frame.ego_signal`; cây quyết định 5.1–5.4; rule 1/3; bảng frame | Chốt contract "đèn điều khiển ego ở vạch dừng kế tiếp" | `01_problem_statement.md`; khảo sát ảnh BDD02, BDD07, BDD11, BDD12, BDD26, LISA01/30 |
| v2 | Làm rõ rule out_of_view vs escalate: escalate chỉ khi đã có box ego mang màu xung đột; nếu không box được thì dùng out_of_view. Thêm ví dụ BDD25 (hai đầu đèn cùng cần vươn = cả hai ego) và BDD18 (ban đêm đốm mờ = 0 box + out_of_view) | Calibration: dat và quang bất đồng ở BDD18 (escalate vs out_of_view) và BDD25 (relevance other vs ego) | `06_calibration_report.csv` dòng 1–3; `06_calibration_measure.csv` |
| v3 | Thêm checklist trước export: mỗi ảnh có đúng 1 tag frame, mọi box có đủ attribute, rà lại đèn nhỏ/xa theo rule 5.3 và lưu task | Blind handoff: peer đánh giá guideline dễ theo nhưng export thiếu tag frame ở cả 4 ảnh và giữ box đèn nhỏ/xa ở BDD07, BDD21; checklist giúp giảm lỗi thao tác mà không đổi ontology hay gold | `07_blind_handoff/peer_feedback.md` câu 5; `07_blind_handoff/transfer_score.csv` BDD07/d2,d4; BDD21/d2,d4; BDD26/d4; BDD12/d2 |
