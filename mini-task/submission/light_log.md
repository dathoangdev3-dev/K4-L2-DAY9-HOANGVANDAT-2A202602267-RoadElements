# Traffic light log

Họ tên: Hoàng Văn Đạt

Viết mục 1–3 trong mini-task traffic light, trước khi chạy `make compare TASK=traffic_light`; mục 4 viết sau compare. Mỗi track là một đầu đèn bạn đã
vẽ.

## 1. Các track

`state` theo frame: ghi dạng khoảng, ví dụ `red 0–14, green 15–29`. Frame đếm từ 0 như trong CVAT.

| Track (#id CVAT) | pictogram | state theo frame | relevance | Bằng chứng cho relevance |
|---|---|---|---|---|
| #0 | circle | red 0–14, green 15–29 | relevant | Đèn trên cần vươn chính giữa ngã tư, quay thẳng về hướng ego |
| #1 | circle | red 0–14, green 15–29 | relevant | Đèn thứ hai cùng cần vươn, cùng pha với #0, cùng điều khiển làn ego |
| #2 | circle | red 0–14, green 15–29 | relevant | Đèn bên phải cùng giao lộ, pha khớp với #0 và #1 |
| #3 | circle | red 0–29 | not_relevant | Đèn ngã tư phía xa, nhỏ hơn nhiều so với #0; điều khiển đường song song không phải làn ego |
| #4 | circle | red 0–29 | not_relevant | Đèn phía xa thứ hai, cùng ngã tư sau với #3 |
| #5 | circle | unknown 0–29 | not_relevant | Đèn xa nhất, kích thước rất nhỏ, không đọc được màu chắc chắn |

## 2. Điểm chuyển state

- Đèn đổi state tại frame 15. Frame 14 trông ra sao: ô đỏ vẫn còn sáng rõ, chưa thấy ô xanh. Frame 15: ô xanh bật rõ, ô đỏ tắt. Không có khoảng LED nhấp nháy giữa hai state.
- Keyframe đặt tại frame 0 (red) và frame 15 (green). Đã kiểm tra các frame 1–14 đều ở trạng thái red và frame 15–29 đều ở trạng thái green — không cần thêm keyframe giữa chừng.

## 3. Các đầu đèn nhỏ ở ngã tư phía xa

Có vẽ track #3, #4, #5 cho 3 đầu đèn nhỏ ở ngã tư phía xa. Tất cả gán `relevance=not_relevant` vì thuộc ngã tư sau, không điều khiển làn ego tại giao lộ đầu tiên. Track #3 và #4 đọc được state=red xuyên suốt 30 frame. Track #5 quá nhỏ và mờ, không đọc được màu — gán `state=unknown` và bật `needs_review`.

## 4. Sau khi so với reference

- **Khác biệt về state/pictogram:** frame đổi state reference=15, bạn=15 — khớp hoàn toàn. Pictogram không có trong reference nên không so được, giữ nguyên `circle` cho tất cả track.
- **Track của bạn không có trong reference (B#3/B#4/B#5):** giữ lại. LISA không gán đèn xa nhưng hướng dẫn mini lab không cấm. Ba track này có `relevance=not_relevant` rõ ràng và giúp mô hình học phân biệt đèn điều khiển ego với đèn không liên quan — có giá trị về mặt dữ liệu huấn luyện.
