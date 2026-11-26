# BÀI LÀM PHA 2 – HACKATHON 02

- **Mã đề:** 05
- **Họ tên:** Phan Huy Hưng
- **Lớp:** CNTT1
- **Link repository Pha2:** https://github.com/devhngg05/CNTT1_PromptAI_H02_Pha2
- **Công cụ AI đã dùng (ChatGPT/Claude/Gemini):** Gemini

> Pha 2 (20 phút cuối). Mỗi mục: mở cuộc trò chuyện mới, gửi nguyên văn prompt đã viết trong bai_lam_pha1.md, dán câu trả lời và link chia sẻ vào đây. Xong, kéo thả file này vào repository Pha2.

## 4.2. Trích xuất tin nhắn đặt vé xem phim ra JSON

**KET QUA AI**

```text
[
{
"loai_ve": "P2D",
"ngay_chieu": "2026-12-24",
"ve_nguoi_lon": 2,
"ve_tre_em": 1,
"loai_ghe": "thuong",
"ghi_chu": null
},
{
"loai_ve": "P3D",
"ngay_chieu": "2027-01-01",
"ve_nguoi_lon": 3,
"ve_tre_em": 0,
"loai_ghe": null,
"ghi_chu": "1 người hay chóng mặt, cần ngồi gần lối ra"
},
{
"loai_ve": "GOLD",
"ngay_chieu": null,
"ve_nguoi_lon": 4,
"ve_tre_em": 0,
"loai_ghe": "doi",
"ghi_chu": "1 bạn đi xe lăn"
}
]```

**Link trò chuyện:** https://share.gemini.google/0vLNt6X3VZA5

## 4.3. Báo giá bằng Chain-of-Thought

**KET QUA AI**

```text
**Bước 1 - Tiền vé người lớn:**
Giá vé người lớn phim 3D (P3D) là 130.000 đồng/vé. Với 5 người lớn:


$$5 \times 130.000 = 650.000 \text{ đồng}$$

**Bước 2 - Tiền vé trẻ em:**
Mức giá vé trẻ em cao từ 1 m đến 1,3 m bằng 70% giá vé người lớn: $70\% \times 130.000 = 91.000 \text{ đồng/vé}$.

* Trẻ cao 1,1 m (nằm trong khoảng từ 1 m đến 1,3 m): 91.000 đồng.
* Trẻ cao 1,25 m (nằm trong khoảng từ 1 m đến 1,3 m): 91.000 đồng.
* Bé cao 0,9 m (dưới 1 m, ngồi cùng người lớn): 0 đồng (miễn phí).

Tổng tiền vé trẻ em:


$$91.000 + 91.000 + 0 = 182.000 \text{ đồng}$$

**Bước 3 - Tiền vé:**
Tổng tiền vé trước khi giảm giá (tiền vé người lớn + tiền vé trẻ em):


$$650.000 + 182.000 = 832.000 \text{ đồng}$$

**Bước 4 - Giảm giá nhóm:**
Nhóm có 5 người lớn, đáp ứng điều kiện từ 5 người lớn trở lên nên được giảm 10% trên tiền vé.

* Số tiền được giảm: $10\% \times 832.000 = 83.200 \text{ đồng}$
* Tiền vé sau giảm: $832.000 - 83.200 = 748.800 \text{ đồng}$

**Bước 5 - Tiền combo:**
Phụ thu combo bắp nước là 75.000 đồng/combo và không áp dụng giảm giá. Với 3 combo:


$$3 \times 75.000 = 225.000 \text{ đồng}$$

**Bước 6 - Tổng tiền:**
Tổng số tiền khách cần thanh toán (tiền vé sau giảm + tiền combo):


$$748.800 + 225.000 = 973.800 \text{ đồng}$$

[RESULT: 973.800 đồng]
```

**Link trò chuyện:**

### b) Kiểm tra kết quả AI

(Ghi kết luận AI đúng hay sai; nếu sai, ghi bước sai đầu tiên và kết quả đúng của bước đó – xoá dòng này)

