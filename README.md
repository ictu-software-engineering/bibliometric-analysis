# Giới thiệu Phân tích trắc lượng thư mục (bibliometric analysis)
Phân tích trắc lượng thư mục là một phương pháp phổ biến và nghiêm ngặt để khám phá và phân tích khối lượng lớn dữ liệu khoa học. Nó cho phép chúng ta giải mã các sắc thái tiến hóa của một lĩnh vực cụ thể, đồng thời làm sáng tỏ các lĩnh vực mới nổi trong lĩnh vực đó. Tuy nhiên, ứng dụng của nó trong nghiên cứu kinh doanh còn tương đối mới và trong nhiều trường hợp khác còn hạn chế. Vì vậy, khoá học này nhằm cung cấp phương pháp trắc lượng thư mục, đặc biệt tập trung vào các kỹ thuật khác nhau, đồng thời đưa ra các hướng dẫn từng bước để thực hiện phân tích một cách nghiêm ngặt. Để đạt được mục tiêu này, chúng ta cũng làm sáng tỏ thời điểm và cách thức sử dụng phân tích trắc lượng thư mục so với các kỹ thuật tương tự khác như phân tích tổng hợp và đánh giá tài liệu có hệ thống. Nhìn chung, bài viết này sẽ là một nguồn tài liệu hữu ích để hiểu rõ hơn về các kỹ thuật và quy trình sẵn có để thực hiện các nghiên cứu sử dụng phân tích trắc lượng thư mục.

## Đặt vấn đề
Bibliometric analysis phổ biến có thể là do (1) các phần mềm như Gephi, Leximancer, VOSviewer + Scopus và Web of Science, và (2) sự tổng hợp liên ngành. Bibliometric analysis cho phép (1) xử lý khối lượng lớn dữ liệu khoa học và (2) tạo ra tác động nghiên cứu cao.

Bibliometric analysis được dùng để
- Khám phá các xu hướng mới nổi trong hoạt động của bài báo và tạp chí,
- Mô hình cộng tác và các thành phần nghiên cứu 
- Khám phá cấu trúc trí tuệ của một lĩnh vực cụ thể trong tài liệu hiện có
  
Dữ liệu trong phân tích trắc lượng thư mục có xu hướng lớn (ví dụ: hàng trăm, nếu không phải hàng nghìn) và có tính chất khách quan (ví dụ: số lượng trích dẫn và ấn phẩm, số lần xuất hiện của từ khóa và chủ đề). Bibliometric analysis rất hữu ích cho việc giải mã và lập bản đồ kiến thức khoa học. Do đó, các nghiên cứu trắc lượng thư mục được thực hiện tốt có thể xây dựng nền tảng vững chắc để phát triển một lĩnh vực theo những cách mới và có ý nghĩa. Vì vậy, nó cho phép và trao quyền cho các học giả (1) có được cái nhìn tổng thể toàn diện, (2) xác định các lỗ hổng kiến thức, (3) rút ra được tính mới ý tưởng để đi sâu hơn, và (4) định vị những đóng góp của mình cho lĩnh vực này.

Bất chấp những giá trị của nó, phân tích trắc lượng thư mục vẫn còn tương đối mới và trong nhiều trường hợp, việc thực hiện nó không tận dụng được hết tiềm năng của nó. Điều này xảy ra khi các nghiên cứu đo thư mục dựa vào một tập hợp hạn chế dữ liệu và kỹ thuật đo thư mục và chỉ cung cấp sự hiểu biết từng phần về lĩnh vực đang được nghiên cứu (ví dụ: phân tích hiệu suất mà không lập bản đồ khoa học). 

Để giải quyết vấn đề trên, bài viết này nhằm mục đích cung cấp (1) cái nhìn tổng quan về phương pháp trắc lượng thư mục và (2) hướng dẫn từng bước để tiến hành phân tích trắc lượng thư mục. Để đạt được mục đích này, đầu tiên bài viết trình bày tổng quan về phân tích trắc thư mục và hướng dẫn cách thực hiện nó. Thứ hai, bài viết đưa ra một số gợi ý liên quan đến các kỹ thuật khác nhau có thể được sử dụng để phân tích trắc lượng thư mục và khi nào chúng nên được sử dụng.

