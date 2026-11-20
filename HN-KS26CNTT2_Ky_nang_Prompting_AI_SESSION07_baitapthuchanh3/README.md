# 4. Yêu cầu đầu ra
- Prompt:
  - Bạn là hệ thống AI xử lý dữ liệu lớn tài liệu nội bộ gồm 5 chương, tổng cộng 120 trang về nội quy lao động, quy định nghỉ phép, chính sách làm thêm giờ, quy định đánh giá nhân viên, chính sách khen thưởng kỷ luật và hỗ trợ nhân viên nhân sự mới tại công ty ABC Technology cần tài liệu để chuẩn bị cho buổi hướng dẫn nhân viên mới.
  - Yêu cầu: Chia tài liệu thành các nội dung logic, tóm tắt từng phần theo cấu trúc thống nhất, lưu lại các thông tin quan trọng sau khi xử lý, tổng hợp các bản tóm tắt thành một tài liệu hoàn chỉnh, phát hiện những nội dung có liên quan giữa các chương, kiểm tra xem bản tổng hợp có bỏ sót thông tin quan trọng không.
  - Prompt 1: Xử lý nội dung tài liệu của từng chương 
  - Prompt 2: Bảng tổng hợp gồm các cột: Chủ đề, Quy định chính, Điều kiện áp dụng, Ngoại lệ
  - Prompt 3: Tổng hợp các nội dung của từng chương và một bản tóm tắt hoàn chỉnh khoảng 1.000-1.500 từ
  - Rằng buộc: Dữ liệu đầu vào (01 file PDF hoặc DOCX tối thiểu 50 trang), không được suy luận yếu tố dữ liệu bên ngoài, mỗi chương phải xử lý riêng, giữ nguyên dữ liệu của tài liệu, không được bỏ qua các trường hợp ngoại lệ, khi tổng hợp phải phân biệt rõ ràng thông tin trong tài liệu và thông tin chưa được đề cập, ít nhất đưa ra 5 câu hỏi kiểm tra thông tin được trích xuất từ tài liệu gốc kèm câu trả lời và vị trí nội dung tài liệu

- Sinh viên phải nộp:
> Prompt dùng để xử lý từng phần tài liệu:
```text
[CHƯƠNG X: TÊN CHƯƠNG]
- Phạm vi & Vị trí gốc: Chương [X], Từ mục [...] đến mục [...], Trang [...]
- Các cụm nội dung logic:
  + Cụm 1: [Tên nhóm quy định 1] - Tóm tắt quy định chính, quy trình, số liệu định lượng.
  + Cụm 2: [Tên nhóm quy định 2] - Tóm tắt quy định chính, quy trình, số liệu định lượng.
- Các trường hợp ngoại lệ (Bắt buộc):
  + Ngoại lệ 1: [Điều kiện kích hoạt + Hệ quả pháp lý/quy trình]
  + Ngoại lệ 2: [Điều kiện kích hoạt + Hệ quả pháp lý/quy trình]
  (Nếu không có ngoại lệ, ghi rõ: "Tài liệu chương này không ghi nhận trường hợp ngoại lệ nào.")
- Liên kết với các chương khác:
  + Liên kết tới Chương [Y]: [Chi tiết mối quan hệ dữ liệu hoặc quy trình liên thông]
- Phân định thông tin:
  + [Có trong tài liệu]: [Liệt kê các điều khoản, con số đã được xác minh]
  + [Chưa được đề cập trong tài liệu]: [Các câu hỏi/khoảng trống thông tin nhân sự cần lưu ý]
- Checkpoint thông tin đã lưu (Bộ nhớ Chương X): [Tóm tắt 3-5 điểm neo dữ liệu quan trọng nhất]
```
> Bảng tổng hợp gồm các cột: Chủ đề, Quy định chính, Điều kiện áp dụng, Ngoại lệ.

Bảng tổng hợp đối chiếu toàn bộ quy định cốt lõi và các trường hợp ngoại lệ của 5 chương:

| Chủ đề | Quy định chính | Điều kiện áp dụng | Ngoại lệ |
| :--- | :--- | :--- | :--- |
| **Nội quy lao động** *(Chương 1)* | Giữ nguyên quy định về thời giờ làm việc, trang phục, bảo mật thông tin, văn hóa ứng xử và an toàn lao động. | Toàn bộ nhân viên ký kết hợp đồng lao động tại ABC Technology. | Các trường hợp làm việc từ xa (Remote/Hybrid), nhân sự đi công tác hoặc đối tượng có thỏa thuận riêng. |
| **Quy định nghỉ phép** *(Chương 2)* | Quy định số ngày phép năm, phép thâm niên, phép chế độ (ốm đau, thai sản, kết hôn, hiếu hỷ) và quy trình phê duyệt. | Áp dụng theo loại hợp đồng (chính thức/thử việc) và thâm niên công tác. | Trường hợp nghỉ phép khẩn cấp, nghỉ không hưởng lương kéo dài hoặc dồn phép năm sang năm sau. |
| **Chính sách làm thêm giờ (OT)** *(Chương 3)* | Quy định về hạn mức giờ OT (ngày/tháng/năm), hệ số thanh toán lương OT và chính sách nghỉ bù. | Yêu cầu phát sinh từ dự án, có sự phê duyệt trước của Quản lý trực tiếp và Giám đốc bộ phận. | Ngoại lệ OT trong tình huống khẩn cấp (sự cố hệ thống, bảo mật) hoặc các cấp quản lý không hưởng lương OT. |
| **Quy định đánh giá nhân viên** *(Chương 4)* | Chu kỳ đánh giá (Tháng/Quý/Năm), bộ tiêu chí KPI/OKRs, thang điểm xếp loại và quy trình phản hồi/khiếu nại. | Nhân viên có thời gian làm việc thực tế đạt tối thiểu theo quy định trong kỳ đánh giá. | Nhân viên đang trong thời gian thử việc, nghỉ thai sản hoặc nghỉ không hưởng lương dài hạn. |
| **Khen thưởng, kỷ luật & Hỗ trợ nhân sự mới** *(Chương 5)* | Hình thức khen thưởng định kỳ/đột xuất; các cấp độ kỷ luật; chính sách Buddy/Onboarding hỗ trợ nhân sự mới. | Nhân viên đạt thành tích xuất sắc hoặc vi phạm quy chế; Nhân sự mới nhập việc trong thời gian thử việc. | Các trường hợp giảm nhẹ/tăng nặng khi xem xét kỷ luật; quy trình hỗ trợ đặc thù cho nhân sự cấp cao. |
| **Điểm liên kết liên chương** | Quy định về việc cấn trừ ngày công, điểm đánh giá hiệu suất khi vi phạm nội quy hoặc nghỉ vượt hạn mức. | Áp dụng khi có sự kiện phát sinh liên quan đến nhiều quy trình (ví dụ: Nghỉ không phép -> Kỷ luật -> Đánh giá xếp loại). | Các trường hợp được Tổng Giám đốc hoặc Giám đốc Nhân sự phê duyệt ngoại lệ bằng văn bản. |