## 4.4. Dây chuyền xử lý khiếu nại – kết quả Trạm 1

**KET QUA AI**

```text
{"loai_su_co": "loi_ky_thuat", "so_khach": 4, "so_suat_bi_loi": 2, "tom_tat": "Cả 2 suất chiếu tại phòng 3 bị mất tiếng hơn 15 phút giữa phim."}
Kết quả kiểm tra đầu ra JSON từ Trạm 1 đều **đạt yêu cầu** trên cả hai nhóm tiêu chí:

### 1. Kiểm tra cú pháp và cấu trúc JSON

* **Tính hợp lệ & định dạng:** Chuỗi đầu ra là một đối tượng JSON hợp lệ, không kèm lời chào, giải thích thừa hay ký tự bao ngoài.
* **Danh sách trường:** Có đủ và đúng chính xác tên 4 khóa (`loai_su_co`, `so_khach`, `so_suat_bi_loi`, `tom_tat`).
* **Kiểu dữ liệu & ràng buộc:**
* `loai_su_co`: `"loi_ky_thuat"` — kiểu chuỗi, nằm trong 4 nhãn cố định.
* `so_khach`: `4` — đúng kiểu số nguyên.
* `so_suat_bi_loi`: `2` — đúng kiểu số nguyên.
* `tom_tat`: `"Cả 2 suất chiếu tại phòng 3 bị mất tiếng hơn 15 phút giữa phim."` — gồm **15 từ** (tính theo tiếng tách bằng khoảng trắng), thỏa mãn giới hạn không quá 20 từ.



### 2. Kiểm tra độ chính xác so với email gốc

| Trường dữ liệu | Giá trị trích xuất | Đối chiếu email gốc | Trạng thái |
| --- | --- | --- | --- |
| `loai_su_co` | `"loi_ky_thuat"` | Sự cố là *"bị mất tiếng giữa phim hơn 15 phút"*; khách khẳng định *"nhân viên soát vé rất lịch sự, không có gì phàn nàn"* nên không bị nhầm sang `"nhan_vien"`. | **Đạt** |
| `so_khach` | `4` | Khớp với chi tiết *"gia đình tôi 4 người"*. | **Đạt** |
| `so_suat_bi_loi` | `2` | Khớp với chi tiết *"xem 2 suất phim liên tiếp"* và *"Cả hai suất đều bị mất tiếng"*. | **Đạt** |
| `tom_tat` | Nội dung sự cố mất tiếng tại phòng 3 | Phản ánh đầy đủ bản chất lỗi (mất tiếng hơn 15 phút), phạm vi (cả 2 suất) và địa điểm (phòng 3). | **Đạt** |

Dữ liệu đầu ra đủ điều kiện và đảm bảo độ chính xác để chuyển tiếp sang bước tính toán đền bù ở Trạm 2.
Trong cuộc trò chuyện này, lượt trước mới dừng ở bước kiểm tra JSON của Trạm 1 — chưa có phần đầu email bị ngắt cũng như mức hoàn tiền cụ thể từ Trạm 2, nên mình chưa thể điền con số chính xác hay kiểm soát chắc chắn tổng độ dài toàn email dưới 150 từ.

Nếu cần dùng ngay phần nối tiếp (khoảng 60 từ) ngay sau cụm từ *"Rạp phim Ánh Dương xin hoàn lại Quý khách khoản"*, bạn có thể tham khảo mẫu sau và thay mức đền bù từ Trạm 2 vào chỗ trống:

> tiền `[số tiền từ Trạm 2]` cho 2 suất chiếu bị ảnh hưởng của 4 khách. Quý khách vui lòng phản hồi email này kèm mã vé và số tài khoản để rạp hoàn tiền trong vòng 3 ngày làm việc.
> Chân thành xin lỗi vì sự bất tiện này và rất mong tiếp tục được đón tiếp gia đình Quý khách.
> Trân trọng,
> Rạp phim Ánh Dương

Bạn gửi thêm phần đầu email bị ngắt và kết quả tính đền bù ở Trạm 2 để mình ghép nối đúng số tiền và căn chuẩn giới hạn dưới 150 từ nhé?
```

