# 4.Yêu cầu đầu ra
- Bạn là sinh viên mới học Python cần AI đóng vai "Python Programming Mentor hỗ trợ phân tích, chấm điểm và hướng dẫn cải thiện code". Hãy xử lý các công việc sau: Hiểu lỗi trong chương trình, Đánh giá chất lượng code, Biết cách tối ưu và cải thiện bài làm
- Prompt 1: Phân tích code của sinh viên theo các yêu cầu sau: xác định chức năng chương trình, tìm lỗi logic và lỗi cú pháp, giải thích nguyên nhân
- Prompt 2: Sử dụng phương pháp Feynman để giải thích cho người mới theo nhu cầu sau: sử dụng ngôn ngữ đơn giản, có ví dụ hoặc ẩn dụ thực tế, hạn chế thuật ngữ khó.
- Prompt 3: Chấm theo tiêu chí rubirc: Đúng chức năng (40%), Thuật toán (30%), Chất lượng code (20%), Xử lý lỗi (10%)
- Đầu ra AI phản hồi gồm: Giải thích code, Phân tích lỗi, Bảng điểm, Rubric dạng Markdown, Nhận xét ưu điểm/nhược điểm, Code python cải tiến dễ hiểu cho người mới học lập trình không được viết dòng code có chứa những hàm chuyên gia và có bình luận
- Dữ liệu đầu vào:
  ```
  Diem_toan = input("nhap diem:")
  Diem_TA = input("nhap diem:")
  Diem_TB = Diem_toan + Diem_TA / 2
  if Diem_TB >= 8:
  print("gioi")
  elif Diem_TB >= 5:
  print("trung binh")
  else:
  print("kha")
  ```

