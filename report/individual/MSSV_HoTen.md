# Báo cáo cá nhân — HoVaTen-MSSV

Đổi tên file theo quy tắc `MSSV_HoTen.md`. Ví dụ: `20241234_NguyenVanAn.md`.

Đoạn video: MOT17-09, 150 frame (frame 1–150), nguồn MOTChallenge, giấy phép CC BY-NC-SA 3.0.

## 0. Thông tin học viên

- Họ tên:
- MSSV:
- Mã đề (A/B/C):
- Email:
- Link repository:
- Giờ bắt đầu:
- Giờ kết thúc:

## 1. Xem trước đoạn video (CP0)

Ghi **trước khi vẽ**, mỗi người một dòng.

| Mã | Frame xuất hiện | Frame cuối thấy được | Rẽ / dừng / đổi tốc độ ở frame | Bị che ở frame | Ghi chú |
|---|---|---|---|---|---|
| P1 | | | | | |
| P2 | | | | | |
| P3 | | | | | |
| P4 | | | | | |
| P5 | | | | | |

## 2. Keyframe và thời gian (CP1, CP4)

Số keyframe lấy từ kết quả `src/check_submission.py`.

| Mã | Số keyframe | Keyframe ở frame | Số frame có mặt | Keyframe / 100 frame | Thời gian (phút) | Chỗ khó |
|---|---|---|---|---|---|---|
| P1 | | | | | | |
| P2 | | | | | | |
| P3 | | | | | | |
| P4 | | | | | | |
| P5 | | | | | | |
| **Tổng** | | | | | | |

Keyframe / 100 frame của cả bài = tổng keyframe ÷ tổng số frame có mặt × 100 = ...

Bạn đặt keyframe nhiều nhất ở người nào? Vì sao (người đó rẽ, dừng, lại gần camera hay bị che)?

...

## 3. Đoạn bị che (CP2)

Người bị che: `P_`

| Mốc | Frame |
|---|---:|
| Bắt đầu bị che một phần (bật `occluded`) | |
| Mất hẳn (bật `outside`) | |
| Hiện lại (tắt `outside`) | |
| Thấy rõ trở lại (tắt `occluded`) | |

- Thời gian khuất hẳn: ___ frame = ___ giây.
- Quyết định: giữ cùng ID / tạo track mới.
- Lý do (trả lời 3 câu: khuất bao lâu so với 60 frame, ngoại hình có khớp, chỗ hiện lại có đúng hướng và tốc độ):

...

Ảnh chụp màn hình:

![Trước khi che](images/che_1_truoc.png)
![Giữa đoạn che, thấy cờ trên panel object](images/che_2_giua.png)
![Sau khi hiện lại, cùng ID](images/che_3_sau.png)

## 4. Tự review ID (CP3)

Lượt 1 theo người (đi ngược từ frame 149 về 0 trên CVAT), lượt 2 theo cảnh (nhảy 10 frame). Ít nhất 3 dòng; không có lỗi thì ghi một dòng "đã kiểm hai lượt, không lỗi".

Loại lỗi dùng đúng một trong 7 mã: `id_switch`, `fragmentation`, `lost`, `merge`, `false_track`, `drift`, `flag`.

| Frame | Mã người | Loại lỗi | Mô tả một câu | Phát hiện ở lượt | Đã sửa? |
|---:|---|---|---|---|---|
| | | | | | |
| | | | | | |
| | | | | | |

Tổng hợp số lỗi theo loại:

| `id_switch` | `fragmentation` | `lost` | `merge` | `false_track` | `drift` | `flag` |
|---:|---:|---:|---:|---:|---:|---:|
| | | | | | | |

Lỗi nào chỉ lượt 2 (theo cảnh) mới thấy, lượt 1 (theo người) không thấy? Vì sao?

...

## 5. File xuất và kết quả tự kiểm (CP4)

| Kiểm tra | Kết quả |
|---|---|
| Tên file MOT 1.1 | |
| Tên file CVAT for video 1.1 | |
| Số track ID khác nhau trong `gt/gt.txt` (phải là 5) | |
| Frame `outside` không có dòng trong `gt.txt` (đúng / sai) | |
| Job đã completed trên CVAT máy cá nhân | |

Dán phần tóm tắt in ra từ `src/check_submission.py`:

```text
Số frame in theo CVAT (bắt đầu từ 0). Trong gt.txt, frame_id = frame CVAT + 1.

=== File MOT 1.1: LeHoangDuc_mot.zip ===
  Số track ID: 13   |   Tổng số box: 992
  [OK]        Đúng 13 track ID.

  Track | Frame có mặt | Số frame | Đoạn vắng (outside)
      1 |   0–149      |      150 | -
      2 |   0–149      |      135 | 120–123, 137–147
      3 |   0–149      |      146 | 41–44
      4 |   0–105      |      106 | -
      5 |   0–147      |      124 | 111–134
      6 |   0–149      |      150 | -
      7 |   8–29       |       22 | -
      8 |  44–61       |       18 | -
      9 |  59–149      |       91 | -
     10 |  67–87       |       21 | -
     11 | 134–149      |       16 | -
     12 | 143–149      |        7 | -
     13 | 144–149      |        6 | -


=== File CVAT for video 1.1: LeHoangDuc_cvat_video.zip ===

  Track | Nhãn   | Frame thấy | Keyframe | KF/100 frame | Frame occluded | Lần bật outside
      0 | person |        150 |       18 |         12.0 |              0 |               0
              Track 0: keyframe ở frame [0, 10, 14, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 120, 130, 140, 146, 149]
      1 | person |        135 |       15 |         11.1 |             25 |               2
              Track 1: keyframe ở frame [0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100, 110, 124, 130, 148]
      2 | person |        146 |       17 |         11.6 |             25 |               1
              Track 2: keyframe ở frame [0, 10, 20, 26, 30, 45, 55, 60, 70, 80, 90, 100, 110, 120, 130, 140, 149]
      3 | person |        106 |        8 |          7.5 |             16 |               1
              Track 3: keyframe ở frame [0, 10, 20, 30, 40, 90, 103, 104]
      4 | person |        124 |       14 |         11.3 |             16 |               2
              Track 4: keyframe ở frame [0, 10, 20, 30, 40, 50, 105, 135, 136, 137, 138, 139, 140, 142]
      5 | person |        150 |       26 |         17.3 |              0 |               0
              Track 5: keyframe ở frame [0, 10, 11, 13, 14, 20, 23, 26, 29, 30, 31, 33, 40, 43, 50, 60, 70, 74,80, 90, 100, 110, 120, 130, 140, 149]
      6 | person |         18 |        8 |         44.4 |              4 |               1
              Track 6: keyframe ở frame [44, 54, 56, 57, 58, 59, 60, 61]
      7 | person |         91 |       22 |         24.2 |              9 |               0
              Track 7: keyframe ở frame [59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 79, 89, 99, 109, 119, 129, 139, 149]
      8 | person |         16 |        4 |         25.0 |              0 |               0
              Track 8: keyframe ở frame [134, 143, 144, 149]
      9 | person |          7 |        4 |         57.1 |              7 |               0
              Track 9: keyframe ở frame [143, 144, 145, 146]
  [CẢNH BÁO]  Track 9: 57 keyframe / 100 frame > 50. Quá dày, dồn keyframe vào chỗ rẽ / dừng / bị che.
     10 | person |         22 |        9 |         40.9 |             22 |               1
              Track 10: keyframe ở frame [8, 10, 11, 14, 16, 22, 24, 26, 29]
     11 | person |          6 |        5 |         83.3 |              6 |               0
              Track 11: keyframe ở frame [144, 145, 146, 147, 149]
  [CẢNH BÁO]  Track 11: 83 keyframe / 100 frame > 50. Quá dày, dồn keyframe vào chỗ rẽ / dừng / bị che.
     12 | person |         21 |        8 |         38.1 |             21 |               1
              Track 12: keyframe ở frame [67, 73, 74, 75, 76, 77, 79, 83]

  Tổng: 158 keyframe / 992 frame có mặt = 15.9 keyframe / 100 frame
  [OK]        Đọc được 13 track từ annotations.xml.

=== Tóm tắt ===
  Lỗi: 0   |   Cảnh báo: 2
  Không có lỗi định dạng. Mở CVAT xem lại từng [CẢNH BÁO]; cảnh báo đúng ý bạn thì ghi lý do vào báo cáo.
```

## 6. Ba câu kết

1. Nếu được gán lại, bạn sẽ đặt keyframe khác ở đâu? Vì sao?

   ...

2. Có chỗ nào bạn không chắc "cùng ID hay ID mới"? Bạn đã quyết định và ghi chú thế nào?

   ...

3. Một lỗi ID trong job của bạn (nếu không còn sót, chọn lỗi đã sửa) có thể làm xe tự lái dự đoán sai chuyển động của người đó như thế nào? Lỗi đó ảnh hưởng MOTA hay IDF1 nhiều hơn?

   ...

## Bonus (nếu làm)

### B1 — Hai người đi sát

...

### B2 — So cách đặt keyframe

| Cách đặt | Số keyframe | Frame trôi nhất | Ghi chú |
|---|---:|---:|---|
| Đều mỗi 30 frame | | | |
| Theo chỗ đổi hướng | | | |

...

### B3 — So với tracker có sẵn

| Frame | Mã người | Tracker làm gì | Nhãn của bạn | Giải thích (đoán rồi sửa / ghép IoU / box score thấp / ngoại hình) |
|---:|---|---|---|---|
| | | | | |
| | | | | |

## 7. Tài liệu tham khảo và công cụ AI đã dùng

...