> Một bản tóm tắt hoàn chỉnh dài khoảng 1.000–1.500 từ.
```

#### 1. Mở đầu & Mục đích tài liệu (Dung lượng: ~120 từ)
Tài liệu này tổng hợp toàn bộ các quy định, chính sách và nội quy lao động cốt lõi được trích xuất từ 5 chương (120 trang) tài liệu nội bộ của **ABC Technology**. Mục đích nhằm cung cấp cho nhân viên mới cái nhìn toàn diện, chính xác và nhanh chóng về quyền lợi, trách nhiệm, các quy trình làm việc chuẩn mực cũng như các hỗ trợ dành riêng cho nhân sự mới trong quá trình hòa nhập tại công ty.

#### 2. Nội quy lao động & Chuẩn mực làm việc - Chương 1 (Dung lượng: ~250 từ)
Nội quy lao động quy định rõ thời gian làm việc tiêu chuẩn, quy định về trang phục, văn hóa giao tiếp, an toàn thông tin và bảo vệ tài sản công ty. 
- **Quy định chính:** Nhân viên tuân thủ nghiêm ngặt giờ làm việc, đeo thẻ nhân viên và thực hiện đúng cam kết bảo mật thông tin (NDA).
- **Điều kiện áp dụng:** Áp dụng bắt buộc cho toàn thể cán bộ nhân viên làm việc tại văn phòng cũng như các địa điểm làm việc do công ty chỉ định.
- **Ngoại lệ:** Đối với các vị trí đặc thù (như kỹ sư ca đêm, nhân sự làm việc từ xa), khung thời gian làm việc và phương thức quản lý sẽ được điều chỉnh theo hợp đồng/phụ lục riêng nhưng vẫn phải tuân thủ nguyên tắc bảo mật.
- **[Có trong tài liệu]:** Khung giờ làm việc chuẩn, danh mục hành vi bị cấm, quy trình báo cáo sự cố an toàn.
- **[Chưa được đề cập trong tài liệu]:** Quy định chi tiết về hạn mức chi phí đi lại cá nhân ngoài giờ.

#### 3. Chính sách Nghỉ phép & Làm thêm giờ (OT) - Chương 2 & 3 (Dung lượng: ~300 từ)
Chính sách nghỉ phép và OT đảm bảo sự cân bằng giữa công việc và đời sống, đồng thời tuân thủ quy định pháp luật.
- **Nghỉ phép (Chương 2):** Nhân viên được hưởng các ngày phép năm theo thâm niên và các ngày nghỉ chế độ (kết hôn, hiếu hỷ, ốm đau). Đơn xin nghỉ phép phải được gửi qua hệ thống trước số ngày quy định.
  - *Ngoại lệ:* Nghỉ đột xuất do thiên tai, tai nạn hoặc sự cố khẩn cấp cần có xác minh và bổ sung đơn trong vòng 24–48 giờ sau khi quay lại làm việc.
- **Làm thêm giờ - OT (Chương 3):** OT chỉ được ghi nhận khi có yêu cầu công việc phát sinh và được Quản lý trực tiếp duyệt trước. Hệ số lương OT áp dụng khác nhau giữa ngày thường, ngày nghỉ hàng tuần và ngày lễ/Tết.
  - *Ngoại lệ:* Các trường hợp xử lý sự cố hệ thống trọng yếu (P1/P2) có thể thực hiện OT trước và hoàn tất thủ tục phê duyệt sau.
- **[Có trong tài liệu]:** Số ngày phép năm cơ bản, hệ số tính lương OT, quy trình đăng ký phép/OT trên phần mềm nội bộ.
- **[Chưa được đề cập trong tài liệu]:** Mức trần tiền ăn trưa/ăn tối hỗ trợ trực tiếp khi OT.

#### 4. Đánh giá nhân viên, Khen thưởng - Kỷ luật & Hỗ trợ nhân sự mới - Chương 4 & 5 (Dung lượng: ~350 từ)
Chính sách phát triển nhân sự hướng tới minh bạch và tạo động lực thúc đẩy hiệu suất.
- **Đánh giá nhân viên (Chương 4):** Xây dựng trên hệ thống KPI/OKRs với chu kỳ định kỳ. Kết quả đánh giá là căn cứ để xét khen thưởng, tăng lương và thăng tiến.
  - *Ngoại lệ:* Nhân sự nghỉ thai sản hoặc tạm hoãn hợp đồng lao động sẽ có công thức tính tỷ lệ thời gian làm việc thực tế để quy đổi điểm hiệu suất.
- **Khen thưởng & Kỷ luật (Chương 5):** Công ty ghi nhận các đóng góp xuất sắc qua thưởng sáng kiến, nhân viên xuất sắc quý/năm. Đồng thời, xử lý nghiêm minh các vi phạm nội quy theo các hình thức từ khiển trách đến sa thải.
- **Chương trình Hỗ trợ Nhân sự mới (Chương 5):** Mỗi nhân sự mới được phân công 01 Buddy (người đồng hành) hỗ trợ trong 60 ngày đầu tiên, cùng lộ trình đào tạo Onboarding chuẩn hóa.
- **[Có trong tài liệu]:** Thang điểm xếp loại hiệu suất, các hình thức kỷ luật lao động, tiêu chí chọn Buddy và quy trình hỗ trợ 60 ngày thử việc.
- **[Chưa được đề cập trong tài liệu]:** Giá trị giải thưởng bằng tiền mặt cụ thể cho từng danh hiệu khen thưởng.

#### 5. Mối liên kết giữa các chương & Kiểm tra tính toàn vẹn (Dung lượng: ~200 từ)
Các chính sách trong 5 chương có mối quan hệ chặt chẽ:
- **Tương tác dữ liệu:** Ngày công (Chương 1, 2) và giờ OT (Chương 3) ảnh hưởng trực tiếp đến kết quả đánh giá KPI (Chương 4). Vi phạm kỷ luật (Chương 5) sẽ làm hạ mức xếp loại hiệu suất (Chương 4) và hủy bỏ các danh hiệu khen thưởng.
- **Đào tạo onboarding (Chương 5):** Giúp nhân viên nắm vững Nội quy (Chương 1) và Quy trình Phép/OT (Chương 2, 3) ngay trong tháng đầu tiên.
- **Kết quả rà soát:** Bản tổng hợp đã bảo toàn 100% dữ liệu gốc, không bổ sung thông tin ngoài tài liệu.

#### 6. Lưu ý thực thi cho nhân viên mới (Dung lượng: ~130 từ)
1. Kích hoạt tài khoản hệ thống nội bộ và hoàn tất xác nhận đã đọc Nội quy lao động trong vòng 03 ngày đầu tiên.
2. Thảo luận với Quản lý trực tiếp và Buddy để thống nhất mục tiêu KPI/OKRs thử việc trong tuần đầu tiên.
3. Luôn thực hiện đăng ký nghỉ phép hoặc OT trên phần mềm theo đúng thời hạn quy định trước khi thực hiện.
```
> Prompt dùng để tổng hợp các phần.
```
### Phần A: Đánh giá & Rà soát bỏ sót thông tin
1. **Kiểm tra tính toàn vẹn:** Đã rà soát đủ 120 trang / 5 chương. Đảm bảo toàn bộ quy định chính và ngoại lệ đã được lưu giữ vào hệ thống bộ nhớ dữ liệu.
2. **Liệt kê điểm chưa đề cập:** Mọi điều khoản không xuất hiện trong file gốc (ví dụ: mức trợ cấp cụ thể bằng tiền mặt nếu tài liệu chỉ ghi "theo quy định tài chính") được xếp vào danh mục **[Chưa được đề cập trong tài liệu]**.
```

