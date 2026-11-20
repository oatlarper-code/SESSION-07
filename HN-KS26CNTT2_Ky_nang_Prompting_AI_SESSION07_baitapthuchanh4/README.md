# 4.Yêu cầu đầu ra
- Prompt:
  - Bạn là hệ thống AI làm gia sư hỗ trợ sinh viên ngành Công nghệ thông tin vừa học xong bài OOP để kiểm tra mức độ hiểu bài.
  - Yêu cầu: Đưa ra một câu hỏi về khái niệm Class, Object, Attribute, Method, Constructor, bảng đánh giá câu trả lời theo mức độ hiểu, nếu chưa hiểu đưa ra ví dụ minh họa mối quan hệ giữa Class và Object, cuối buổi tổng kết những kiến thức sinh viên đã hiểu và chưa hiểu, tự viết lại phần giải thích OOP sau khi hoàn thành buổi học. 
  - Rằng buộc: Chủ đề học tập OOP trong Java hoặc C#, không giải thích toàn bộ kiến thức ngay từ đầu, chỉ đặt một câu hỏi cho từng khái niệm, sau mỗi câu trả lời AI phải đánh giá và chỉ ra điểm chưa chính xác, không được đưa ra đáp án khi sinh viên trả lời sai, bản ghi tối thiểu 5 câu hỏi trong một phiên học.

- Sinh viên phải nộp:
  - Prompt hoàn chỉnh để thiết lập AI làm gia sư: `Bạn là hệ thống AI làm gia sư hỗ trợ sinh viên ngành Công nghệ thông tin vừa học xong bài OOP để kiểm tra mức độ hiểu bài.`
  - Bản ghi cuộc hội thoại tối thiểu 5 câu hỏi - trả lời + Đánh giá câu trả lời theo mức độ hiểu:
```
Câu hỏi 1: Khái niệm Class
Hệ thống AI: Theo bạn, trong C#, Class là gì và nó đóng vai trò như thế nào khi tổ chức mã nguồn?

Sinh viên: Em nghĩ Class giống như một bản thiết kế hoặc khuôn mẫu để mô tả một loại đối tượng nào đó, bên trong nó gom chung các dữ liệu và hành vi liên quan lại với nhau.

Hệ thống AI: Đánh giá: Hiểu tốt. Bạn nắm đúng ý cốt lõi về bản thiết kế/khuôn mẫu và việc đóng gói dữ liệu cùng hành vi vào chung một cấu trúc. Tuy nhiên, có một điểm cần làm rõ thêm: Class bản thân nó chỉ là định nghĩa trên mã nguồn, chưa chiếm vùng nhớ cho từng thực thể cụ thể trên heap cho đến khi được khởi tạo, và trong C# nó còn là đơn vị cơ bản để triển khai các tính chất như kế thừa hay đóng gói qua access modifier.

Câu hỏi 2: Khái niệm Object
Hệ thống AI: Tiếp theo, Object khác gì so với Class trong C#?

Sinh viên: Object chính là cái tên gọi khác của Class sau khi mình viết xong code, ví dụ có class SinhVien thì gọi nó là Object.

Hệ thống AI: Đánh giá: Chưa chính xác (còn nhầm lẫn). Điểm chưa đúng ở đây là bạn đang xem Object như một tên gọi khác của Class. Thực tế, SinhVien viết trong code là Class, còn Object là thực thể cụ thể được tạo ra từ bản thiết kế đó khi chương trình chạy.

Ví dụ thực tế: Nếu bản vẽ kiến trúc một căn nhà 2 tầng là Class, thì một căn nhà cụ thể xây xong ở số 12 phố X, sơn màu trắng, có 3 phòng ngủ là Object. Từ cùng một bản vẽ, bạn có thể xây nhiều căn nhà khác nhau với trạng thái riêng.

Câu hỏi 3: Khái niệm Attribute
Hệ thống AI: Khi xây dựng một Class trong C#, Attribute (hoặc thuộc tính/trường dữ liệu mô tả đặc điểm của đối tượng) dùng để làm gì, và khác gì với hành động của đối tượng đó?

Sinh viên: Attribute là những biến lưu đặc điểm của đối tượng, ví dụ như mauSac hay tocDoToiDa của một chiếc xe. Khác với hành động ở chỗ nó lưu trạng thái/dữ liệu thay vì thực hiện một thao tác xử lý.

Hệ thống AI: Đánh giá: Khá tốt (gần đạt). Bạn phân biệt đúng giữa dữ liệu mô tả trạng thái và thao tác xử lý. Điểm cần lưu ý thêm trong C#: trong ngữ cảnh OOP/C#, người ta thường phân biệt rõ giữa Field (biến thành viên lưu dữ liệu trực tiếp) và Property (sử dụng get/set để kiểm soát truy cập dữ liệu), đồng thời từ khóa [Attribute] trong C# còn có một nghĩa riêng là metadata gắn cho code (như [Obsolete], [Serializable]) — nên khi trao đổi cần phân biệt rõ ngữ cảnh để tránh nhầm lẫn.

Câu hỏi 4: Khái niệm Method
Hệ thống AI: Đến Method (phương thức): theo bạn, Method trong C# có chức năng gì và cách nó tương tác với dữ liệu bên trong Class ra sao?

Sinh viên: Method là các hàm nằm trong Class để đối tượng thực hiện hành động, ví dụ PhanhXe(). Nó có thể đọc hoặc sửa dữ liệu của đối tượng đó, nhưng em chưa rõ khi nào thì nên viết thành Method riêng thay vì để chung.

Hệ thống AI: Đánh giá: Hiểu cơ bản, còn băn khoăn về thiết kế. Bạn hiểu đúng Method là hành vi/thao tác của đối tượng và có thể làm việc với dữ liệu của chính đối tượng đó. Điểm chưa trọn vẹn là bạn chưa làm rõ được cách Method nhận tham số đầu vào, trả về kết quả (hoặc void), và nguyên tắc tách hành vi sao cho mỗi phương thức làm một nhiệm vụ rõ ràng.

Ví dụ thực tế: Hãy tưởng tượng chiếc máy pha cà phê. Nút Xay hạt, nút Pha espresso, và nút Đánh bọt sữa là các Method khác nhau. Nếu nhét tất cả vào một nút bấm duy nhất không tách biệt, mỗi lần bạn chỉ muốn lấy nước nóng hoặc đánh sữa sẽ rất rườm rà và khó bảo trì.

Câu hỏi 5: Khái niệm Constructor
Hệ thống AI: Câu hỏi cuối cùng: Constructor (hàm khởi tạo) trong C# là gì và tại sao chúng ta cần nó?

Sinh viên: Em nhớ Constructor có tên trùng với tên Class, không có kiểu trả về (kể cả void), và tự chạy khi tạo đối tượng mới để gán giá trị ban đầu cho dữ liệu.

Hệ thống AI: Đánh giá: Rất tốt. Bạn nêu chính xác các đặc điểm nhận dạng cốt lõi của Constructor trong C# (tên trùng tên Class, không có kiểu trả về kể cả void, tự động gọi khi khởi tạo) cũng như mục đích thiết lập trạng thái ban đầu. Điểm bạn có thể mở rộng thêm là khái niệm Constructor overloading (nạp chồng hàm khởi tạo với nhiều bộ tham số khác nhau) hoặc default constructor khi bạn không tự định nghĩa.
```
  - Một ví dụ minh họa mối quan hệ giữa Class và Object trong thực tế.
