# So sánh traffic_sign

> Các số dưới đây là số của công cụ so sánh, không phải ngưỡng chấm.

Box GTSDB (43 class Đức). GT không có readable, truncated, relevant_to_ego — các attribute này tự đối chiếu bằng decision log.

Trùng từng đỉnh với reference: 0/6 shape (<= 0,5 px).

## 00073.png

- readable, truncated, relevant_to_ego: GT không có, không so — tự đối chiếu bằng decision log
- R1: bạn thiếu biển có trong reference — gợi ý `missing`
- R2: bạn thiếu biển có trong reference — gợi ý `missing`
- R3: bạn thiếu biển có trong reference — gợi ý `missing`
- R4: bạn thiếu biển có trong reference — gợi ý `missing`
- R5: bạn thiếu biển có trong reference — gợi ý `missing`
- R6: bạn thiếu biển có trong reference — gợi ý `missing`
- B1: box bạn vẽ không có trong reference — gợi ý `guideline_gap`

## 00206.png

- readable, truncated, relevant_to_ego: GT không có, không so — tự đối chiếu bằng decision log
- R1: bạn thiếu biển có trong reference — gợi ý `missing`
- R2: bạn thiếu biển có trong reference — gợi ý `missing`
- R3: bạn thiếu biển có trong reference — gợi ý `missing`
- R4: bạn thiếu biển có trong reference — gợi ý `missing`
- R5: bạn thiếu biển có trong reference — gợi ý `missing`
- B1: box bạn vẽ không có trong reference — gợi ý `guideline_gap`

## 00054.png

- readable, truncated, relevant_to_ego: GT không có, không so — tự đối chiếu bằng decision log
- R1: bạn thiếu biển có trong reference — gợi ý `missing`
- R2: bạn thiếu biển có trong reference — gợi ý `missing`
- R3: bạn thiếu biển có trong reference — gợi ý `missing`
- R4: bạn thiếu biển có trong reference — gợi ý `missing`
- B1: box bạn vẽ không có trong reference — gợi ý `guideline_gap`

## 00088.png

- readable, truncated, relevant_to_ego: GT không có, không so — tự đối chiếu bằng decision log
- R1: bạn thiếu biển có trong reference — gợi ý `missing`
- R2: bạn thiếu biển có trong reference — gợi ý `missing`
- R3: bạn thiếu biển có trong reference — gợi ý `missing`
- R4: bạn thiếu biển có trong reference — gợi ý `missing`
- B1: box bạn vẽ không có trong reference — gợi ý `guideline_gap`

## 00026.png

- readable, truncated, relevant_to_ego: GT không có, không so — tự đối chiếu bằng decision log
- R1: bạn thiếu biển có trong reference — gợi ý `missing`
- B1: box bạn vẽ không có trong reference — gợi ý `guideline_gap`

## 00223.png

- readable, truncated, relevant_to_ego: GT không có, không so — tự đối chiếu bằng decision log
- R1: bạn thiếu biển có trong reference — gợi ý `missing`
- B1: box bạn vẽ không có trong reference — gợi ý `guideline_gap`

## Dòng gợi ý cho comparison_log.csv

```csv
task,sample,object,difference,error_type,who_is_right,action,note
traffic_sign,00073.png,R1,R1: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00073.png,R2,R2: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00073.png,R3,R3: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00073.png,R4,R4: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00073.png,R5,R5: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00073.png,R6,R6: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00073.png,B1,B1: box bạn vẽ không có trong reference,guideline_gap,,,
traffic_sign,00206.png,R1,R1: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00206.png,R2,R2: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00206.png,R3,R3: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00206.png,R4,R4: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00206.png,R5,R5: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00206.png,B1,B1: box bạn vẽ không có trong reference,guideline_gap,,,
traffic_sign,00054.png,R1,R1: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00054.png,R2,R2: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00054.png,R3,R3: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00054.png,R4,R4: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00054.png,B1,B1: box bạn vẽ không có trong reference,guideline_gap,,,
traffic_sign,00088.png,R1,R1: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00088.png,R2,R2: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00088.png,R3,R3: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00088.png,R4,R4: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00088.png,B1,B1: box bạn vẽ không có trong reference,guideline_gap,,,
traffic_sign,00026.png,R1,R1: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00026.png,B1,B1: box bạn vẽ không có trong reference,guideline_gap,,,
traffic_sign,00223.png,R1,R1: bạn thiếu biển có trong reference,missing,,,
traffic_sign,00223.png,B1,B1: box bạn vẽ không có trong reference,guideline_gap,,,
```

Hãy điền `who_is_right`, `action`, `note`; loại lỗi chỉ là gợi ý.