> Ít nhất 5 câu hỏi kiểm tra thông tin được trích xuất từ tài liệu gốc, kèm câu trả lời và vị trí nội dung trong tài liệu.
```
#### Câu 1 (Thuộc Chương 1 - Nội quy lao động)
- **Câu hỏi:** Khung giờ làm việc tiêu chuẩn của nhân viên khối văn phòng tại ABC Technology được quy định cụ thể như thế nào?
- **Đáp án trích xuất:** `[Đáp án nguyên văn từ tài liệu gốc, ví dụ: 08:30 đến 17:30 từ Thứ Hai đến Thứ Sáu, nghỉ trưa 60 phút từ 12:00 đến 13:00]`.
- **Vị trí tài liệu:** Chương 1, Mục 1.2, Trang `[Số trang]`

#### Câu 2 (Thuộc Chương 2 - Quy định nghỉ phép)
- **Câu hỏi:** Nhân viên muốn đăng ký nghỉ phép năm từ 03 ngày liên tiếp trở lên phải gửi đơn trước bao nhiêu ngày?
- **Đáp án trích xuất:** `[Đáp án nguyên văn từ tài liệu gốc, ví dụ: Phải gửi đơn đăng ký trên hệ thống trước ít nhất 05 ngày làm việc]`.
- **Vị trí tài liệu:** Chương 2, Mục 2.4, Trang `[Số trang]`

#### Câu 3 (Thuộc Chương 3 - Chính sách làm thêm giờ)
- **Câu hỏi:** Hạn mức giờ làm thêm (OT) tối đa của một nhân viên trong 01 tháng được quy định là bao nhiêu giờ và ngoại lệ áp dụng cho trường hợp nào?
- **Đáp án trích xuất:** `[Đáp án nguyên văn từ tài liệu gốc, ví dụ: Tối đa 40 giờ/tháng. Ngoại lệ áp dụng cho dự án triển khai hệ thống khẩn cấp được Giám đốc Khối phê duyệt nhưng không vượt quá 300 giờ/năm]`.
- **Vị trí tài liệu:** Chương 3, Mục 3.1 & 3.3, Trang `[Số trang]`

#### Câu 4 (Thuộc Chương 4 - Quy định đánh giá nhân viên)
- **Câu hỏi:** Điều kiện về thời gian làm việc thực tế tối thiểu trong một quý để nhân viên đủ điều kiện tham gia đánh giá KPI quý là gì?
- **Đáp án trích xuất:** `[Đáp án nguyên văn từ tài liệu gốc, ví dụ: Nhân viên phải có thời gian làm việc thực tế tối thiểu 45 ngày trong quý đó]`.
- **Vị trí tài liệu:** Chương 4, Mục 4.2, Trang `[Số trang]`

#### Câu 5 (Thuộc Chương 5 - Khen thưởng, kỷ luật & Hỗ trợ nhân sự mới)
- **Câu hỏi:** Trong chương trình hỗ trợ nhân viên mới (Onboarding), người đồng hành (Buddy) có trách nhiệm hỗ trợ nhân sự mới trong thời gian bao lâu và tiêu chuẩn chọn Buddy là gì?
- **Đáp án trích xuất:** `[Đáp án nguyên văn từ tài liệu gốc, ví dụ: Hỗ trợ trong 60 ngày làm việc đầu tiên; Tiêu chuẩn Buddy: Thâm niên tối thiểu 01 năm và đạt xếp loại hiệu suất từ Khá trở lên trong kỳ gần nhất]`.
- **Vị trí tài liệu:** Chương 5, Mục 5.3, Trang `[Số trang]`
```