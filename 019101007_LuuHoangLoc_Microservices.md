# BÀI BÁO CÁO

# PHẦN2:GIỚI Thiệu Về Microservices
## 1.1) Microservices là gi?
- Microservices là tên gọi của các dịch vụ nhỏ thuộc dạng tách biệt đại diện cho 1 phần nhỏ tương ứng bên trong các Business domain của lập trình viên. Với kiến thức Monolithic thì bạn sẽ sở hữu một server lớn với khả năng chịu mọi trách nhiệm giải quyết hầu hết các requests. Và việc này sẽ gây ra khá nhiều khó khăn trên các phương tiện đối với tất cả requests
- Chính vì vậy, Microservices được xem như giải pháp có thể cân bằng được tất cả các traffic dựa theo yêu cầu của doanh nghiệp. Và nếu như bạn đang nhận một lượng lớn các thanh toán thì hầu hết bạn sẽ có thể scale up thiết bị thanh toán và giữ cho các dịch vụ nằm ở mức sử dụng 1 lượng nhỏ hơn so với các services
## 1.2) Kiến trúc của Microservices là gì?
### a Kiến trúc
Bên trong kiến trúc của Microservices thì các services sẽ tồn tại độc lập nhau về xử lý, lưu trữ và cả request. Và cấu trúc cụ thể của nó sẽ như hình sau: 

