# Churn-Analysis
Case study: Phân tích tỉ lệ rời bỏ của khách hàng với SQL và Power BI
Ngành viễn thông có tính cạnh tranh cao và khách hàng có nhiều lựa chọn để lựa chọn. Các công ty phụ thuộc rất nhiều vào việc giữ chân khách hàng để đảm bảo sự tăng trưởng và thành công liên tục. Chúng ta sẽ đi trả lời các câu hỏi để giải giảm tỉ lệ rời bỏ cảu khách hàng thông qua bộ dữ liệu Maven Telecom’s :
1. Các yếu tố chính dẫn đến sự rời bỏ là gì?
2. Hồ sơ lý tưởng (đặc điểm chung) của một khách hàng rời bỏ là gì?
3. Maven Telecom có thể thực hiện những bước nào để giảm tỷ lệ rời bỏ và giữ chân khách hàng?

Định hướng
Sử dụng 2 công nghệ phổ biến hiện nay để thao tác, xử lý và trực quan hóa kết quả
Các bước:
1.	Hiểu dữ liệu - đọc Dictionary để làm sạch
2.	Thực hiện các tính toán toán tỷ lệ rời bỏ
3.	Hiểu được thông tin mang lại
4.	Đưa ra giải pháp giảm tỉ lệ rời bỏ cho Maven Telecom 
5.	Trực quan hóa và trình bày
Làm sạch dữ liệu – Window Funtion
Trong thực tế các thao tác tổng hợp xử lý dữ liệu sẽ rất mất thời gian và dựa trên nhiều yếu tố khác nhau. Chú ý các kỹ thuật khai phá dữ liệu cũng như xử lý các giá trị null hay giá trị thiếu sẽ linh hoạt theo từng lĩnh vực ngành nghề và công ty. Tuy nhiên tập dữ liệu của chúng ta nhìn nhận là đã hoàn chỉnh và có thể đi vào phân tích:
 
Phân tích
1.	Khai phá dữ liệu
1a. Tổng số lượng khách hàng 
 
1b. Có bao nhiêu khách hàng rời bỏ và phần trăm
Maven đã mất 1869 khách hàng, chiếm 26,5% tổng số khách hàng trong khoảng thời gian dữ liệu này được ghi lại. Đó là một con số khá quan trọng và chúng tôi sẽ điều tra lý do tại sao họ rời đi.
 
Chú ý rằng chúng ta đang sử dụng hàm cửa sổ để tính toán để tính toán. Và đó cũng là cấu trúc sẽ được sử dụng liên tục trong các phân tích sâu chúng ta tiếp theo. Các phân tiếp theo sẽ lấy các trường dữ liệu khác và tùy theo yêu cầu sẽ dùng hàm cửa sổ sum, count… để giải quyết yêu cầu.
1c. Doanh thu mất do khách hàng rời bỏ?
Maven Telecom đã mất 3,7 triệu đô và chiếm 17% tổng doanh thu trong 21 triệu đô doanh thu
 
1d. Loại khách hàng chính rời bỏ công ty
 
Nhận thấy rằng ~42% khách hàng rời bỏ đã dành 6 tháng hoặc ít hơn tại Maven trước khi rời đi.
Gần một nửa số khách hàng rời bỏ có thời gian làm việc tương đối ngắn với công ty, vì vậy Maven có cơ hội cải thiện khả năng giữ chân khách hàng đối với những khách hàng mới hơn.
1e. Phương thức thanh toán mà khách hàng rời bỏ nhiều
71,1% khách hàng rời bỏ sử dụng Rút tiền qua ngân hàng làm phương thức thanh toán cho các dịch vụ của họ cho Maven Telecom. Đây có thể là một lý do cho tỷ lệ churn? Chúng tôi sẽ điều tra thêm.
 
2.	Nhân khẩu học
2a. Tỉ lệ giới tính 
 Tỷ lệ giới tính khá tương đồng nên yếu tố giới tính nhìn nhận không ảnh hưởng đến sự rời bỏ của khách hàng.
