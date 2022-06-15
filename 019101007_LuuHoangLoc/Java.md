# BÀI BÁO CÁO
## PHẦN 3 : SPRING BOOT
### 1.1)Spring Boot là gì ?:
Spring Boot là một Java framework được phát triển bởi Pivital Team dựa trên Java framework mã nguồn mở để tạo ra các microservice, nhằm mục đích xây dựng các ứng dụng Spring độc lập một cách nhanh chóng và có khả năng thực thi ngay.

Sau khi sử dụng Spring Boot để lập trình ứng dụng Spring, bạn có thể chạy ngay ứng dụng của mình mà không cần phải config (cấu hình) quá nhiều.
### 1.2)Những đặc điểm nổi bật của Spring Boot:
- Spring Boot được phát triển tối ưu sao cho việc cấu hình XML trở nên đơn giản nhất trong Spring.
- Spring Boot được phát triển sao cho việc lập trình trở nên nhanh chóng và dễ dàng.
- Gia tăng năng suất trong lập trình.
- Giảm thời gian lập trình xuống tối thiểu.
- Spring Boot được phát triển nhằm giúp người không có nhiều kiến thức lập trình vẫn có thể xây dựng ứng dụng.

TinoHost có thể kể đến 3 tính năng rất quan trọng tạo nên sự “dễ chịu” của Spring Boot như:
- `SpringApplication`: bạn lập trình xong và chỉ muốn chạy thử nghiệm luôn ứng dụng của mình? Vậy bạn chỉ cần gọi run() là được. Vì Spring Boot được thiết kế theo dạng “just run” nhằm giúp lập trình viên chỉ cần cấu hình ít Spring nhất có thể, còn lại Spring Boot sẽ tự động lo liệu.
- `Externalized` Configuration: bạn muốn tạo một ứng dụng có thể chạy trên nhiều môi trường khác nhau? Vậy, Spring Boot sẽ giúp bạn config cấu hình từ bên ngoài và ứng dụng của bạn sẽ có thể thoải mái chạy.
- `Profiles`: Khi bạn có nhiều config khác nhau, bạn có thể sử dụng Profile để phân chia từng loại config cho từng môi trường để dễ dàng quản lý hơn.

Không chỉ dừng lại ở những tính năng đó, với Spring Boot, bạn còn có thể phát triển web Application, Caching, gửi Email, Validation, làm việc với công nghệ SQL,…

![Mosaic of Pluto in true color](https://wiki.tino.org/wp-content/uploads/2021/07/word-image-1542.png)

### 1.3)Vì sao nên học Spring Boot?:
Để xây dựng một ứng dụng Java, bạn sẽ có vô số công nghệ để có thể sử dụng. Theo TinoHost, đây là 5 tính năng và lợi ích vô cùng thuyết phục vì sao bạn nên chọn `Spring Boot`:
- Bạn ngán ngẩm việc phải cấu hình từng chút một cho ứng dụng của mình? `Spring Boot` sẽ tự động cấu hình gần như mọi thứ giúp bạn tập trung vào việc `code`.
- Với một ứng dụng lớn, việc quản lý từng `Microservice` sẽ vô cùng phức tạp. `Spring Boot` sẽ giúp bạn đơn giản hóa việc này.
- `Annotation Based Configuration` là tính năng đắc lực sẽ hỗ trợ bạn tạo lập bean thay vì XML.
- Servlet được nhúng sẵn trong `Spring Boot`, vì thế bạn có thể bật và chạy `Server Tomcat` một cách dễ dàng.
- Spring Boot rất linh hoạt để bạn có thể cấu hình `Java Beans`, XML và cả `Database Transaction` (giao dịch/ trao đổi)
.
![Mosaic of Pluto in true color](https://wiki.tino.org/wp-content/uploads/2021/07/word-image-1543-1024x492.png)
### 1.4)Tại sao spring boot áp dung trong Microservices:
- Microservices được sử dung rất rông rãi trong các project java Web bây giờ, bản chất Microservices đó là chia để trị tức là một khối project java Web lớn chúng ta có thể chia thành các project Java web nhỏ nhờ đó dễ dàng quản lý thời gian,lỗi,member,tài nguyên trong dự án

- Mỗi project Java web nhỏ là một Microservices và thường sử dụng spring boot.
