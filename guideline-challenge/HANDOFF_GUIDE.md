# Hướng dẫn làm thử bài Blind Handoff — Nhóm 4changlinhngulam

> Bài này dành cho **team peer** nhận file `blind-pack.zip` từ nhóm 4changlinhngulam.  
> Mục tiêu: gắn nhãn 4 ảnh blind trong **15 phút** chỉ dựa vào tài liệu trong pack — không hỏi thêm về quy tắc domain.

---

## 1. Nhận được gì

File `blind-pack.zip` chứa:

| File | Nội dung |
|---|---|
| `images/BDD07.jpg` | Ảnh blind 1 |
| `images/BDD26.jpg` | Ảnh blind 2 |
| `images/BDD21.jpg` | Ảnh blind 3 |
| `images/BDD12.jpg` | Ảnh blind 4 |
| `cvat_labels.json` | Bộ nhãn — dán vào CVAT |
| `guideline.md` | Hướng dẫn gắn nhãn đầy đủ |
| `PEER_README.md` | Tóm tắt quy trình |

---

## 2. Chuẩn bị CVAT (5 phút)

1. Mở **Docker Desktop**, chờ engine chạy xong
2. Mở terminal, vào thư mục CVAT đã cài từ Day 2:
   ```bash
   cd <thư-mục-cvat-day2>
   docker compose start
   ```
3. Mở `http://localhost:8080` trên trình duyệt → đăng nhập
4. Tạo **Task mới**:
   - Tên task: `peer-<tên-bạn>-4changlinhngulam` (ví dụ `peer-an-4changlinhngulam`)
   - Kéo thả 4 file ảnh từ thư mục `images/` vào mục **Files**
5. Dán bộ nhãn vào **Labels → Raw**:
   - Mở file `cvat_labels.json`, copy toàn bộ nội dung
   - Trong CVAT: Labels → Raw → paste → Save
6. Dán nội dung `guideline.md` vào trường **Guide** của task → Save

---

## 3. Gắn nhãn (15 phút)

**Đọc `guideline.md` trước** — đặc biệt mục 4 (taxonomy), mục 5 (cây quyết định 5.1–5.4) và mục 9 (ví dụ).

### Workflow cho mỗi ảnh:

```
Với mỗi nguồn sáng / vỏ đèn nhìn thấy:
  5.1 → Có phải đèn cho xe không? (không = IGNORE)
  5.2 → Thấy mặt ô đèn không? (không = IGNORE)  
  5.3 → Thuộc giao lộ đầu tiên không? (nhỏ hơn 1/3 = IGNORE)
  5.4 → Chọn relevance: ego / other / unknown
→ Vẽ Rectangle box ôm sát vỏ đèn
→ Điền state: red / yellow / green / unknown
→ Điền relevance: ego / other / unknown

Sau khi xử lý hết → Thêm tag frame:
→ Nhấn nút Tag (chữ T) → chọn label "frame"
→ Điền ego_signal theo bảng trong guideline mục 4
```

### Lưu ý quan trọng:

- ✅ Dùng **Shape** (Rectangle), **không** dùng Track
- ✅ Mỗi ảnh phải có **đúng 1 tag `frame`** — kể cả ảnh không có đèn nào
- ✅ Không để attribute nào còn `__undefined__` trước khi Save
- ✅ Nhấn **Ctrl+S** thường xuyên để lưu
- ❌ Không box đèn đi bộ (bàn tay/người — hình vuông, màu cam/trắng)
- ❌ Không box vỏ đèn quay ngang hoặc quay lưng
- ❌ Không box bóng phản chiếu trên capo hoặc đường ướt

---

## 4. Export kết quả

1. Trong CVAT: **Menu → Export job dataset**
2. Chọn format: **CVAT for images 1.1**
3. Tải về file ZIP
4. Đặt tên file: `peer-<tên-bạn>.zip` (ví dụ `peer-an.zip`)

---

## 5. Ghi câu hỏi trong quá trình làm

Nếu gặp chỗ hướng dẫn chưa rõ, **ghi lại ngay** (đừng hỏi owner):

- Ảnh nào?
- Câu hướng dẫn nào bạn đọc nhưng vẫn không quyết được?
- Bạn đã làm thế nào?

---

## 6. Gửi lại cho nhóm 4changlinhngulam

Gửi kèm:
1. File ZIP export (`peer-<tên-bạn>.zip`)
2. Trả lời 5 câu hỏi sau (có thể ghi thẳng vào email/message):

```
1. Rule nào rõ nhất / giúp quyết định nhanh nhất?
   →

2. Rule nào mơ hồ hoặc phải tự suy diễn?
   →

3. Sample nào khiến guideline "vỡ" (làm theo đúng hướng dẫn nhưng vẫn không chắc)?
   →

4. Attribute / default nào trong CVAT dễ gây thao tác sai?
   →

5. Một thay đổi cụ thể giúp annotator mới ít hỏi hơn?
   →
```

---

## 7. Lỗi thường gặp

| Lỗi | Cách xử lý |
|---|---|
| Không mở được CVAT | Mở Docker Desktop → chờ engine xanh → `docker compose start` lại |
| Paste labels không nhận | Đảm bảo copy toàn bộ JSON kể cả dấu `[` đầu và `]` cuối |
| Không thấy nút Tag | Nhấn phím `T` hoặc chọn biểu tượng nhãn trên thanh công cụ trái |
| Export bị lỗi | Nhấn Ctrl+S trước rồi thử export lại |
| Không chắc ảnh này có đèn không | Đọc ví dụ BDD11 và BDD04 trong `guideline.md` mục 9 |

---

## 8. Thời gian tham khảo

| Việc | Thời gian |
|---|---|
| Đọc guideline (mục 4, 5, 9) | 3 phút |
| Setup CVAT task | 3 phút |
| Gắn nhãn 4 ảnh | 15 phút |
| Export + điền 5 câu hỏi | 4 phút |
| **Tổng** | **~25 phút** |

---

*Câu hỏi về kỹ thuật CVAT (không liên quan domain): hỏi Lab Coach. Câu hỏi về domain rule: ghi lại và gửi kèm khi trả bài.*