2b. Tình trạng hôn nhân
SQL
3c. Nhóm tuổi
Trong file SQL sẽ đầy đủ phân hệ theo các yếu tố ảnh hưởng đến tỷ lệ rời bỏ của khách hàng và sử dụng chung một cấu trúc % dựa trên hàm cửa sổ.
3.	Thông tin chi tiết từ phân tích
Maven có 1869 khách hàng rời bỏ, chiếm 3,7 triệu đô la trong tổng doanh thu bị mất.
42% khách hàng rời bỏ chỉ ở lại trong 6 tháng hoặc ít hơn.
3 lý do hàng đầu dẫn đến việc rời bỏ là đối thủ cạnh tranh đưa ra ưu đãi tốt hơn, đối thủ cạnh tranh có thiết bị tốt hơn và thái độ của nhân viên hỗ trợ.
Maven đã thua ~1,7 triệu đô la cho các đối thủ cạnh tranh, khiến nó trở thành loại khuấy đảo đắt nhất
Các chỉ số chính về sự rời bỏ là loại hợp đồng hàng tháng, Không có hỗ trợ công nghệ cao cấp, Internet cáp quang, Không có ưu đãi khuyến mại và Ưu đãi E.
70% khách hàng chuyển sang đối thủ cạnh tranh đã sử dụng Fiber Optic, 56% không nhận được ưu đãi khuyến mại, 89% có hợp đồng hàng tháng
4.	Chiến lược giữ chân khách hàng
Chương trình khách hàng thân thiết: Vì lý do hàng đầu khiến khách hàng rời bỏ là 'đối thủ cạnh tranh đưa ra ưu đãi tốt hơn' và hơn một nửa số khách hàng bị rời bỏ không có bất kỳ ưu đãi khuyến mại nào, Maven có thể triển khai các chương trình khách hàng thân thiết khác nhau để giữ chân khách hàng của họ. Chẳng hạn, họ có thể thưởng cho khách hàng ký hợp đồng dài hạn với mức chiết khấu, nâng cấp miễn phí hoặc các tính năng bổ sung.
Cải thiện hỗ trợ khách hàng: Đầu tư vào đào tạo và phát triển nhân viên hỗ trợ để đảm bảo họ cung cấp dịch vụ khách hàng xuất sắc. Điều này có thể bao gồm các buổi huấn luyện và phản hồi thường xuyên, cũng như các biện pháp khuyến khích nhân viên nhận được phản hồi tích cực của khách hàng.
Tạo ra các thiết bị tốt hơn: Đánh giá các tính năng, hiệu suất và giá cả của các thiết bị của bạn để đảm bảo chúng phù hợp với các tiêu chuẩn và nhu cầu của thị trường.
Hỗ trợ kỹ thuật cao cấp: Vì những khách hàng không có quyền truy cập vào hỗ trợ kỹ thuật cao cấp có nhiều khả năng rời bỏ, Maven nên xem xét cung cấp dịch vụ này cho tất cả khách hàng.
Cải thiện dịch vụ cáp quang: Đầu tư vào việc cải thiện các dịch vụ cáp quang của bạn như tốc độ nhanh hơn, kết nối ổn định hơn và hỗ trợ khách hàng tốt hơn cho khách hàng cáp quang.
Thu hút khách hàng có giá trị cao: Ưu tiên thu hút những khách hàng này để ngăn họ rời đi. Cung cấp các ưu đãi được cá nhân hóa, gửi thông tin liên lạc được nhắm mục tiêu và cung cấp hỗ trợ kỹ thuật cao cấp để đảm bảo những khách hàng này vẫn hài lòng với dịch vụ của họ.
Dịch vụ sau bán hàng: Lên lịch kiểm tra thường xuyên với khách hàng để đảm bảo họ vẫn hài lòng với dịch vụ của mình. Những đăng ký này có thể ở dạng khảo sát, gọi điện thoại hoặc liên lạc qua email.
Xem thêm về văn bản nguồn nàyNhập văn bản nguồn để có thông tin dịch thuật bổ sung
Gửi ý kiến phản hồi
Bảng điều khiển bên
5.	Dashboard in Power BI

 
 