## Phương pháp trắc lượng thư mục
Phương pháp trắc lượng thư mục gói gọn việc áp dụng các kỹ thuật định lượng (tức là phân tích đo thư mục - ví dụ: phân tích trích dẫn) trên dữ liệu đo thư mục (ví dụ: đơn vị xuất bản và trích dẫn). Cuộc thảo luận ban đầu về trắc lượng thư mục bắt đầu từ những năm 1950, điều này cho thấy phương pháp trắc lượng thư mục không phải là mới. Tuy nhiên, sự phát triển của trắc lượng thư mục mới thực sự phát triển trong những năm gần đây. Điều này có thể là do sự phát triển của chính nghiên cứu khoa học. Tuy nhiên, các bộ dữ liệu thư mục lớn đã làm cho các phương pháp đánh giá cổ điển trở nên cồng kềnh và không thực tế. Đáng chú ý là sự xuất hiện của các cơ sở dữ liệu khoa học như Scopus và Web of Science đã khiến việc thu thập khối lượng lớn dữ liệu đo thư mục trở nên tương đối dễ dàng và các phần mềm đo thư mục như Gephi, Leximancer và VOSviewer cho phép phân tích dữ liệu đó một cách rất thực tế, từ đó nâng cao sự quan tâm của giới học thuật đối với việc phân tích trắc lượng thư mục trong thời gian gần đây. Thật vậy, phương pháp đo thư mục đã được áp dụng trong nhiều lĩnh vực khác nhau, trong đó việc áp dụng phép đo thư mục bao gồm từ việc nghiên cứu xuất bản đến các mô hình cộng tác và khám phá cấu trúc trí tuệ của lĩnh vực nghiên cứu. Ở đây, lĩnh vực nghiên cứu cũng có thể biểu hiện dưới dạng tạp chí. 

Tại thời điểm này, điều quan trọng là phải so sánh phân tích trắc lượng thư mục với các phương pháp đánh giá thay thế được sử dụng thường xuyên khác như phân tích tổng hợp và đánh giá tài liệu có hệ thống. Về bản chất, phân tích tổng hợp đánh giá (1) “sức mạnh và hướng tổng thể của các tác động hoặc mối quan hệ” và (2) “sự khác biệt giữa các nghiên cứu trong việc phân bổ các ước tính quy mô hiệu ứng và các yếu tố giải thích sự khác biệt này”, trong khi các đánh giá tài liệu có hệ thống, chẳng hạn như các đánh giá dựa trên lĩnh vực, phương pháp và lý thuyết, gói gọn việc tiếp thu, sắp xếp và đánh giá tài liệu hiện có bằng cách sử dụng hệ thống, thường được các học giả thực hiện thủ công (ví dụ: phân tích nội dung và chủ đề).

Tương tự như phân tích trắc lượng thư mục, phân tích tổng hợp có thể xử lý một lượng lớn tài liệu và cung cấp bản tóm tắt đầy đủ của một lĩnh vực nhất định, mặc dù tài liệu được xem xét có xu hướng ít đa dạng hơn và tính không đồng nhất của các nghiên cứu hiện tại cũng như sự tồn tại của khuynh hướng xuất bản có thể có ảnh hưởng bất lợi đến tính hợp lệ của các kết quả thu được thông qua phân tích tổng hợp. Ngược lại, việc đánh giá tài liệu có hệ thống sử dụng các phương pháp cổ điển đòi hỏi phạm vi nghiên cứu hẹp và do đó có xu hướng bao gồm số lượng bài báo ít hơn để xem xét (ví dụ: từ hàng chục [ví dụ: 40] đến hàng trăm thấp [ví dụ: 100–300]). Theo nghĩa đó, các bài đánh giá tài liệu có hệ thống sẽ phù hợp hơn với các lĩnh vực nghiên cứu hạn chế (ví dụ: mức độ tương tác của khách hàng trên mạng xã hội) hoặc các lĩnh vực nghiên cứu thích hợp (ví dụ: tiếp thị người ảnh hưởng trên mạng xã hội). Không giống như các bài đánh giá tài liệu có hệ thống có xu hướng dựa vào các kỹ thuật định tính, vốn có thể bị ảnh hưởng bởi sự thiên vị diễn giải của các học giả thuộc các nền tảng học thuật khác nhau, phân tích trắc lượng thư mục và phân tích tổng hợp dựa vào các kỹ thuật định lượng và do đó có thể tránh hoặc giảm thiểu sự thiên vị đó.

