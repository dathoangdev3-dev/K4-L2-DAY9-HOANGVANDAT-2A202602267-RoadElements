# So sánh lane

> Các số dưới đây là số của công cụ so sánh, không phải ngưỡng chấm.

Reference lane do người thiết kế lab vẽ theo card 1 trên 6 ảnh core, KHÔNG phải GT chính thức BDD100K. Khác reference chưa chắc là bạn sai: ghi who_is_right và lý do.

Trùng từng đỉnh với reference: 0/1 shape (<= 0,5 px).

## bb890202-d9d48310.jpg

- B-tag: weather: bạn clear, reference partly cloudy — gợi ý `attribute`
- R1: bạn thiếu polyline reference — gợi ý `missing`
- R2: bạn thiếu polyline reference — gợi ý `missing`
- R3: bạn thiếu polyline reference — gợi ý `missing`
- R4: bạn thiếu polyline reference — gợi ý `missing`
- R5: bạn thiếu polyline reference — gợi ý `missing`
- R6: bạn thiếu polyline reference — gợi ý `missing`
- B1: polyline bạn vẽ không có trong reference — gợi ý `guideline_gap`

## c1589305-200e315b.jpg

- B-tag: weather: bạn clear, reference partly cloudy — gợi ý `attribute`
- R1: bạn thiếu polyline reference — gợi ý `missing`
- R2: bạn thiếu polyline reference — gợi ý `missing`
- R3: bạn thiếu polyline reference — gợi ý `missing`
- R4: bạn thiếu polyline reference — gợi ý `missing`
- R5: bạn thiếu polyline reference — gợi ý `missing`
- R6: bạn thiếu polyline reference — gợi ý `missing`

## c3cd6c82-b5d52beb.jpg

- B-tag: weather: bạn clear, reference overcast — gợi ý `attribute`
- R1: bạn thiếu polyline reference — gợi ý `missing`
- R2: bạn thiếu polyline reference — gợi ý `missing`
- R3: bạn thiếu polyline reference — gợi ý `missing`
- R4: bạn thiếu polyline reference — gợi ý `missing`

## b75f355e-b3f098b9.jpg

- B-tag: weather: bạn clear, reference partly cloudy — gợi ý `attribute`
- R1: bạn thiếu polyline reference — gợi ý `missing`
- R2: bạn thiếu polyline reference — gợi ý `missing`

## c0f739d8-6ff93525.jpg

- B-tag: weather: bạn clear, reference partly cloudy — gợi ý `attribute`
- R1: bạn thiếu polyline reference — gợi ý `missing`
- R2: bạn thiếu polyline reference — gợi ý `missing`

## c95fecc3-41401a5f.jpg

- B-tag: weather: bạn clear, reference overcast — gợi ý `attribute`
- R1: bạn thiếu polyline reference — gợi ý `missing`
- R2: bạn thiếu polyline reference — gợi ý `missing`
- R3: bạn thiếu polyline reference — gợi ý `missing`
- R4: bạn thiếu polyline reference — gợi ý `missing`
- R5: bạn thiếu polyline reference — gợi ý `missing`

## Dòng gợi ý cho comparison_log.csv

```csv
task,sample,object,difference,error_type,who_is_right,action,note
lane,bb890202-d9d48310.jpg,B-tag,"B-tag: weather: bạn clear, reference partly cloudy",attribute,,,
lane,bb890202-d9d48310.jpg,R1,R1: bạn thiếu polyline reference,missing,,,
lane,bb890202-d9d48310.jpg,R2,R2: bạn thiếu polyline reference,missing,,,
lane,bb890202-d9d48310.jpg,R3,R3: bạn thiếu polyline reference,missing,,,
lane,bb890202-d9d48310.jpg,R4,R4: bạn thiếu polyline reference,missing,,,
lane,bb890202-d9d48310.jpg,R5,R5: bạn thiếu polyline reference,missing,,,
lane,bb890202-d9d48310.jpg,R6,R6: bạn thiếu polyline reference,missing,,,
lane,bb890202-d9d48310.jpg,B1,B1: polyline bạn vẽ không có trong reference,guideline_gap,,,
lane,c1589305-200e315b.jpg,B-tag,"B-tag: weather: bạn clear, reference partly cloudy",attribute,,,
lane,c1589305-200e315b.jpg,R1,R1: bạn thiếu polyline reference,missing,,,
lane,c1589305-200e315b.jpg,R2,R2: bạn thiếu polyline reference,missing,,,
lane,c1589305-200e315b.jpg,R3,R3: bạn thiếu polyline reference,missing,,,
lane,c1589305-200e315b.jpg,R4,R4: bạn thiếu polyline reference,missing,,,
lane,c1589305-200e315b.jpg,R5,R5: bạn thiếu polyline reference,missing,,,
lane,c1589305-200e315b.jpg,R6,R6: bạn thiếu polyline reference,missing,,,
lane,c3cd6c82-b5d52beb.jpg,B-tag,"B-tag: weather: bạn clear, reference overcast",attribute,,,
lane,c3cd6c82-b5d52beb.jpg,R1,R1: bạn thiếu polyline reference,missing,,,
lane,c3cd6c82-b5d52beb.jpg,R2,R2: bạn thiếu polyline reference,missing,,,
lane,c3cd6c82-b5d52beb.jpg,R3,R3: bạn thiếu polyline reference,missing,,,
lane,c3cd6c82-b5d52beb.jpg,R4,R4: bạn thiếu polyline reference,missing,,,
lane,b75f355e-b3f098b9.jpg,B-tag,"B-tag: weather: bạn clear, reference partly cloudy",attribute,,,
lane,b75f355e-b3f098b9.jpg,R1,R1: bạn thiếu polyline reference,missing,,,
lane,b75f355e-b3f098b9.jpg,R2,R2: bạn thiếu polyline reference,missing,,,
lane,c0f739d8-6ff93525.jpg,B-tag,"B-tag: weather: bạn clear, reference partly cloudy",attribute,,,
lane,c0f739d8-6ff93525.jpg,R1,R1: bạn thiếu polyline reference,missing,,,
lane,c0f739d8-6ff93525.jpg,R2,R2: bạn thiếu polyline reference,missing,,,
lane,c95fecc3-41401a5f.jpg,B-tag,"B-tag: weather: bạn clear, reference overcast",attribute,,,
lane,c95fecc3-41401a5f.jpg,R1,R1: bạn thiếu polyline reference,missing,,,
lane,c95fecc3-41401a5f.jpg,R2,R2: bạn thiếu polyline reference,missing,,,
lane,c95fecc3-41401a5f.jpg,R3,R3: bạn thiếu polyline reference,missing,,,
lane,c95fecc3-41401a5f.jpg,R4,R4: bạn thiếu polyline reference,missing,,,
lane,c95fecc3-41401a5f.jpg,R5,R5: bạn thiếu polyline reference,missing,,,
```

Hãy điền `who_is_right`, `action`, `note`; loại lỗi chỉ là gợi ý.
