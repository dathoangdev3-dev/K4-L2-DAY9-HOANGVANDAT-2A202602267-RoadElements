# So sánh drivable

> Các số dưới đây là số của công cụ so sánh, không phải ngưỡng chấm.

Polygon BDD100K đổi từ toạ độ normalized sang pixel 1280×720. BDD không có tag needs_review.

Trùng từng đỉnh với reference: 0/1 shape (<= 0,5 px).

## c3cd6c82-b5d52beb.jpg

- direct: IoU 0.169; chỉ reference 57649 px; chỉ bạn 70030 px
- direct: vùng hình học khác reference (57649 px thiếu, 70030 px thừa) — gợi ý `geometry`
- alternative: IoU 0.000; chỉ reference 48138 px; chỉ bạn 0 px
- alternative: vùng hình học khác reference (48138 px thiếu, 0 px thừa) — gợi ý `geometry`
- mọi vùng: IoU 0.129; chỉ reference 105787 px; chỉ bạn 70030 px
- mọi vùng: vùng hình học khác reference (105787 px thiếu, 70030 px thừa) — gợi ý `geometry`

## c068a67b-03b6e200.jpg

- direct: IoU 0.000; chỉ reference 106153 px; chỉ bạn 0 px
- direct: vùng hình học khác reference (106153 px thiếu, 0 px thừa) — gợi ý `geometry`
- alternative: IoU 0.000; chỉ reference 59261 px; chỉ bạn 0 px
- alternative: vùng hình học khác reference (59261 px thiếu, 0 px thừa) — gợi ý `geometry`
- mọi vùng: IoU 0.000; chỉ reference 165414 px; chỉ bạn 0 px
- mọi vùng: vùng hình học khác reference (165414 px thiếu, 0 px thừa) — gợi ý `geometry`

## c723ad21-efed33e5.jpg

- direct: IoU 0.000; chỉ reference 136057 px; chỉ bạn 0 px
- direct: vùng hình học khác reference (136057 px thiếu, 0 px thừa) — gợi ý `geometry`
- alternative: IoU 0.000; chỉ reference 26105 px; chỉ bạn 0 px
- alternative: vùng hình học khác reference (26105 px thiếu, 0 px thừa) — gợi ý `geometry`
- mọi vùng: IoU 0.000; chỉ reference 162162 px; chỉ bạn 0 px
- mọi vùng: vùng hình học khác reference (162162 px thiếu, 0 px thừa) — gợi ý `geometry`

## bb5cc516-c98d1fbe.jpg

- direct: IoU 0.000; chỉ reference 41254 px; chỉ bạn 0 px
- direct: vùng hình học khác reference (41254 px thiếu, 0 px thừa) — gợi ý `geometry`
- alternative: IoU 0.000; chỉ reference 48786 px; chỉ bạn 0 px
- alternative: vùng hình học khác reference (48786 px thiếu, 0 px thừa) — gợi ý `geometry`
- mọi vùng: IoU 0.000; chỉ reference 90040 px; chỉ bạn 0 px
- mọi vùng: vùng hình học khác reference (90040 px thiếu, 0 px thừa) — gợi ý `geometry`

## be860305-899a96c3.jpg

- direct: IoU 0.000; chỉ reference 64633 px; chỉ bạn 0 px
- direct: vùng hình học khác reference (64633 px thiếu, 0 px thừa) — gợi ý `geometry`
- alternative: IoU 0.000; chỉ reference 39403 px; chỉ bạn 0 px
- alternative: vùng hình học khác reference (39403 px thiếu, 0 px thừa) — gợi ý `geometry`
- mọi vùng: IoU 0.000; chỉ reference 104036 px; chỉ bạn 0 px
- mọi vùng: vùng hình học khác reference (104036 px thiếu, 0 px thừa) — gợi ý `geometry`

## Dòng gợi ý cho comparison_log.csv

```csv
task,sample,object,difference,error_type,who_is_right,action,note
drivable,c3cd6c82-b5d52beb.jpg,direct,"direct: vùng hình học khác reference (57649 px thiếu, 70030 px thừa)",geometry,,,
drivable,c3cd6c82-b5d52beb.jpg,alternative,"alternative: vùng hình học khác reference (48138 px thiếu, 0 px thừa)",geometry,,,
drivable,c3cd6c82-b5d52beb.jpg,mọi vùng,"mọi vùng: vùng hình học khác reference (105787 px thiếu, 70030 px thừa)",geometry,,,
drivable,c068a67b-03b6e200.jpg,direct,"direct: vùng hình học khác reference (106153 px thiếu, 0 px thừa)",geometry,,,
drivable,c068a67b-03b6e200.jpg,alternative,"alternative: vùng hình học khác reference (59261 px thiếu, 0 px thừa)",geometry,,,
drivable,c068a67b-03b6e200.jpg,mọi vùng,"mọi vùng: vùng hình học khác reference (165414 px thiếu, 0 px thừa)",geometry,,,
drivable,c723ad21-efed33e5.jpg,direct,"direct: vùng hình học khác reference (136057 px thiếu, 0 px thừa)",geometry,,,
drivable,c723ad21-efed33e5.jpg,alternative,"alternative: vùng hình học khác reference (26105 px thiếu, 0 px thừa)",geometry,,,
drivable,c723ad21-efed33e5.jpg,mọi vùng,"mọi vùng: vùng hình học khác reference (162162 px thiếu, 0 px thừa)",geometry,,,
drivable,bb5cc516-c98d1fbe.jpg,direct,"direct: vùng hình học khác reference (41254 px thiếu, 0 px thừa)",geometry,,,
drivable,bb5cc516-c98d1fbe.jpg,alternative,"alternative: vùng hình học khác reference (48786 px thiếu, 0 px thừa)",geometry,,,
drivable,bb5cc516-c98d1fbe.jpg,mọi vùng,"mọi vùng: vùng hình học khác reference (90040 px thiếu, 0 px thừa)",geometry,,,
drivable,be860305-899a96c3.jpg,direct,"direct: vùng hình học khác reference (64633 px thiếu, 0 px thừa)",geometry,,,
drivable,be860305-899a96c3.jpg,alternative,"alternative: vùng hình học khác reference (39403 px thiếu, 0 px thừa)",geometry,,,
drivable,be860305-899a96c3.jpg,mọi vùng,"mọi vùng: vùng hình học khác reference (104036 px thiếu, 0 px thừa)",geometry,,,
```

Hãy điền `who_is_right`, `action`, `note`; loại lỗi chỉ là gợi ý.