- Kết quả AI trả về:
```
Chào bạn! Mình sẽ đóng vai Python Programming Mentor để cùng bạn phân tích đoạn code này, chỉ ra chỗ chưa ổn theo cách dễ hiểu nhất, chấm điểm rõ ràng và viết lại phiên bản gọn gàng, dễ đọc cho người mới bắt đầu.

1. Giải thích code (Theo phương pháp Feynman)
Chức năng dự định của chương trình
Đoạn code này được viết với ý định: nhập điểm Toán và điểm Tiếng Anh, tính điểm trung bình, rồi xếp loại học lực (gioi, kha, trung binh).

Giải thích đơn giản bằng ẩn dụ thực tế
Hãy tưởng tượng input() giống như việc bạn nhận hai tờ giấy có ghi chữ số (ví dụ tờ "8" và tờ "6"), chứ chưa phải là cục nam châm/con số để làm phép toán thật sự.

Lỗi nối chữ thay vì cộng số: Nếu bạn lấy tờ giấy "8" ghép với tờ giấy "6" theo kiểu dán giấy lại với nhau, bạn sẽ được "86" chứ không phải 14! Trong Python, khi chưa đổi chữ thành số thực/số nguyên, dấu + sẽ ghép chữ thay vì cộng giá trị.

Lỗi thứ tự phép tính: Giả sử bạn có 8 cái bánh và 6 cái bánh, muốn tính trung bình mỗi bạn được bao nhiêu thì phải gom hết lại rồi mới chia 2 ((8 + 6) / 2 = 7). Nếu bạn chỉ chia đôi số bánh của bạn thứ hai trước (6 / 2 = 3) rồi mới cộng thêm 8 thì thành 11 — sai hoàn toàn!

Lỗi thụt lề (IndentationError): Trong Python, các câu lệnh nằm bên trong if, elif, else giống như những người đứng xếp hàng lùi vào một bước để báo hiệu "tôi thuộc nhóm điều kiện này". Nếu đứng thẳng hàng ngang với if thì Python sẽ báo lỗi ngay từ lúc chạy.

Lỗi đảo ngược xếp loại: Nhìn vào điều kiện của bạn:

Trên 8 -> "gioi"

Từ 5 đến dưới 8 -> "trung binh"

Dưới 5 -> "kha"
Điều này giống như xếp học sinh dưới 5 điểm là "kha", còn từ 5 đến dưới 8 điểm là "trung binh" — bị ngược mức xếp loại so với thang điểm thông thường.

2. Phân tích lỗi
Loại lỗi	Vị trí / Dòng liên quan	Nguyên nhân chi tiết
Lỗi cú pháp (Syntax / Indentation)	Các dòng print("gioi"), print("trung binh"), print("kha")	Các lệnh bên trong khối if, elif, else không được thụt lề (thường là 4 dấu cách). Python sẽ báo IndentationError: expected an indented block.
Lỗi kiểu dữ liệu (TypeError)	Diem_TB = Diem_toan + Diem_TA / 2	Hàm input() luôn trả về chuỗi ký tự (str). Khi đem Diem_TA (dạng str) chia cho 2 (int), Python sẽ báo TypeError: unsupported operand type(s) for /: 'str' and 'int'. Kể cả khi Diem_TA được đổi sang số, Diem_toan vẫn là str nên dấu + sẽ gây TypeError khi cộng str với float.
Lỗi logic toán học	Diem_TB = Diem_toan + Diem_TA / 2	Phép chia / có độ ưu tiên cao hơn phép cộng +, nên Python sẽ tính Diem_TA / 2 trước rồi mới cộng Diem_toan (thiếu dấu ngoặc (Diem_toan + Diem_TA) / 2).
Lỗi logic nghiệp vụ (xếp loại)	Khối elif và else	Điểm < 5 in ra "kha", trong khi điểm >= 5 (và < 8) lại in ra "trung binh". Thông thường mức >= 6.5 (hoặc >= 5 tùy quy ước) mới cao hơn "trung binh".
3. Nhận xét ưu điểm & nhược điểm
Ưu điểm:

Bạn đã biết dùng input() để lấy dữ liệu từ người dùng và dùng cấu trúc rẽ nhánh if / elif / else để phân loại kết quả.

Cách đặt tên biến (Diem_toan, Diem_TA, Diem_TB) có gợi ý ý nghĩa của biến.

Nhược điểm:

Quên ép kiểu dữ liệu từ chuỗi (str) sang số (float) sau khi dùng input().

Thiếu dấu ngoặc đơn khi tính trung bình cộng hai môn.

Quên thụt lề các câu lệnh bên trong if / elif / else khiến chương trình không thể chạy.

Thứ tự xếp loại ở nhánh elif và else chưa hợp lý, thông báo input("nhap diem:") cũng chưa phân biệt rõ đang nhập môn Toán hay môn Tiếng Anh.

4. Bảng điểm & Rubric đánh giá
Tiêu chí	Trọng số	Điểm đạt được	Nhận xét ngắn
Đúng chức năng	40%	8 / 40	Có khung nhập và rẽ nhánh, nhưng lỗi thụt lề, lỗi kiểu dữ liệu, sai công thức TB và ngược xếp loại làm chương trình chưa chạy đúng mục tiêu.
Thuật toán	30%	9 / 30	Ý tưởng chia 3 mức xếp loại có hình hài, nhưng thiếu ngoặc tính trung bình và logic phân tầng điểm chưa đúng.
Chất lượng code	20%	10 / 20	Tên biến dễ đoán, nhưng thiếu thụt lề chuẩn, thiếu chú thích và lời nhắc nhập chưa rõ môn nào.
Xử lý lỗi	10%	0 / 10	Chưa ép kiểu dữ liệu đầu vào và chưa kiểm tra các trường hợp nhập sai/điểm bất hợp lý.
Tổng điểm	100%	27 / 100	Cần sửa các lỗi nền tảng về kiểu dữ liệu, thụt lề và thứ tự phép tính.
5. Code Python cải tiến (dễ hiểu cho người mới)
Python
# Nhap diem Toan va Tieng Anh, dung float() de chuyen chuoi thanh so thap phan
diem_toan = float(input("Nhap diem Toan: "))
diem_ta = float(input("Nhap diem Tieng Anh: "))

# Kiem tra diem co nam trong khoang hop le tu 0 den 10 hay khong
if diem_toan < 0 or diem_toan > 10 or diem_ta < 0 or diem_ta > 10:
    print("Diem khong hop le! Vui long nhap diem tu 0 den 10.")
else:
    # Dung dau ngoac () de cong hai mon truoc roi moi chia 2
    diem_tb = (diem_toan + diem_ta) / 2
    print("Diem trung binh:", diem_tb)

    # Xep loai hoc luc theo thu tu tu cao xuong thap
    if diem_tb >= 8:
        print("Xep loai: gioi")
    elif diem_tb >= 6.5:
        print("Xep loai: kha")
    elif diem_tb >= 5:
        print("Xep loai: trung binh")
    else:
        print("Xep loai: yeu")
```