Vì phân tích tổng hợp và phân tích trắc lượng thư mục đều có bản chất định lượng nên sự khác biệt giữa hai phương pháp có thể gây nhầm lẫn cho một số học giả. Để làm sáng tỏ sự khác biệt này, các học giả cần lưu ý rằng các phương pháp định lượng của họ tương đối khác nhau về cách sử dụng, mặc dù cả hai đều có thể xử lý một lượng lớn tài liệu. Cụ thể, phân tích tổng hợp tập trung vào việc tóm tắt bằng chứng thực nghiệm bằng cách phân tích hướng và sức mạnh của tác động cũng như mối quan hệ giữa các biến số và “hữu ích trong việc giải quyết các câu hỏi nghiên cứu mở với dữ liệu gần với kết quả chính xác hơn so với dữ liệu được báo cáo trong bất kỳ nghiên cứu sơ cấp nào”. Nó được thực hiện để làm sáng tỏ những phát hiện thực nghiệm hỗn hợp và các điều kiện biên. Do đó, phân tích tổng hợp thường được sử dụng làm công cụ mở rộng lý thuyết. Ngược lại, phân tích trắc lượng thư mục tóm tắt cấu trúc trắc lượng thư mục và trí tuệ của một lĩnh vực bằng cách phân tích các mối quan hệ xã hội và cấu trúc giữa các thành phần nghiên cứu khác nhau (ví dụ: tác giả, quốc gia, tổ chức, chủ đề).

Tóm lại, việc sử dụng bất kỳ phương pháp nào trong ba phương pháp xem xét được thảo luận ở đây đều phụ thuộc vào mục tiêu của việc xem xét cũng như tầm quan trọng và tính chất của tài liệu thu thập được. Tuy nhiên, các phương pháp đánh giá này vẫn bổ sung cho nhau và mang lại những lợi thế riêng cho các học giả quan tâm đến việc sử dụng chúng.

1. Phương pháp trắc lượng thư mục (bibliometric-analysis)
   - Mục tiêu: Tóm tắt số lượng lớn dữ liệu trắc lượng thư mục để trình bày trạng thái cấu trúc trí tuệ và các xu hướng mới nổi của một chủ đề hoặc lĩnh vực nghiên cứu.
   - Sử dụng khi: (1) Khi phạm vi xem xét rộng. (2) Khi tập dữ liệu quá lớn để xem xét thủ công.
   - Không nên sử dụng khi: (2) Khi phạm vi xem xét hẹp. (2) Khi tập dữ liệu đủ nhỏ và có thể quản lý được để nội dung của nó có thể được xem xét thủ công
   - Phạm vi: Rộng
   - Dữ liệu: Lớn
   - Phương pháp: (1) Định lượng (đánh giá và giải thích). (2) Định tính (chỉ giải thích)
3. Phương pháp phân tích tổng hợp (meta-analysis review)
  - Mục tiêu: Tóm tắt bằng chứng thực nghiệm về mối quan hệ giữa các biến đồng thời khám phá các mối quan hệ chưa được nghiên cứu trong các nghiên cứu hiện có.
  - Sử dụng khi: (1) Khi trọng tâm của việc đánh giá là tóm tắt kết quả thay vì tập trung vào nội dung có thể rộng hoặc cụ thể. (2) Khi các nghiên cứu trong lĩnh vực này là đồng nhất. (3) Khi số lượng nghiên cứu đồng nhất sẵn có đủ cao. (4) Khi số lượng nghiên cứu đồng nhất còn lại sau khi loại bỏ các nghiên cứu chất lượng thấp đủ cao
  - Không nên sử dụng khi: (1) Khi các nghiên cứu trong lĩnh vực này không đồng nhất. (2) Khi số lượng nghiên cứu đồng nhất tương đối thấp. (3) Khi số lượng nghiên cứu đồng nhất chất lượng cao tương đối thấp.
  - Phạm vi: Cụ thể 
  - Dữ liệu: Nhỏ nhưng chất lượng
  - Phương pháp: Định lượng (đánh giá và giải thích)
5. Phương pháp phân tích tài liệu có hệ thống (systematic literature review)
- Mục tiêu: Tóm tắt và tổng hợp những phát hiện của tài liệu hiện có về một chủ đề hoặc lĩnh vực nghiên cứu.
- Sử dụng khi: (1) Khi phạm vi xem xét là cụ thể. (2) Khi tập dữ liệu đủ nhỏ và có thể quản lý được để nội dung của nó có thể được xem xét thủ công.
- Không nên sử dụng khi: (1) Khi phạm vi xem xét rộng. (2) Khi tập dữ liệu quá lớn để xem xét thủ công.
- Phạm vi: Hẹp
- Dữ liệu: Nhỏ
- Phương pháp: Định tính (đánh giá và giải thích)
## Các công cụ và kỹ thuật dùng để phân tích trắc lượng thư mục
Các kỹ thuật phân tích trắc lượng thư mục được thể hiện qua hai loại: (1) phân tích hiệu suất và (2) lập bản đồ khoa học. Về bản chất, phân tích hiệu suất tính đến sự đóng góp của các thành phần nghiên cứu, trong khi việc lập bản đồ khoa học tập trung vào mối quan hệ giữa các thành phần nghiên cứu. Các phần phụ tiếp theo làm sáng tỏ các kỹ thuật có sẵn để phân tích hiệu suất và lập bản đồ khoa học