![Mosaic of Pluto in true color](https://d3hi6wehcrq5by.cloudfront.net/itnavi-blog/2021/01/Microservices-l%C3%A0-g%C3%AC-2.jpg)

Ví dụ như sau: nếu như bạn cần xây dựng một hệ thống để bán hàng dựa trên Microservices thì giả giả sử đơn hàng sẽ cần tối thiểu 4 service với database độc lập như sau: 
- Employee service (sử dụng table tc-employee)
- Store service (sử dụng table tc-store)
- Inventory service (sử dụng table tc-warehouse)
- Order service (sử dụng table tc-order)

Và trong số đó, thì table tc-order sẽ chỉ chứa khóa ngoại chính là ID của nhân viên tại cửa hàng và ID của kho theo đúng tinh thần thiết kế chuẩn hóa database. 
### b Tính chất khối Monolithic ảnh hưởng đến cấu trúc Microservices
- Được thiết kế, phát triển và triển khai dựa theo một khối duy nhất. 
- Các ứng dụng monolithic rất phức tạp và nó sẽ gây ra nhiều khó khăn cho quá trình nâng cấp, bảo trì hoặc thêm các tính năng mới. 
- Thường rất khó để có thể áp dụng triển khai dựa theo kiểu agile.
- Bạn cần phải triển khai lại toàn bộ một hệ thống mặc dù chỉ phải cập nhật hoặc nâng cấp một phần duy nhất. 
- Mở rộng được các khối ứng dụng nếu như gặp khó khăn thì sẽ có các yêu cầu về những tài nguyên khác nhau. 
- Một service thường không có độ ổn định nên có thể làm sập cả hệ thống. 
- Khó đổi mới: Bởi vì ứng dụng monolithic cần phải sử dụng chung một công nghệ vì vậy nó rất khó có thể thay đổi hoặc áp dụng thêm các công nghệ mới. 

Các tính chất giới hạn này của kiến trúc Monolithic dẫn đến sự phát triển của kiến trúc Microservices. 

![Mosaic of Pluto in true color](https://d3hi6wehcrq5by.cloudfront.net/itnavi-blog/2021/01/Microservices-l%C3%A0-g%C3%AC-3.jpg)

*Microservice có vai trò quan trọng với một Developer*
## 1.3) Các ưu điểm và nhược điểm nổi bật của Microservices là gì?
### a) Ưu điểm nổi trội của Microservices là gì?
- Microservices cho phép dễ dàng continuous delivery và deployment các ứng dụng lớn và phức tạp hơn. 
- Có thể cải thiện khả năng bảo trì: bởi vì các service tương đối nhỏ nên dễ hiểu và dễ thay đổi hơn. 
- Có khả năng testing dễ dàng: nhờ các services nhỏ.
- Có thể triển khai tốt hơn: các services thường rất dễ cho việc triển khai độc lập. 
- Cho phép các services được phát triển nhanh chóng bởi những team khác nhau. Khi đó, mỗi team đều sẽ được phát triển và thử nghiệm để triển khai cũng như mở rộng được quy mô của dịch vụ của mình một cách độc lập nhất với tất cả các team. 
- Nếu như có lỗi xảy ra trong một service thì chỉ có service đó bị ảnh hưởng và các service khác sẽ thực hiện xử lý các yêu cầu cần thiết. Trong khi đó, thì mỗi một thành phần nếu như hoạt động sai của kiến trúc một khối thì nó sẽ làm ảnh hưởng đến toàn bộ hệ thống. 
- Lập trình viên có thể thay đổi dễ dàng bằng cách sử dụng công nghệ mới khi triển khai các service. Tương tự như khi có thay đổi lớn thì các service đều có thể thực hiện và bạn dễ dàng thay đổi được công nghệ hơn.
### b) Nhược điểm còn tồn tại
- Bởi vì các nhà phát triển thường xuyên phải đối phó với sự phức tạp khi tạo ra một hệ thống phân tán. 
- Cần phải implement việc communication giữa các inter-services.
- Handle partial failure rất phức tạp bởi vì luồng xử lý cần phải đi qua nhiều service khác nhau. 
- Khi thực hiện các requests trải rộng trên nhiều service khó khăn thì điều này cần đòi hỏi sự phối hợp giữa các team. 
- Thường rất khó khăn trong việc đảm bảo toàn vẹn cho CSDL nếu như triển khai theo các cấu trúc cơ sở dữ liệu dạng phân vùng. 
- Việc triển khai và quản lý microservices nếu như làm thủ công theo cách làm với ứng dụng thì sẽ rất phức tạp.
- Lập trình viên cần phải xử lý các sự cố kết nối chậm, lỗi nếu như thông điệp không được gửi hoặc nếu như thông điệp được gửi đến nhiều đích đến vào các thời điểm khác nhau. 

![Mosaic of Pluto in true color](https://d3hi6wehcrq5by.cloudfront.net/itnavi-blog/2021/01/Microservices-l%C3%A0-g%C3%AC-4.jpg)

*Microservice sở hữu nhiều ưu điểm*
## 1.4) Các lợi ích mang lại của Microservices là gì?
Microservices được sử dụng ngày càng phổ biến nhờ mang lại vô số lợi ích như: 
- Source code rất tinh gọn: Bởi vì hệ thống được cấu thành từ các dự án nhỏ, và mỗi dự án đều rất đơn giản cũng như tập trung vào 1 hoặc 1 vài nghiệp vụ chính. Vì vậy, các code base và độ phức tạp của chúng đều không cao. Nhờ vậy, nó sẽ giúp mang lại tính gọn nhẹ, dễ bảo trì cũng như mở rộng hơn. 
- Bảo mật tối ưu cho source code: Khi nhân viên làm việc ở các dự án thì chỉ truy cập được vào một source code của dự án đó. 
- Được tồn tại độc lập: Bởi vì đây là 4 dự án khác nhau và chúng có thể có cách deploy riêng biệt và một service nào đó chết thì các service khác vẫn sẽ hoạt động một cách bình thường. 
- Scale hoàn toàn độc lập: Tùy thuộc vào nhu cầu sử dụng của hệ thống mà bạn có thể scale riêng cho service đó. Có thể như service đơn hàng mà sử dụng thường xuyên nên chạy từ 2 đến 3 server để gia tăng performance. 
## 1.5) Bạn nên sử dụng kiến trúc Microservices khi nào là hợp lý
Với những thách thức đối với nhu cầu sử dụng Microservices thì bạn nên dùng cấu trúc này khi: 
Khi phát triển những phiên bản đầu tiên cho một ứng dụng, khi đó bạn thường không phải gặp những vấn đề mà Microservices cần phải giải quyết. Hơn nữa, việc sử dụng một kiến trúc phân tán hoặc phức tạp sẽ làm chậm đi quá trình phát triển của ứng dụng. 
Đây là một trong những vấn đề lớn đối với các start-up bởi vì họ buộc phải phát triển nhanh mô hình kinh doanh của mình cũng như ứng dụng kèm theo. Chính vì vậy, trừ khi bạn đã có một hệ thống phức tạp để quản lý bằng Monolithic hoặc bạn đã xác định được tương lai của ứng dụng sẽ ra sao; thì có thể dùng Microservices. 
## 1.6) Các vấn đề nên lưu ý khi thiết kế Microservices
Sau khi hiểu rõ Microservices là gì thì ngay sau đây, ITNavi sẽ đưa ra các lưu ý khi thiết kế Microservices như sau: 
### Hiểu sai về Microservices
- Một số dòng code/kích cỡ của một đội lập trình thường là chỉ số tồi.
- Mico là một từ khóa dễ gây hiểu nhầm và bạn nghĩ rằng nên tạo ra services nhỏ hết mức thì đó là cách hiểu hoàn toàn sai. 
- Services trở thành các cục monolithic với nhiều hàm, chức năng khác được hỗ trợ nhau. Chính vì thế, khi phát triển services kiểu SOA rồi dán nhãn Microservices hoàn toàn bị đánh lạc hướng và không mang lại bất kỳ lợi ích nào. 

![Mosaic of Pluto in true color](https://d3hi6wehcrq5by.cloudfront.net/itnavi-blog/2021/01/Microservices-l%C3%A0-g%C3%AC-5.jpg)
### Những điều cần phải tuân thủ
- Một Service có phạm vi và chức năng giới hạn thì việc tập trung vào một nhiệm vụ sẽ giúp cho quá trình phát triển cũng như triển khai dịch vụ trở nên nhanh chóng hơn. 
- Khi thiết kế, bạn nên xác định và giới hạn cho các service dựa theo chức năng nghiệp vụ thực tế. 
- Hãy đảm bảo microservices có thể phát triển cũng như được triển khai độc lập. 
- Mục tiêu thiết kế là đưa ra phạm vi cho một microservices phục cụ cho một nghiệp vụ chứ không đơn giản là làm những dịch vụ nhỏ hơn. Khi đó, kích thước hợp lý của một services đó chính là kích thước đủ để đáp ứng cho các yêu cầu của một chức năng bên trong hệ thống.
- Khác biệt so với services trong SOA thì một microservice không nên có quá nhiều hàm hoặc chức năng hỗ trợ xung quanh cũng như định dạng thông báo gửi hoặc gửi tin đơn giản. 

## 1.7) So sánh giữa kiến trúc Microservice và Monolithic
a. Tổng quan

- *Về kiến trúc Monolithic*

Như tên gọi Monolithic – nguyên khối – đây là ứng dụng mà mọi dịch vụ đều nằm trên một hệ thống và dùng chung 1 database. Người dùng cứ thẳng đuột mà thao tác với giao diện, giao diện gọi đến chức năng, chức năng lại tìm đến dữ liệu trong database. Đó chính là kiến trúc Monolithic – Nguyên khối.
- *Về kiến trúc Microservce*

Do có cái nhìn tổng quan nhờ Monolithic thì ta cũng mườn tượng ra kiến trúc Microservice như nào rồi. Đó là kiểu kiến trúc thay vì các chức năng được đặt cùng nhau trong hệ thống thì nó sẽ được tách riêng lẻ và có thể với mỗi chức năng đó sẽ tương tác đến các database khác nhau.

b. So sánh

#### b.1 Độ phức tạp
Về độ phức tạp ta sẽ phải xem xét về 2 vấn đề:
- Độ phức tạp của quá trình phát triển.
- Độ phức tạp của việc triển khai phần mềm.

Đối với sự phức tạp của việc phát triển, kích thước của codebase có thể nhanh chóng phát triển khi xây dựng phần mềm dựa trên microservice. Nhiều mã nguồn có liên quan, sử dụng các framework, ngôn ngữ khác nhau và các phiên bản thư viện ở từng dịch vụ có thể sẽ 0khác nhau. Đối với khía cạnh điều hành và giám sát, số lượng dịch vụ bị ảnh hưởng có liên quan nhiều. Kiến trúc nguyên khối chỉ giao tiếp trong phạm vi nhất định, đó có nghĩa là mỗi chức năng cụ thể sẽ luôn có một quy trình xử lý của mình. Bên cạnh đó, một chức năng trong kiến trúc microservice có thể ảnh hưởng đến các dịch vụ khác nhau.

Với việc triển khai hệ thống microservices có thể dùng nhiều công cụ khác nhau, lấy ví dụ như Kubernetes là một công cụ phổ biến thì việc triển khai cũng khá phức tạp, mặc dù Kubernetes cho phép các khả năng như tự động mở rộng quy mô, nhưng nó không phải là một hệ thống dễ quản lý. Bên cạnh đó, để triển khai một hệ thống sử dụng kiến trúc nguyên khối, chỉ cần một thao tác sao chép đơn giản là đủ. Để bắt đầu hoặc dừng hệ thống nguyên khối thường chỉ cần một lệnh đơn giản là đủ. Các dữ liệu giữa các dịch vụ cũng làm tăng thêm sự phức tạp khi chạy ở kiến trúc microservice, so với một khối nguyên khối. Ngoài ra việc đồng bộ hóa cũng là 1 thử thách ở kiến trúc microservice. Ví dụ: việc xử lý các requests không tốt có thể gây ra lỗi thanh toán hai lần. Các kiến trúc microservice có thể quản lý điều này bằng cách sử dụng các kỹ thuật như bộ điều phối trung tâm. Tuy nhiên, trong một kiến trúc nguyên khối, các giao dịch rất dễ xử lý hoặc thậm chí minh bạch đối với nhà phát triển.
> Kiến trúc nguyên khối thắng về độ phức tạp
#### b.2 Độ tin cậy
Khi thiết kế hệ thống ta phải giả định rẳng hệ thống sẽ gặp sự cố tại một thời điểm nào đó. Với hệ thống sử dụng kiến trúc Microservcies, một dịch vụ trong hệ thống bị lỗi, người quản lý chỉ cần khoanh vùng và đưa ra giải pháp để xử lý dịch vụ đó khiến cho hệ thống sẽ vẫn hoạt động bình thường với các chức năng đang hoạt động. Kiến trúc Microservices đã cung cấp một số các giải pháp để giải quyết vấn đề này như Chaos Monkey (Netflix).

Bên cạnh đó với kiến trúc nguyên khối việc xảy ra sự cố sẽ gây tê liệt toàn bộ hệ thống dẫn đén thiệt hại khá lớn

VD: Nếu xảy ra sự cố sập máy chủ, hệ thống với các dịch vụ được phân tán khắp nơi sẽ được đảm bảo an toàn hơn.
>Microservices giành chiến thắng về độ tin cậy
#### b.3 Tài nguyên sử dụng
Với một hệ thống nhỏ việc gọi đến một request thì kiến trúc Microservice sẽ sử dụng nhiều tài nguyên hơn (trong trường hợp thuật toán giống nhau). Một số chi phí phát sinh có thể do docker, máy ảo, việc ghi nhật ký, giám sát tiến trình …

Tuy nhiên, microservices cho phép chúng ta sử dụng tài nguyên thông minh hơn rất nhiều. Vì người quản lý có thể phân bổ tài nguyên khi cần thiết nên mức sử dụng tài nguyên thực tế có thể thấp hơn nhiều.

Do việc so sánh 2 kiến trúc thường sẽ thực hiện trên các hệ thống có quy mô lớn nên đây có thể coi là điểm tốt hơn của microservices so với monolithic.
>Microservices giành chiến thắng về tài nguyên sử dụng với hệ thống lớn.

 #### b.4 Khả năng mở rộng
 Nhờ tính linh hoạt khi kết hợp các dịch vụ trong hệ thống nên việc mở rộng đối với kiến trúc Microservices sẽ dễ dàng hơn. Với kiến trúc Monolithic việc thêm các tính năng sẽ càng làm cho codebase của dự án lớn lên, các công nghệ có thể xung đột khi thêm một chức năng mới. Ngoài ra chi phí cũng là một điểm cần lưu ý do tính linh hoạt khi tính phí theo từng khoảng thời của các dịch vụ riêng lẻ trong hệ thống sử dụng kiến trúc

Microservices, điều này sẽ giúp tiết kiệm hơn so với việc chạy liên tục của hệ thống sử dụng kiến trúc nguyên khối.

Để mở rộng quy mô một cách chính xác và sử dụng tài nguyên tốt hơn thì kiến trúc Microservices sẽ mang lại nhiều lợi ích hơn
>Microservices giành chiến thắng về khả năng mở rộng.
#### b.5 Hiệu suất truyền tải
Trong các khối lượng công việc không thể chạy đồng thời trên toàn mạng, kiến trúc nguyên khối có thể mang lại hiệu suất tốt hơn. Dữ liệu cần được gửi giữa các dịch vụ và cũng như tất cả cơ sở hạ tầng gây ra một chi phí nhất định. Nếu khối lượng công việc không thể được chia tỷ lệ cho nhiều trường hợp, một hệ thống sử dụng kiến trúc nguyên khối có thể mang lại hiệu suất truyền tải cao hơn.

Với khối lượng công việc được chạy trong cùng local và không có chi phí do container, giám sát container hoặc dịch vụ.
>Kiến trúc nguyên khối giành chiến thắng về hiệu suất truyền tải
#### b.6 Tổng kết
|Kiến Trúc Microservices |Kiến Trúc Nguyên Khối|
|------------------------|---------------------|
|Dễ dàng phát triển mở rộng|It phức tạp hơn|
|Tài nguyên sử dụng sẽ ít hơn|Hiệu suất truyền tải dữ liệu tốt hơn|
|Đảm bảo an toàn khi gặp sự cố||
>Với mỗi từng kiến trúc sẽ có ưu nhược điểm riêng nên việc lựa chọn kiến trúc sẽ tùy thuộc vào dự án mà bạn sẽ triển khai.