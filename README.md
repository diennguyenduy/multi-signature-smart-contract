# multi-signature-smart-contract

### 1, giới thiệu

  Multisig là viết tắt của multi-signature (đa chữ ký), là một loại chữ ký điện tử giúp cho hai hoặc nhiều người dùng ký vào tài liệu như là một nhóm. Do đó, một đa chữ ký được tạo ra bằng sự kết hợp của nhiều chữ ký. Công nghệ đa chữ ký đang được dùng trong thế giới tiền điện tử, nhưng nguyên lý của nó đã có mặt từ lâu trước khi tạo ra Bitcoin.

  Trong ngữ cảnh của tiền điện tử, công nghệ lần đầu tiên được áp dụng cho các địa chỉ tiền điện tử trong năm 2012, cuối cùng dẫn đến việc tạo ra các ví đa chữ ký một năm sau đó. Địa chỉ đa chữ ký có thể được sử dụng trong các ngữ cảnh khác nhau, nhưng hầu hết các trường hợp sử dụng đều liên quan đến các vấn đề bảo mật. Trong bài này, chúng ta sẽ thảo luận về việc sử dụng chúng trong các ví đa chữ ký.


### 2, Ví làm việc như thế nào?

Để đơn giản, chúng ta có thể hình dung nó như một hộp tiền gửi an toàn có hai khóa và hai chìa khóa. Một chìa khóa được giữ bởi Alice và một chìa khóa khác được giữ bởi Bob. Cách duy nhất có thể mở hộp là phải có cả hai chìa khóa cùng một lúc, vì vậy, một người không thể mở hộp mà không có sự đồng ý của người khác.

Về cơ bản, các quỹ được lưu trữ trên một địa chỉ đa chữ ký chỉ có thể được truy cập bằng cách sử dụng 2 hoặc nhiều chữ ký. Vì vậy, việc sử dụng một ví đa chữ ký cho phép người dùng tạo thêm một lớp bảo mật cho quỹ của mình. Nhưng trước khi đi xa hơn, điều quan trọng là phải hiểu những nét cơ bản của một địa chỉ Bitcoin chuẩn, dựa trên đơn chìa khóa thay vì đa chìa khóa (địa chỉ một chìa khóa).


### 3, Đơn chìa khóa và Đa chữ ký

Thông thường, Bitcoin được lưu trữ trong một địa chỉ tiêu chuẩn có một chìa khóa, có nghĩa là bất kỳ ai giữ chìa khóa cá nhân tương ứng đều có thể truy cập vào quỹ. Điều này có nghĩa là chỉ cần một chìa khóa để ký các giao dịch, và bất kỳ ai có chìa khóa cá nhân đều có thể chuyển coin theo ý muốn mà không cần có sự cho phép của bất kỳ ai khác.

Việc quản lý một địa chỉ đơn chìa khóa là nhanh hơn và dễ dàng hơn so với một địa chỉ đa chìa khóa, nhưng có một số vấn đề, đặc biệt là liên quan đến bảo mật. Với việc có một chìa khóa duy nhất, quỹ được bảo vệ bởi một điểm chịu lỗi duy nhất, và đó là lý do tại sao bọn tội phạm mạng liên tục phát triển các kỹ thuật lừa đảo mới để ăn cắp tiền của người dùng tiền điện tử.

Hơn nữa, các địa chỉ đơn chìa khóa không phải là lựa chọn tốt nhất cho các doanh nghiệp có liên quan đến tiền điện tử. Hãy tưởng tượng về trường hợp quỹ của một công ty lớn đang được lưu trữ tại một địa chỉ tiêu chuẩn có một chìa khóa cá nhân tương ứng. Điều này có nghĩa là chìa khóa cá nhân sẽ được giao phó cho một người hoặc cho nhiều người cùng một lúc - và rõ ràng đó không phải là cách an toàn nhất.

Ví đa chữ ký cung cấp một giải pháp tiềm năng cho cả hai vấn đề này. Không giống như địa chỉ đơn chìa khóa, quỹ được lưu trữ trên một địa chỉ đa chữ ký chỉ có thể được chuyển đi nếu có đa chữ ký (được tạo ra bằng cách sử dụng các chìa khóa cá nhân khác nhau).

Theo cách cấu hình cho một địa chỉ đa chữ ký, việc mở khóa có thể yêu cầu sự kết hợp của các chìa khóa khác nhau: 2-of-3 là phổ biến nhất, trong đó chỉ có 2 chữ ký là đủ để truy cập vào quỹ của một địa chỉ 3 chữ ký. Tuy nhiên, có nhiều biến thể khác, chẳng hạn như 2-of-2, 3-of-3, 3-of-4, v.v.

### 4, Tăng bảo mật