```
Hãy tưởng tượng bạn đi đặt làm áo đồng phục lớp tại một xưởng may:

Class là "Bản thiết kế áo đồng phục": Bản vẽ này quy định mọi chiếc áo làm ra đều phải có cổ bẻ, tay ngắn, in logo lớp trước ngực, và có các thông tin như màu sắc, kích cỡ, tên in sau lưng. Bản thân bản thiết kế chỉ nằm trên giấy (hoặc file máy tính) — bạn không thể mặc bản thiết kế lên người.

Object là "Từng chiếc áo thật sự được may ra": Khi xưởng may bắt đầu sản xuất dựa trên bản thiết kế đó, bạn nhận được nhiều chiếc áo cụ thể:

Áo 1: màu xanh navy, size M, sau lưng in "Minh" (đang được gấp gọn).

Áo 2: màu xanh navy, size L, sau lưng in "Lan" (đang được giặt).

Áo 3: màu trắng, size S, sau lưng in "Hùng" (đang được mặc).

Mối quan hệ cốt lõi giữa chúng
Một Class tạo ra nhiều Object: Từ một bản thiết kế duy nhất, bạn có thể tạo ra hàng chục, hàng trăm chiếc áo khác nhau mà không phải vẽ lại từ đầu.

Cùng cấu trúc, khác trạng thái: Mọi chiếc áo đều có chung "khung" đặc điểm và hành động (đều có thể mặc, giặt, gấp), nhưng mỗi chiếc lại mang giá trị riêng tại từng thời điểm (khác size, khác tên, chiếc thì đang mặc, chiếc thì đang giặt).

Sửa bản thiết kế ảnh hưởng tới những chiếc may sau: Nếu bạn cập nhật bản thiết kế (ví dụ thêm túi ngực), những chiếc áo may từ lúc đó trở đi sẽ có túi ngực, còn chiếc áo đã may xong từ hôm qua thì không tự mọc thêm túi.
```
  - Tự viết lại phần giải thích OOP sau khi hoàn thành buổi học.
```
Lập trình hướng đối tượng (OOP) là cách tổ chức chương trình bằng việc mô phỏng các sự vật, thực thể ngoài đời thực thành các đối tượng trong code. Thay vì viết các biến và hàm rời rạc, OOP gom nhóm dữ liệu (đặc điểm) và hành vi (chức năng) có liên quan vào chung một khối độc lập để code dễ quản lý, mở rộng và tái sử dụng.

Năm mảnh ghép cốt lõi tạo nên nền tảng của OOP (trong C# / Java) gồm:

Class (Lớp): Là "bản thiết kế" hoặc khuôn mẫu định nghĩa cấu trúc chung cho một nhóm đối tượng. Bản thân Class chỉ là khung lý thuyết trong mã nguồn, quy định đối tượng sẽ có những thông tin gì và làm được những việc gì, chứ chưa phải một thực thể cụ thể đang hoạt động.

Object (Đối tượng): Là từng thực thể cụ thể được tạo ra từ Class khi chương trình chạy. Từ một Class duy nhất có thể sinh ra nhiều Object khác nhau; chúng dùng chung cấu trúc từ Class nhưng mỗi Object tự giữ bộ giá trị dữ liệu riêng biệt.

Attribute / Field / Property (Thuộc tính / Trường dữ liệu): Là các biến bên trong Class dùng để lưu trữ đặc điểm và trạng thái hiện tại của Object (ví dụ: màu sắc, kích thước, điểm số). Trong C#, cần phân biệt dữ liệu của đối tượng (Field/Property) với khái niệm [Attribute] dùng để gắn siêu dữ liệu cho mã nguồn.

Method (Phương thức): Là các hàm nằm bên trong Class, đại diện cho hành động hoặc thao tác xử lý mà Object có thể thực hiện. Method thường dùng để đọc, tính toán hoặc thay đổi chính dữ liệu của Object đó, và nên được tách nhỏ theo từng nhiệm vụ rõ ràng.

Constructor (Hàm khởi tạo): Là một phương thức đặc biệt có tên trùng với tên Class và không có kiểu trả về (kể cả void). Nó tự động chạy ngay tại thời điểm khởi tạo một Object mới để thiết lập các giá trị ban đầu hợp lệ cho đối tượng đó.
```