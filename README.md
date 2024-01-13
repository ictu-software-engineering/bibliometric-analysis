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