![Toolbox](/images/tool_technique.jpeg)

### Phân tích hiệu suất (Performance analysis)
Phân tích hiệu suất xem xét sự đóng góp của các thành phần nghiên cứu cho một lĩnh vực nhất định. Phân tích mô tả là đặc điểm nổi bật của dạng nghiên cứu này. Phân tích hiệu suất có thể được tìm thấy trong hầu hết các đánh giá tổng quan, ngay cả trong những đánh giá không tham gia lập bản đồ khoa học, bởi vì thông lệ tiêu chuẩn trong các đánh giá là trình bày hiệu suất của các thành phần nghiên cứu khác nhau (ví dụ: tác giả, tổ chức, quốc gia và tạp chí) trong lĩnh vực này, tương tự như kiến thức nền tảng hoặc hồ sơ của những người tham gia thường được trình bày trong nghiên cứu thực nghiệm mặc dù mang tính phân tích nhiều hơn.

Có nhiều tiêu chí/thước đo được dùng để phân tích hiệu suất. Các thước đo nổi bật nhất là số lượng ấn phẩm và trích dẫn mỗi năm hoặc theo mỗi thành phần nghiên cứu, trong đó ấn phẩm là đại diện cho năng suất, trong khi trích dẫn là thước đo tác động và ảnh hưởng. Các tiêu chí khác như trích dẫn trên mỗi bài báo và chỉ số h kết hợp cả trích dẫn và bài báo để đo lường hiệu suất của các thành phần nghiên cứu. Phân tích, mặc dù mang tính mô tả, thừa nhận tầm quan trọng của các thành phần khác nhau trong một lĩnh vực nghiên cứu. 
1. Các số liệu liên quan đến xuất bản
- Tổng số công bố (TP): Tổng công bố của thành phần nghiên cứu
- Các công bố của giới học thuật (academia) (TP-A): Tổng số công bố của các thành phần nghiên cứu từ giới học thuật
- Công bố từ ngành công nghiệp (industry) (TP-I): Tổng số ấn phẩm nghiên cứu từ ngành
- Các công bố từ sự hợp tác giữa giới học thuật và ngành công nghiệp (TP-AI): Tổng số ấn phẩm hợp tác nghiên cứu từ sự hợp tác giữa giới học thuật và ngành công nghiệp
- Số tác giả đóng góp (NCA): Tổng số tác giả đóng góp cho các công bố của đối tượng nghiên cứu
- Các công bố một tác giả (SA):  Tổng số ấn phẩm độc quyền theo lĩnh vực nghiên cứu
- Công bố đồng tác giả (CA): Tổng số bài báo đồng tác giả theo đối tượng nghiên cứu
- Số năm hoạt động xuất bản (NAY): Số năm thành viên nghiên cứu ghi lại một ấn phẩm
- Năng suất trên mỗi năm xuất bản hoạt động (PAY): TP → NAY

2. Số liệu liên quan đến trích dẫn
- Tổng số trích dẫn (TC): Tổng số trích dẫn của lĩnh vực nghiên cứu
- Số trích dẫn trung bình (AC): Số trích dẫn trung bình (ví dụ: trên mỗi bài báo, mỗi năm, mỗi kỳ) 

3. Các số liệu liên quan đến trích dẫn và xuất bản
- Chỉ số hợp tác (CI): (NCA ÷ TP) ÷ TP (tức là mức độ hợp tác của đối tượng nghiên cứu)
- Hệ số cộng tác (CC): 1 – (TP ÷ NCA) (tức là chuẩn hóa mức độ cộng tác của tác giả trong khoảng từ 0 đến 1)
- Số công bố được trích dẫn (NCP):  Số công bố của thành phần nghiên cứu được trích dẫn
- Tỷ lệ công bố được trích dẫn (PCP): NCP → TP
- Trích dẫn trên mỗi ấn phẩm được trích dẫn (CCP): TC cho NCP
- h-index (h): h số lượng ấn phẩm được trích dẫn ít nhất h lần (tức là thước đo mức độ ảnh hưởng)
- g-index (g):  g số lượng ấn phẩm nhận được ít nhất g2 trích dẫn (tức là thước đo tác động)
- i-index (i-10, i-100, i-200): i số lượng công bố được trích dẫn ít nhất i lần (ví dụ: i = 10, 100, 200, v.v.)

