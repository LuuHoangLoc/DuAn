## JHIPSTER
Là một trình tạo ứng dụng mã nguồn mở và miễn phí được sử dụng để nhanh chóng phát triển các ứng dụng web và Dịch vụ hiện đại bằng cách sử dụng Angular hoặc React và Spring Framework.

 Là một nền tảng phát triển để nhanh chóng tạo, phát triển và triển khai các ứng dụng web & kiến ​​trúc microservice hiện đại.
 ![image](https://user-images.githubusercontent.com/107390677/174553927-39156ef6-e5e2-464d-8f8f-2658fb83fb1c.png)

 - CÁCH KHỞI TẠO MICROSERVICES BẰNG JHIPSTER

 Câu hỏi đầu tiên mà JHipster sẽ hỏi là  loại ứng dụng mà bản thân muốn tạo. Có hai sự lựa chọn :

 -Kiến trúc “nguyên khối” sử dụng một ứng dụng duy nhất, một ứng dụng phù hợp với tất cả, chứa cả mã front-end và back-end Spring Boot.

-Kiến trúc “microservices” phân chia front-end và back-end, để ứng dụng của mình dễ dàng mở rộng quy mô và tồn tại các vấn đề về cơ sở hạ tầng.

Ứng dụng “nguyên khối” dễ sử dụng hơn nhiều, vì vậy nếu bản thân không có bất kỳ yêu cầu cụ thể nào thì đây là tùy chọn của chương trình đề xuất và là tùy chọn mặc định. 

## Tổng quan về kiến trúc Microservices

- Cổng là ứng dụng do `JHipster` tạo (sử dụng loại ứng dụng `microservice gateway`khi bạn tạo) xử lý lưu lượng truy cập Web và phục vụ ứng dụng Angular / React. Có thể có một số cổng khác nhau, nếu bạn muốn làm theo mẫu `Backends cho Frontends` , nhưng điều đó không bắt buộc.

- JHipster `Registry` là một ứng dụng thời gian chạy mà trên đó tất cả các ứng dụng sẽ đăng ký và lấy cấu hình của chúng. Nó cũng cung cấp bảng điều khiển giám sát thời gian chạy.

- `Lãnh sự` là một dịch vụ khám phá dịch vụ, cũng như một kho lưu trữ khóa / giá trị. Nó có thể được sử dụng thay thế cho JHipster Registry.

- `Microservices` là các ứng dụng do JHipster tạo (sử dụng loại ứng dụng `microservice application` khi bạn tạo chúng), xử lý các yêu cầu REST. Chúng không có trạng thái và một số phiên bản của chúng có thể được khởi chạy song song để xử lý các tải nặng.

![image](https://user-images.githubusercontent.com/107390677/174557881-d6fc2207-6570-4849-9430-78b407632052.png)

## Tác dụng của JHIPSTER

Đây là một công cụ rất hữu ích giúp tạo ra 1 project java web một cách nhanh chóng và đầy đủ các chức năng cần thiết. Jhipster hỗ trợ cho rất nhiều công nghệ khác nhau. Phía Backend bạn thể dùng nhiều công nghệ như Spring boot, Spring Sercurity, Maven, Grandle,...

![image](https://user-images.githubusercontent.com/107390677/174562313-39af252a-2ca0-4ec0-a15d-28dbfdf8d533.png)


## Tại sao nên lựa chọn JHIPSTER

Bởi rất đơn giản là vì có được một project đủ mạnh mẽ đầy đủ những thứ cơ bản để bắt đầu với thời gian nhanh nhất. Và nếu  đang tập tành với Spring để trở thành 1 Java Web developer thì tôi nên quan tâm đến công nghệ này.