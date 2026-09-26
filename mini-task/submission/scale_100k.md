# Nếu scale lên 100k frames

Họ tên: Hoàng Văn Đạt

Mỗi mini-task trả lời một câu: **"Nếu scale lên 100k frames, lỗi nào sẽ trở thành systematic defect?"** Viết ngay sau
khi ghi comparison log của task đó. Dựa vào một lỗi bạn **thật sự** gặp hôm nay.

Mỗi câu trả lời có 3 phần: lỗi (và bằng chứng: task + sample), vì sao nó lặp lại có hệ thống thay vì ngẫu nhiên,
và cách phát hiện sớm (lát nào cần oversample, tín hiệu QC nào).

## Lane

**Lỗi:** Gắn tag `weather=clear` cho ảnh có mây nhẹ thay vì `partly_cloudy` — gặp ở `lane / bb890202-d9d48310.jpg`.

**Vì sao lặp lại có hệ thống:** Người gán nhãn thường ưu tiên quan sát mặt đường hơn bầu trời; khi bầu trời không phải tiêu điểm chính, xu hướng là chọn giá trị mặc định (clear) mà không nhìn kỹ. Trên 100k frame, đây sẽ là lỗi attribute phổ biến nhất vì nó không gây lỗi hình học rõ ràng để phát hiện.

**Cách phát hiện sớm:** Oversample ảnh buổi chiều và ngày có mây nhẹ trong batch QC. Tín hiệu cảnh báo: tỷ lệ `partly_cloudy` dưới 15% trong tập dữ liệu ban ngày là bất thường — nên kiểm tra lại.

## Drivable area

**Lỗi:** Vùng `direct` vẽ quá rộng so với vạch sơn thật, IoU chỉ đạt 0.169 — gặp ở `drivable / c3cd6c82-b5d52beb.jpg`. Bài làm thừa 70.030 px ngoài vùng reference.

**Vì sao lặp lại có hệ thống:** Khi không có xe phía trước làm mốc, người gán nhãn thường kéo polygon đến đường chân trời thay vì dừng tại điểm hết làn rõ ràng. Trên 100k frame, mô hình sẽ học vùng drivable rộng hơn thực tế, gây phantom lane extension.

**Cách phát hiện sớm:** Theo dõi diện tích trung bình của vùng `direct` theo loại cảnh (đường thẳng, nút giao, có xe phía trước). Đột biến diện tích lớn hơn 30% median là tín hiệu cần QC lại.

## Traffic sign

**Lỗi:** Bỏ sót nhiều biển báo nhỏ ở xa và ở mép ảnh — gặp ở `traffic_sign / 00073.png` (thiếu 5-6 biển so với reference GTSDB).

**Vì sao lặp lại có hệ thống:** Người gán nhãn thường quét ảnh từ trung tâm ra; biển nhỏ dưới 20px ở mép ảnh dễ bị bỏ qua vì mắt tập trung vào vùng trung tâm đường. Trên 100k frame, false negative sẽ tích luỹ đặc biệt ở ảnh đường cao tốc có nhiều biển ở xa.

**Cách phát hiện sớm:** So recall theo vùng ảnh (chia 9 ô). Nếu recall vùng mép (ô ngoài) thấp hơn 20% so với vùng trung tâm thì cần nhắc annotator quét kỹ 4 góc ảnh trước khi submit.

## Traffic light

**Lỗi:** Bài làm vẽ thêm 3 đèn nhỏ ở ngã tư phía xa (B#3, B#4, B#5) mà reference LISA không gán nhãn — gặp ở `traffic_light / dayClip5--01606.jpg`.

**Vì sao lặp lại có hệ thống:** LISA không có quy tắc rõ về kích thước tối thiểu của đèn cần gán nhãn. Khi hướng dẫn không nêu ngưỡng cụ thể, annotator sẽ quyết định khác nhau — người thận trọng vẽ thêm, người tiết kiệm thời gian bỏ qua. Trên 100k frame, inconsistency này gây precision thấp cho đèn `not_relevant`.

**Cách phát hiện sớm:** Theo dõi tỷ lệ `relevance=not_relevant` / tổng track. Nếu tỷ lệ này dao động lớn giữa annotator (>2x) thì cần thêm quy tắc ngưỡng kích thước tối thiểu vào hướng dẫn.