### Bản đồ khoa học (Science Mapping)
Lập bản đồ khoa học xem xét mối quan hệ giữa các thành phần nghiên cứu. Việc phân tích liên quan đến sự tương tác trí tuệ và kết nối cấu trúc giữa các thành phần nghiên cứu. Các kỹ thuật lập bản đồ khoa học bao gồm phân tích trích dẫn, phân tích đồng trích dẫn, ghép nối thư mục, phân tích đồng từ và phân tích đồng tác giả. Những kỹ thuật như vậy, khi kết hợp với phân tích mạng, là công cụ trình bày cấu trúc trắc lượng thư mục và cấu trúc trí tuệ của lĩnh vực nghiên cứu
1. Phân tích trích dẫn (citation analysis)
   - Mục đích: Để phân tích mối quan hệ giữa các ấn phẩm bằng cách xác định các ấn phẩm có ảnh hưởng nhất trong một lĩnh vực nghiên cứu.
   - Ví dụ mẫu: [citation analysis](https://journals.lww.com/jcma/Fulltext/2022/03000/Classification_and_citation_analysis_of_the_100.20.aspx)

Phân tích trích dẫn là một kỹ thuật cơ bản để lập bản đồ khoa học hoạt động dựa trên giả định rằng các trích dẫn phản ánh mối liên kết trí tuệ giữa các bài báo được hình thành khi một bài báo này trích dẫn bài báo kia. Trong phân tích này, tác động của một bài báo được xác định bởi số lượng trích dẫn mà nó nhận được. Việc phân tích cho phép xác định chắc chắn các bài báo có ảnh hưởng nhất trong một lĩnh vực nghiên cứu. Mặc dù có nhiều phương pháp khác nhau (ví dụ: số liệu mạng) để xác định tầm quan trọng của các bài báo trong lĩnh vực nghiên cứu, thước đo khách quan và đơn giản nhất về tác động của nó là trích dẫn của nó. Do đó, bằng cách sử dụng các trích dẫn, người ta có thể phân tích các bài báo có ảnh hưởng nhất trong một lĩnh vực nghiên cứu để hiểu rõ hơn về động lực trí tuệ của lĩnh vực đó.

3. Phân tích đồng trích dẫn (co-citation analysis)
   - Mục đích: Phân tích mối quan hệ giữa các bài báo được trích dẫn để hiểu sự phát triển của các chủ đề nền tảng trong một lĩnh vực nghiên cứu.
   - Ví dụ mẫu: [co-citation analysis](https://files.eric.ed.gov/fulltext/EJ1260330.pdf)
  
Phân tích đồng trích dẫn là một kỹ thuật lập bản đồ khoa học trong đó giả định các bài báo được trích dẫn cùng nhau thường xuyên có chủ đề tương tự nhau. Phân tích có thể được sử dụng để tiết lộ cấu trúc trí tuệ của một lĩnh vực nghiên cứu, chẳng hạn như các chủ đề cơ bản. Trong mạng đồng trích dẫn, hai bài báo được kết nối với nhau khi chúng cùng xuất hiện trong danh sách tham khảo của bài báo khác. Lợi ích của việc sử dụng phân tích đồng trích dẫn là ngoài việc tìm kiếm các bài báo có ảnh hưởng nhất, các học giả còn có thể khám phá các cụm chủ đề. Ở đây, các cụm chuyên đề được hình thành dựa trên các bài báo được trích dẫn. Tuy nhiên, phân tích đồng trích dẫn chỉ tập trung vào các bài báo được trích dẫn nhiều và loại bỏ các bài báo mới xuất bản hoặc nằm ngoài các cụm chủ đề của nó. Theo nghĩa đó, phân tích đồng trích dẫn phù hợp với các học giả muốn khám phá các bài báo có ảnh hưởng sâu rộng và nền tảng kiến thức.

5. Đồng/Ghép thư mục (bibliographic coupling)
   - Mục đích: Để phân tích mối quan hệ giữa các bài báo trích dẫn để hiểu sự phát triển định kỳ hoặc hiện tại của các chủ đề trong một lĩnh vực nghiên cứu.
   - Ví dụ mẫu: [bibliographic coupling](https://www.tandfonline.com/doi/pdf/10.1080/23311975.2022.2124594)

Ghép nối thư mục là một kỹ thuật lập bản đồ khoa học hoạt động dựa trên giả định rằng hai bài báo có chung tài liệu tham khảo cũng giống nhau về nội dung. Phân tích tập trung vào việc phân chia các bài báo thành các cụm chuyên đề dựa trên các tài liệu tham khảo được chia sẻ và được sử dụng tốt nhất trong một khung thời gian cụ thể. Ở đây, các cụm chủ đề được hình thành dựa trên các bài báo trích dẫn, và do đó, các bài báo gần đây và chuyên đề có thể đạt được khả năng hiển thị thông qua việc ghép nối thư mục (không giống như phân tích đồng trích dẫn). Theo nghĩa đó, việc ghép nối thư mục phù hợp với các học giả muốn khám phá một loạt các chủ đề và những phát triển mới nhất của nó. Do đó, việc phân tích có thể cung cấp sự trình bày về hiện tại của lĩnh vực nghiên cứu


7. Phân tích từ đồng nghĩa (co-word analysis)
   - Mục đích: Để khám phá mối quan hệ hiện tại hoặc tương lai giữa các chủ đề trong lĩnh vực nghiên cứu bằng cách tập trung vào nội dung văn bản của chính bài báo đó
   - Ví dụ mẫu: [co-word](https://www.sciencedirect.com/science/article/pii/S0148296321007505)

Trong khi ba kỹ thuật lập bản đồ khoa học trước đây tập trung vào các bài báo thì đơn vị phân tích để phân tích từ đồng nghĩa là “từ”. Nói cách khác, không giống như phân tích trích dẫn, phân tích đồng trích dẫn và ghép nối thư mục, sử dụng các bài báo được trích dẫn hoặc trích dẫn làm tiêu điểm hoặc đại diện, phân tích từ đồng nghĩa là một kỹ thuật kiểm tra nội dung thực tế của chính bài báo đó. Các từ trong phân tích đồng từ thường bắt nguồn từ “từ khóa tác giả” và nếu không có nó, các từ đáng chú ý cũng có thể được trích xuất từ “tiêu đề bài viết”, “tóm tắt” và “văn bản đầy đủ” để phân tích. Tương tự như phân tích đồng trích dẫn, phân tích đồng từ giả định rằng các từ thường xuất hiện cùng nhau có mối quan hệ chủ đề với nhau.

Tuy nhiên, việc sử dụng từ ngữ làm đơn vị phân tích cũng có những nhược điểm. Ví dụ, một số từ nhất định được sử dụng trong nhiều ngữ cảnh và do đó, việc đọc (lại) các bài báo trở nên cần thiết để hiểu ý nghĩa của mối quan hệ giữa các từ. Ngoài ra, một số từ có thể rất chung chung (ví dụ: tên trường chủ đề—ví dụ: quảng cáo) và do đó, có thể gặp khó khăn khi gán chúng cho bất kỳ cụm chủ đề nào.

Để giảm thiểu những nhược điểm tiềm ẩn của việc phân tích từ đồng nghĩa, các học giả được khuyến khích sử dụng phân tích một cách chiến lược. Ở đây có hai khuyến nghị được đưa ra. Đầu tiên, phân tích đồng từ có thể được sử dụng như một phần bổ sung để làm phong phú thêm sự hiểu biết về các cụm chủ đề bắt nguồn từ phân tích đồng trích dẫn hoặc ghép nối thư mục vì các chủ đề được hình thành thông qua những điểm chung trong các ấn phẩm có xu hướng tương đối chung, và do đó, việc sử dụng phân tích từ đồng nghĩa có thể giúp các học giả xây dựng nội dung của từng cụm chủ đề. Thứ hai, phân tích đồng từ có thể được sử dụng để dự báo nghiên cứu trong tương lai trong lĩnh vực này, điều này có thể xảy ra khi các “từ” đáng chú ý trong hàm ý của bài báo và hướng nghiên cứu trong tương lai được sử dụng trong phân tích. Theo nghĩa đó, phân tích đồng từ phù hợp với các học giả muốn làm phong phú thêm cách diễn giải về phân tích đồng trích dẫn (quá khứ) hoặc ghép nối thư mục (hiện tại) và dự đoán quỹ đạo sắp tới. Do đó, phân tích từ đồng nghĩa có thể cung cấp bản xem trước về tương lai của lĩnh vực nghiên cứu.

9. Phân tích đồng tác giả (co-authorship analysis)
    - Mục đích: Để kiểm tra các tương tác hoặc mối quan hệ xã hội giữa các tác giả và các đơn vị của họ và các tác động tương đương đối với sự phát triển của lĩnh vực nghiên cứu.
    - Ví dụ mẫu: [co-authorship analysis](https://publications.aston.ac.uk/id/eprint/43903/1/Ariel_Social_network_analysis_IoT_Elsevier_ver2A_accepted.pdf)

Phân tích đồng tác giả xem xét sự tương tác giữa các học giả trong một lĩnh vực nghiên cứu. Vì đồng tác giả là một cách hợp tác trí tuệ chính thức giữa các học giả, do đó, điều quan trọng là phải hiểu cách các học giả tương tác với nhau (bao gồm các thuộc tính liên quan của tác giả như các tổ chức liên kết và Quốc gia). Với sự phức tạp ngày càng tăng về phương pháp và lý thuyết trong nghiên cứu, sự hợp tác giữa các học giả đã trở nên phổ biến. Trên thực tế, sự hợp tác giữa các học giả có thể dẫn đến những cải tiến trong nghiên cứu—ví dụ, sự đóng góp từ các học giả khác nhau có thể góp phần mang lại sự hiểu biết rõ ràng hơn và phong phú hơn. Ở đây, các học giả hợp tác với nhau tạo thành một mạng lưới được gọi là “những bức ảnh ghép vô hình”, nghiên cứu của họ có thể giúp phát triển các cam kết trong lĩnh vực nghiên cứu. Ví dụ, phân tích có thể làm sáng tỏ nghiên cứu theo nhóm của các học giả từ một khu vực cụ thể và những hiểu biết sâu sắc đó có thể được sử dụng để biện minh và khơi dậy nghiên cứu mới của các học giả ở những khu vực ít được đại diện. Phân tích này cũng cho phép lập bản đồ hợp tác trong các khoảng thời gian khác nhau, từ đó cho phép các học giả xem xét quỹ đạo phát triển trí tuệ dựa trên các mạng cộng tác, đồng thời trang bị cho các học giả tương lai những thông tin có giá trị để tiếp cận và cộng tác với các học giả có uy tín và có xu hướng trong lĩnh vực nghiên cứu.

## Công cụ phân tích
Chúng ta có hàng loạt các công cụ như: [VOSviewer](https://www.vosviewer.com), bibliometrix package in R, Bibexcel, Pajek, Gephi, SciMat, Sci2, and UCINET
## Các câu hỏi nghiên cứu
1. What Fields of Knowledge do Evaluation Theorists Draw Upon in Their Publications? [Phân tích](https://escholarship.org/content/qt2c5156kx/qt2c5156kx.pdf)
2. What Fields Draw Upon the Published Works of Evaluation Theorists in Their Work? [Phân tích](https://escholarship.org/content/qt2c5156kx/qt2c5156kx.pdf)
3. What are the current publication trends in financial literacy in terms of time, journals, disciplines, authors, affiliated countries and institutions, type of study and economy? [Phân tích](https://www.thestraughtergroup.org/wp-content/uploads/2022/09/A-Systemic-Review-of-Financial-Literacy.pdf)
4. Which are the influential studies and themes of research in this domain? [Phân tích](https://www.thestraughtergroup.org/wp-content/uploads/2022/09/A-Systemic-Review-of-Financial-Literacy.pdf)
5. What is the intellectual structure of financial literacy research, how has it evolved over the years and what are the recent
research trends in this domain? [Phân tích](https://www.thestraughtergroup.org/wp-content/uploads/2022/09/A-Systemic-Review-of-Financial-Literacy.pdf)
6. What are the gaps and areas for future research? [Phân tích](https://www.thestraughtergroup.org/wp-content/uploads/2022/09/A-Systemic-Review-of-Financial-Literacy.pdf)
7. How has the business and management literature addressing entrepreneurial universities evolved so far? [Phân tích](https://www.sciencedirect.com/science/article/pii/S0040162520313482)
8. What structures characterise the business and management literature about entrepreneurial universities? [Phân tích](https://www.sciencedirect.com/science/article/pii/S0040162520313482)
9. What are the possible future trends for research on entrepreneurial universities within the business and management research fields? [Phân tích](https://www.sciencedirect.com/science/article/pii/S0040162520313482)
10. What are the characteristics of the literature produced during the period 1992- 2012 in terms of type, influence, and impact? [Phân tích](https://napier-repository.worktribe.com/preview/2299323/The%20First%20Two%20Decades%20of%20Smart-City%20Research.pdf)
11. How large was the scientific community researching smart cities? [Phân tích](https://napier-repository.worktribe.com/preview/2299323/The%20First%20Two%20Decades%20of%20Smart-City%20Research.pdf)
12. What are the influence and productivity levels of researchers falling within this community and the organizations to which they belong? [Phân tích](https://napier-repository.worktribe.com/preview/2299323/The%20First%20Two%20Decades%20of%20Smart-City%20Research.pdf)
13. What is the interpretation of the smart city concept that emerges from their research? [Phân tích](https://napier-repository.worktribe.com/preview/2299323/The%20First%20Two%20Decades%20of%20Smart-City%20Research.pdf)
14. What factors have influenced the development of the intellectual structure resulting from the first two decades of smart city research? [Phân tích](https://napier-repository.worktribe.com/preview/2299323/The%20First%20Two%20Decades%20of%20Smart-City%20Research.pdf)
15. What are the most-cited articles in the neuromarketing domain between 2004 and 2019? [Phân tích](https://www.tandfonline.com/doi/pdf/10.1080/23311975.2021.1978620)
16. What are the most productive countries and authors in the neuromarketing domain between 2004 and 2019? [Phân tích](https://www.tandfonline.com/doi/pdf/10.1080/23311975.2021.1978620)
17. What are the studies that employed neuromarketing tools in the last five years? [Phân tích](https://www.tandfonline.com/doi/pdf/10.1080/23311975.2021.1978620)
18. What are the general research trends of AI applications in supply chains? [Phân tích](https://www.researchgate.net/profile/Saikouk-Tarik/post/Instructions_on_how_to_conduct_a_systematic_literature_review/attachment/603d54fe6e8959000110b556/AS%3A996653792247811%401614632189911/download/Artificialintelligenceapplicationsinsupplychain.pdf)
19. What are the supply chain outcomes that AI achieves? [Phân tích](https://www.researchgate.net/profile/Saikouk-Tarik/post/Instructions_on_how_to_conduct_a_systematic_literature_review/attachment/603d54fe6e8959000110b556/AS%3A996653792247811%401614632189911/download/Artificialintelligenceapplicationsinsupplychain.pdf)
20. What level of AI drives such outcomes? [Phân tích](https://www.researchgate.net/profile/Saikouk-Tarik/post/Instructions_on_how_to_conduct_a_systematic_literature_review/attachment/603d54fe6e8959000110b556/AS%3A996653792247811%401614632189911/download/Artificialintelligenceapplicationsinsupplychain.pdf)
21. what are the key journals, influential institutions, impactful and trending articles in GSCM research? [Phân tích](https://fardapaper.ir/mohavaha/uploads/2019/01/Fardapaper-A-review-of-green-supply-chain-management-From-bibliometric-analysis-to-a-conceptual-framework-and-future-research-directions.pdf)
22.  How have the key GSCM studies evolved over time building on each other, and what are the underlying research streams? [Phân tích](https://fardapaper.ir/mohavaha/uploads/2019/01/Fardapaper-A-review-of-green-supply-chain-management-From-bibliometric-analysis-to-a-conceptual-framework-and-future-research-directions.pdf)
23.  Based on the key papers - how can GSCM drivers, practices and performance measures be integrated and aligned in one comprehensive framework, and what learnings be derived? [Phân tích](https://fardapaper.ir/mohavaha/uploads/2019/01/Fardapaper-A-review-of-green-supply-chain-management-From-bibliometric-analysis-to-a-conceptual-framework-and-future-research-directions.pdf)
24.   What are the total number of publications in Journal of Knowledge Management (JKM)? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
25.   What are the core JKM articles? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
26.   Who are the main researchers, universities and countries in JKM? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
27.   What are the core journals used in JKM? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
28.   What is the affiliations of researchers? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
29.   What are the topics main in articles of JKM? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
30.   What are the structural networks among the actors who publish in JKM? [Phân tích](https://repositorio.uchile.cl/bitstream/handle/2250/169592/item_85048006580.pdf?sequence=1)
31.   What is the empirical evidence in relation to what energy efficiency technological measures are being implemented in residential buildings in Europe? [Phân tích](https://www.sciencedirect.com/science/article/pii/S0378778819302129)
32.   What is the empirical evidence in relation to decisions behind the diffusion of energy efficiency technologies in residential buildings in Europe? [Phân tích](https://www.sciencedirect.com/science/article/pii/S0378778819302129)
33.   Research question III: What is the empirical evidence in relation to positive side-effects of technological measures for energy efficiency in residential buildings in Europe? [Phân tích](https://www.sciencedirect.com/science/article/pii/S0378778819302129)
