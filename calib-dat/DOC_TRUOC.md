# Bộ calibration — Đạt

Nhóm **4changlinhngulam** · Lab 9 · đề tài "Đèn nào điều khiển xe mình?"

## Trong gói có gì

| File / thư mục | Dùng để |
|---|---|
| `calibration/` | **7 ảnh cần label** (BDD09, BDD13, BDD15, BDD17, BDD18, BDD25, LISA30) |
| `examples/` | 4 ảnh ví dụ mà guideline nhắc tới (BDD02, LISA01, BDD11, BDD04) — chỉ để xem, **không** đưa vào task |
| `02_guideline.md` | Guideline v1 — đọc kỹ mục 5 (cây quyết định) và bảng frame trước khi vẽ |
| `03_cvat_labels.json` | Danh sách label — dán vào tab **Raw** |
| `GUIDE.md` | Hướng dẫn CVAT của coach (mục 2.2 tạo task, 2.3 dán Guide, 4 export) |

## Làm gì (khoảng 20 phút)

1. Bật CVAT local (Docker → `cvat-day2` → `docker compose start`), mở http://localhost:8080.
2. **Tasks → + → Create a new task**
   - **Name:** `4changlinhngulam-calib-dat`
   - **Labels:** tab **Raw** → xoá hết → dán **toàn bộ** `03_cvat_labels.json` → **Save**. Sang tab
     **Constructor** kiểm có `traffic_light` (state, relevance) và tag `frame` (ego_signal).
   - **Select files → My computer** → chọn **cả 7 ảnh** trong `calibration/`. Sorting giữ mặc định.
   - **Submit & Open**.
3. Trang task → **Task description → Edit** → dán toàn bộ `02_guideline.md` → **Submit**.
4. Label **độc lập**: không nhìn màn hình nhau, không bàn trước. Chỉ dựa vào chữ trong guideline.
   - Mỗi ảnh **đúng 1 tag `frame`**, chọn `ego_signal` (không để `__undefined__`).
   - Mỗi đèn trong scope: 1 rectangle `traffic_light`, chọn đủ `state` và `relevance`.
   - Không chắc → dùng `unknown` / `escalate` theo guideline, **không đoán**.
   - Ghi ra giấy chỗ nào guideline làm bạn phân vân — rất có ích cho v2.
5. **Ctrl+S**, rồi **Menu → Export job dataset** → **CVAT for images 1.1**, **Save images: TẮT**.
6. Đổi tên file tải về thành **`dat.zip`** (đúng chữ thường, không dấu) và gửi cho Quang.

⚠️ Chưa mở `project/04_edge_cases/edge_case_cards.md` trong repo trước khi export xong — trong đó có đáp án dự kiến.

Repo nhóm: https://github.com/cuducquang/K4-L2-DAY09-4changlinhngulam---RoadElements
