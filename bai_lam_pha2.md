# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 01
- **Họ tên:**Tạ Hoàng Nam
- **Lớp:**CNTT4
- **Link repository Pha2:**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):**Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt tour ra JSON

**KET QUA AI**

```text
[
  {
    "ma_tour": "SP2N",
    "ngay_khoi_hanh": "2026-12-20",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_phong": "doi",
    "ghi_chu": null
  },
  {
    "ma_tour": "PQ4N",
    "ngay_khoi_hanh": "2027-01-05",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_phong": null,
    "ghi_chu": "Một người ăn chay"
  },
  {
    "ma_tour": "DL3N",
    "ngay_khoi_hanh": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_phong": "doi",
    "ghi_chu": "ông nội đi xe lăn"
  }
]
```

**Link trò chuyện:**https://share.gemini.google/Xg3pqIhpaRL1

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Báo giá chi tiết cho đoàn đi tour DL3N – Đà Lạt 3 ngày 2 đêm (đơn giá gốc: 3.200.000 đồng/người lớn):
Tiền người lớn:
5
×
3.200.000
=
16.000.000
 đ
o
ˆ
ˋ
ng
5×3.200.000=16.000.000 đ 
o
ˆ
 
ˋ
 ng
Tiền trẻ em: (Áp dụng mức 70% giá người lớn cho 2 bé 8 tuổi và 10 tuổi; bé 3 tuổi được miễn phí)
2
×
(
3.200.000
×
70
%
)
=
2
×
2.240.000
=
4.480.000
 đ
o
ˆ
ˋ
ng
2×(3.200.000×70%)=2×2.240.000=4.480.000 đ 
o
ˆ
 
ˋ
 ng
Tiền tour:
16.000.000
+
4.480.000
=
20.480.000
 đ
o
ˆ
ˋ
ng
16.000.000+4.480.000=20.480.000 đ 
o
ˆ
 
ˋ
 ng
Giảm giá đoàn: (Đoàn có 5 người lớn, đủ điều kiện giảm 5% trên tổng tiền tour)
20.480.000
×
5
%
=
1.024.000
 đ
o
ˆ
ˋ
ng
20.480.000×5%=1.024.000 đ 
o
ˆ
 
ˋ
 ng
Phụ thu: (1 người lớn ở phòng đơn, không áp dụng giảm giá)
1
×
800.000
=
800.000
 đ
o
ˆ
ˋ
ng
1×800.000=800.000 đ 
o
ˆ
 
ˋ
 ng
Tổng tiền:
(
20.480.000
−
1.024.000
)
+
800.000
=
19.456.000
+
800.000
=
20.256.000
 đ
o
ˆ
ˋ
ng
(20.480.000−1.024.000)+800.000=19.456.000+800.000=20.256.000 đ 
o
ˆ
 
ˋ
 ng
[RESULT: 20.256.000 đồng]
```

**Link trò chuyện:**https://share.gemini.google/HH0u57g7CO0H

### b) Kiểm tra kết quả AI
Đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "khach_san", "so_khach": 2, "so_dem_bi_anh_huong": 2, "tom_tat": "Khách bị đổi từ khách sạn 4 sao sang 3 sao ẩm mốc trong 2 đêm đầu."}
```

**Link trò chuyện:**https://share.gemini.google/Q1MKe4rhOyJc

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
Tiêu chí    Điểm    Minh chứng    Đề xuất sửa
Đúng thông tin (50%)    0 / 5.0    Báo sai giá ("2.200.000đ" thay vì 2.400.000đ) và sai chính sách huỷ ("huỷ trước 3 ngày thì được hoàn tiền đầy đủ").    Sửa giá thành 2.400.000 đồng/người lớn; nêu đúng chính sách huỷ (trước từ 7 ngày hoàn 100%, 3-6 ngày hoàn 50%, dưới 3 ngày không hoàn).
Đầy đủ (30%)    1.5 / 3.0    Đã trả lời 2 ý (giá và chính sách huỷ) nhưng thiếu lời mời khách cung cấp ngày đi và số lượng khách để đặt tour ("Anh cần gì cứ nhắn em nhé!").    Bổ sung câu hỏi chốt thông tin: "Anh dự kiến đi vào ngày nào và đi mấy người để em hỗ trợ kiểm tra chỗ và giữ tour cho mình ạ?"
Giọng điệu (20%)    1.0 / 2.0    Có chào hỏi lịch sự nhưng dùng từ ngữ suồng sã, thiếu chuyên nghiệp ("đi rất vui luôn ạ", "nha anh").    Thay bằng văn phong tư vấn chuyên nghiệp hơn, bỏ các từ cảm thán suồng sã ("luôn ạ", "nha").
Tổng điểm    2.5 / 10
```

**Link trò chuyện:**https://share.gemini.google/BteQ2gmsSpBr
