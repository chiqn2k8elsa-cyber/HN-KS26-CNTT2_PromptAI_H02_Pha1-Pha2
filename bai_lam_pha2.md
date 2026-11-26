# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 04
- **Họ tên: Nguyễn Quỳnh Chi**
- **Lớp:CNTT2**
- **Link repository Pha2:https://github.com/chiqn2k8elsa-cyber/HN-KS26-CNTT2_PromptAI_H02_Pha1-Pha2**
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini): ChatGPT**

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xe ra JSON

**KET QUA AI**

```text
[
  {
    "ma_tuyen": "SGDL",
    "ngay_di": "2026-12-22",
    "nguoi_lon": 2,
    "tre_em": 1,
    "loai_cho": "giuong",
    "ghi_chu": null
  },
  {
    "ma_tuyen": "SGNT",
    "ngay_di": "2027-01-02",
    "nguoi_lon": 3,
    "tre_em": 0,
    "loai_cho": null,
    "ghi_chu": "Một người đang mang thai 6 tháng"
  },
  {
    "ma_tuyen": "SGCT",
    "ngay_di": null,
    "nguoi_lon": 4,
    "tre_em": 0,
    "loai_cho": "ghe",
    "ghi_chu": "Bà nội đi xe lăn"
  }
]
```

**Link trò chuyện:https://chatgpt.com/share/6b079dd3-b390-83ec-b894-c41a0f4af6cc**

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
Bước 1: Tính tiền vé người lớn
- Số người lớn: 8 người
- Giá vé tuyến SGDL: 320.000 đồng/vé
\(8 \times 320.000 = 2.560.000\) đồng

Bước 2: Tính tiền vé trẻ em
- Trẻ 6 tuổi: \(320.000 \times 75\% = 240.000\) đồng
- Trẻ 7 tuổi: \(320.000 \times 75\% = 240.000\) đồng
- Trẻ 9 tuổi: \(320.000 \times 75\% = 240.000\) đồng
- Bé 2 tuổi: ngồi cùng người lớn, miễn phí = 0 đồng
Tổng tiền vé trẻ em:

\(3 \times 240.000 = 720.000\) đồng

Bước 3: Tính tổng tiền vé chưa giảm giá

\(2.560.000 + 720.000 = 3.280.000\) đồng

Bước 4: Tính số tiền vé được giảm

Đoàn có 8 người lớn (từ 6 người lớn trở lên), được giảm 5% trên tổng tiền vé.

\(3.280.000 \times 5\% = 164.000\) đồng

Tiền vé sau giảm:

\(3.280.000 - 164.000 = 3.116.000\) đồng

Bước 5: Tính phụ thu hành lý cồng kềnh
- Số kiện: 2 kiện
- Phụ thu: 100.000 đồng/kiện
\(2 \times 100.000 = 200.000\) đồng

Bước 6: Tính tổng tiền

\(3.116.000 + 200.000 = 3.316.000\) đồng
[RESULT: 3.316.000 đồng]
```

**Link trò chuyện:https://chatgpt.com/share/6b079e2c-5328-83ec-aad1-9af76dc6eee8**

### b) Kiểm tra kết quả AI

Kết luận AI là đúng

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{
  "loai_su_co": "sai_loai_xe",
  "so_khach": 3,
  "so_chang_bi_doi": 2,
  "tom_tat": "3 khách đặt giường nằm nhưng cả chiều đi và về đều bị đổi sang xe ghế ngồi."
}
```

**Link trò chuyện:https://chatgpt.com/share/6b079e89-7a14-83ec-9966-be9acf870b86**

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
|---|---|---|---|
| **Đúng thông tin (50%)** | **0/5** | **Sai giá vé:** “Vé Sân Vận Động bên em giá 1.000.000đ/người” → Sai tuyến và giá vé. Giá chuẩn tuyến SGNT là 380.000đ/vé người lớn. **Sai chính sách đổi vé:** “Anh huỷ trước 3 ngày thì được hoàn tiền đầy đủ nha anh.” → Trả lời về hoàn tiền/huỷ vé, trong khi khách cần thông tin đổi vé; không nêu đúng chính sách đổi vé. | “Vé tuyến SGNT có giá 380.000đ/vé người lớn. Anh đổi vé trước giờ xe chạy từ 24 giờ trở lên được miễn phí, từ 6 đến dưới 24 giờ phí 20% giá vé, dưới 6 giờ không được đổi ạ.” |
| **Đầy đủ (30%)** | **0/3** | Không trả lời đúng cả 2 nội dung khách cần tư vấn (giá vé SGNT và chính sách đổi vé). Không mời khách cung cấp ngày đi, số vé để đặt chỗ. | “Anh cho em xin ngày đi và số lượng vé để em hỗ trợ đặt chỗ cho anh nhé ạ.” |
| **Giọng điệu (20%)** | **1/2** | “xem rất đã luôn ạ”, “nha anh”, “Anh cần gì cứ nhắn em nhé!” → Cách diễn đạt hơi suồng sã, thiếu tính chuyên nghiệp trong tư vấn dịch vụ. | Dùng cách diễn đạt lịch sự, chuyên nghiệp hơn như: “Dạ, em sẵn sàng hỗ trợ anh đặt vé và giải đáp thêm thông tin ạ.” |
| **Tổng điểm** | **1/10** | | |
```

**Link trò chuyện:https://chatgpt.com/share/6b079eff-6304-83ec-8ea6-169632b4bf06**