Bằng cách sử dụng một ví đa chữ ký, người dùng có thể ngăn chặn các vấn đề gây ra do bị mất hoặc bị trộm chìa khóa cá nhân. Vì vậy, ngay cả khi một trong số các chìa khóa gặp vấn đề, quỹ vẫn sẽ an toàn.

Hãy tưởng tượng rằng Alice tạo một địa chỉ đa chữ ký 2-of-3 và sau đó lưu trữ mỗi chìa khóa cá nhân vào một nơi hoặc thiết bị khác nhau (ví dụ: điện thoại di động, máy laptop và máy tính bảng). Ngay cả khi điện thoại di động của cô bị đánh cắp, kẻ trộm sẽ không thể vào được quỹ của cô chỉ với 1 trong 3 chìa khóa. Tương tự, các cuộc tấn công lừa đảo và các phần mềm độc hại ít có khả năng thành công hơn vì hacker có nhiều khả năng sẽ chỉ truy cập vào được một thiết bị và một chìa khóa duy nhất.

Về phía bên kia, nếu Alice mất một trong những chìa khóa riêng tư của mình, cô vẫn có thể truy cập vào quỹ của mình bằng cách sử dụng 2 chìa khóa khác.


### 5, Xác thực hai yếu tố

Bằng cách tạo ra một ví đa chữ ký cần hai chìa khóa, Alice có thể tạo ra một cơ chế xác thực hai yếu tố để truy cập vào quỹ của mình. Ví dụ, cô có thể có một chìa khóa riêng được lưu trữ trong máy laptop và một chìa khóa khác trong thiết bị di động (hoặc thậm chí trên một mảnh giấy). Điều này sẽ đảm bảo rằng chỉ những người truy cập được vào cả hai chìa khóa mới có thể thực hiện giao dịch.

Tuy nhiên, hãy nhớ rằng việc sử dụng công nghệ đa chữ ký với cơ chế xác thực hai yếu tố có thể nguy hiểm - đặc biệt nếu nó được đặt làm địa chỉ đa chữ ký 2-of-2. Nếu một trong các chìa khóa bị mất, bạn sẽ không thể truy cập vào quỹ của mình. Do đó, việc sử dụng thiết lập 2-of-3 hoặc dịch vụ 2FA bên thứ ba để dùng mã dự phòng sẽ an toàn hơn. Khi nói đến tài khoản giao dịch, sử dụng Google Authenticator được khuyến khích.


### 6, Giao dịch ký quỹ

Việc tạo ra một ví đa chữ ký 2-of-3 có thể cho phép giao dịch ký quỹ giữa hai bên (Alice và Bob) gồm sự xuất hiện của một bên thứ ba (Charlie) với tư cách là trọng tài được ủy thác bởi hai bên trong trường hợp có sự cố.

Theo kịch bản, Alice trước tiên sẽ ký quỹ, và quỹ sẽ sẽ bị khóa lại (cả người dùng cũng không thể truy cập vào). Sau đó, nếu Bob cung cấp hàng hóa hoặc dịch vụ theo thỏa thuận, cả hai có thể sử dụng các chìa khóa của mình để ký và hoàn tất giao dịch.

Charlie, trọng tài, sẽ chỉ tham gia nếu có tranh chấp. Khi có tranh chấp, anh ta có thể sử dụng chìa khóa của mình để tạo ra một chữ ký mà sẽ được giao cho Alice hoặc Bob tùy theo phán quyết của Charlie.

### 7, Nhược điểm

Mặc dù ví đa chữ ký là một giải pháp tốt cho một loạt các vấn đề, điều quan trọng là hãy ghi nhớ rằng nó vẫn có một số rủi ro và hạn chế. Việc thiết lập địa chỉ đa chữ ký của riêng bạn đòi hỏi phải có một số kiến thức kỹ thuật, đặc biệt nếu bạn không muốn dựa vào các nhà cung cấp bên thứ ba.

Ngoài ra, do blockchain và địa chỉ đa chữ ký là tương đối mới nên có thể sẽ khó tiến hành quyền truy đòi theo pháp luật nếu phát sinh vấn đề. Người giám hộ hợp pháp là không có đối với các quỹ đặt trong một ví được chia sẻ với nhiều người giữ chìa khóa.


## Kết luận

Mặc dù có một vài nhược điểm, ví đa chữ ký có nhiều ứng dụng thú vị, khiến cho Bitcoin, Ethereum và các đồng tiền điện tử khác thậm chí còn hữu ích và hấp dẫn hơn - đặc biệt là đối với các doanh nghiệp. Bằng cách yêu cầu nhiều hơn một chữ ký để chuyển tiền, các ví đa chữ ký cung cấp bảo mật nâng cao và cho phép các giao dịch ký quỹ không cần ủy thác. Do đó, công nghệ này có khả năng sẽ ngày càng được áp dụng nhiều hơn trong tương lai.
