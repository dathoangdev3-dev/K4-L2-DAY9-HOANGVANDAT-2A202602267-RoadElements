# QC report

Họ tên: Hoàng Văn Đạt · Chế độ: cá nhân · Nếu nhóm — các thành viên: N/A
Guideline dùng: `GUIDE.md` + 4 card, bản phát ngày học.

Viết ở phút 205–225.

- **Cá nhân**: mở lại `submission/traffic_light/compare.html` sau khi vẽ xong — xem như bài của người khác.

## 1. Sample plan

Không đủ thời gian xem hết. Chọn **6 sample** và nói vì sao chọn. Lấy theo lát dễ lỗi (ngã tư, crosswalk, đêm/mưa,
lóa, biển nhỏ, điểm chuyển state), không lấy ngẫu nhiên.

| # | Task | Sample (ảnh / frame) | Lát (vì sao chọn) |
|---|---|---|---|
| 1 | traffic_light | dayClip5--01606.jpg | Frame đầu tiên — kiểm tra tất cả track khởi tạo đúng vị trí |
| 2 | traffic_light | dayClip5--01615.jpg | Frame ngay tại điểm chuyển state (frame 15) — dễ sai keyframe |
| 3 | traffic_light | dayClip5--01616.jpg | Frame ngay sau chuyển state — xác nhận green đã ổn định |
| 4 | traffic_light | dayClip5--01635.jpg | Frame cuối — kiểm tra outside đúng chỗ, không có box thừa |
| 5 | lane | bb890202-d9d48310.jpg | Ảnh ví dụ lane có mây nhẹ — kiểm tra tag weather |
| 6 | drivable | c3cd6c82-b5d52beb.jpg | IoU thấp nhất (0.169) — xem lại biên polygon direct |

## 2. Lỗi tìm thấy

Ít nhất 1 lỗi geometry, 1 lỗi attribute và 1 ca cần vào decision log. Nếu không tìm thấy loại nào, ghi rõ "đã xem,
không có".

| Task | Sample | Object | Mô tả lỗi | error_type | severity | action | Downstream sai gì nếu bỏ qua |
|---|---|---|---|---|---|---|---|
| drivable | c3cd6c82-b5d52beb.jpg | direct polygon | Polygon vẽ rộng hơn vạch sơn thật ~70.000 px — lấn sang vỉa hè bên phải | geometry | major | rework | Mô hình học vùng drivable bao gồm cả vỉa hè, xe có thể lên vỉa hè trong tình huống khẩn |
| lane | bb890202-d9d48310.jpg | image_context tag | weather=clear nhưng ảnh có mây nhẹ — nên là partly_cloudy | attribute | minor | rework | Model weather classifier học sai phân phối; ảnh partly_cloudy bị đếm vào clear |
| traffic_light | dayClip5--01606.jpg | B#5 | Đèn xa quá nhỏ, state=unknown — cần quy tắc ngưỡng kích thước tối thiểu | guideline_gap | minor | escalate | Annotator khác nhau sẽ quyết định vẽ hay không vẽ đèn xa không nhất quán |

## 3. Kết luận cho batch

- **Accept** batch traffic_light với 2 điều kiện: (1) sửa lại tag weather cho lane, (2) thêm quy tắc kích thước tối thiểu vào hướng dẫn để xử lý track #5.
- **Note cho người label:** Khi gán nhãn đèn xa, luôn gán `relevance=not_relevant` trước khi quyết định có vẽ box hay không — nếu relevance rõ ràng thì vẽ, nếu đèn quá nhỏ để đọc state thì bật `needs_review`.
- **Known limitation phải ghi khi handoff:** Hướng dẫn mini lab chưa định nghĩa ngưỡng kích thước tối thiểu cho đèn xa; track #5 (B#5) có `needs_review=true` cần người phụ trách xem xét trước khi đưa vào training set.