**Link trò chuyện:** https://share.gemini.google/Lj6Lvd3vApUH

## 4.5. Prompt chấm bài theo Rubric

**KET QUA AI**

```text
| Tiêu chí | Điểm | Minh chứng | Đề xuất sửa |
| --- | --- | --- | --- |
| **Đúng thông tin (50%)** | 0/5 | **(1) Câu bị lỗi:** "Vé 2D bên em có 80k thôi nè, rẻ xỉu." — **Lý do sai:** Sai giá vé so với thông tin chuẩn (giá vé P2D chuẩn là 90.000 đồng/vé người lớn, không phải 80.000 đồng) và thiếu thông tin đối tượng vé người lớn. **(2) Câu bị lỗi:** "Anh huỷ trước 2 tiếng vẫn được hoàn 50% nha anh." — **Lý do sai:** Sai chính sách huỷ vé so với thông tin chuẩn (huỷ trước giờ chiếu dưới 3 giờ không được hoàn tiền; mức hoàn 50% chỉ áp dụng khi huỷ từ 3 đến dưới 24 giờ). | **(1)** "Hiện tại giá vé phim 2D (P2D) của Rạp phim Ánh Dương là 90.000 đồng/vé người lớn ạ." **(2)** "Theo chính sách của rạp, vé huỷ trước giờ chiếu dưới 3 giờ sẽ không được hoàn tiền (rạp chỉ hoàn 100% khi huỷ trước từ 24 giờ trở lên và hoàn 50% khi huỷ từ 3 đến dưới 24 giờ). Vì vậy, nếu anh/chị huỷ trước giờ chiếu 2 tiếng thì rất tiếc sẽ không được hoàn tiền ạ." |
| **Đầy đủ (30%)** | 2/3 | **Câu bị lỗi:** "Cần gì nhắn em nha!" — **Lý do sai:** Nhân viên đã trả lời đủ cả hai câu hỏi của khách (giá vé và chính sách huỷ vé), nhưng thiếu lời mời khách cung cấp ngày, suất chiếu và số lượng vé để hỗ trợ đặt chỗ theo yêu cầu của rubric. | "Nếu anh/chị muốn đặt chỗ, anh/chị vui lòng cung cấp giúp em ngày xem, suất chiếu và số lượng vé để em hỗ trợ đặt vé nhanh chóng ạ." |
| **Giọng điệu (20%)** | 0/2 | **(1) Câu bị lỗi:** "Hi anh!" — **Lý do sai:** Lời chào suồng sã, thiếu trang trọng và chuyên nghiệp so với tiêu chí giọng điệu của rubric. **(2) Câu bị lỗi:** "Vé 2D bên em có 80k thôi nè, rẻ xỉu." — **Lý do sai:** Dùng từ ngữ suồng sã, tiếng lóng ("80k", "thôi nè", "rẻ xỉu"), vi phạm tiêu chí lịch sự, chuyên nghiệp. **(3) Câu bị lỗi:** "Anh huỷ trước 2 tiếng vẫn được hoàn 50% nha anh. Cần gì nhắn em nha!" — **Lý do sai:** Dùng khẩu ngữ suồng sã ("nha anh", "Cần gì nhắn em nha!"), chưa đảm bảo phong thái chuyên nghiệp khi tư vấn khách hàng. | **(1)** "Dạ, Rạp phim Ánh Dương xin chào anh/chị ạ." **(2)** "Giá vé phim 2D (P2D) dành cho người lớn hiện tại là 90.000 đồng/vé ạ." **(3)** "Trường hợp huỷ vé trước giờ chiếu 2 tiếng sẽ không được hoàn tiền theo quy định của rạp ạ. Nếu anh/chị cần hỗ trợ thêm thông tin, anh/chị vui lòng phản hồi để em phục vụ ạ." |

Tổng điểm: 2/10.
```

**Link trò chuyện:** https://share.gemini.google/LfdtPnXbGkJp
