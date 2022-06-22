# 1)JHipster là gì:
JHipster is a development platform to generate, develop and deploy Spring Boot + Angular/React Web applications and Spring microservices.

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_1_8671_700.jpg)

Nói một cách đơn giản, JHipster( viết tắt của Java Hipster) là phương pháp đơn giản để chúng ta tạo ra một project xung quanh những công nghệ được ưa thích nhất với Spring technologies và Angular/React.Khi chúng ta bắt đầu dự án chúng ta sẽ quan tâm đến 3 khía cạnh:Server side stack sẽ trông như thế nào?Client side stack sẽ trông như thế nào?Làm sao để chúng ta khả năng deploy project của chúng ta?
## 1.1)Server side:
Khi chúng ta bắt đầu build phần backend có những câu hỏi mà chúng ta quan tâm đó là:

Ngôn ngữ chúng ta lựa chọn là gì?Tầng dữ liệu sẽ như thế nào?Hệ thống sẽ bảo mật ra sao?Khả năng bảo trì và mở rộng hệ thống?Cách cung cấp API document?Kiểm thử ứng dụng thế nào?Câu trả lời sẽ có khi bạn nhìn vào danh sách công nghệ mà JHipster cung cấp :

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_2_8671_700.jpg)

## 1.2)Client side:

Với những framework frontend mạnh mẽ
![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_3_8671_700.jpg)

## 1.3)Deployment:
Deply dự án đơn giản 

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_3_8671_700.jpg)
 
# 2)Tại sao lựa chọn JHipster:

 Chúng ta sẽ đơn giản có được một project đủ mạnh mẽ đầy đủ những thứ cơ bản để bắt đầu với thời gian nhanh nhất.Và nếu bạn đang tập tành với Spring để trở thành 1 Java Web developer thì bạn nên quan tâm đến công nghệ này.

# 3)Cách tạo project đầu tiên với JHipster:

Những gì bạn cần có để bắt đầu tạo một project đầu tiên với JHipster:

Cài đặt Yeoman: npm install -g yoCài đặt JHipster: npm install -g generator-jhipster

Note:

Bạn cũng khả năng dùng Yarn/Homebrew/Chocolatey/Docker để cài đặt JHipster.

Với bước cài đặt JHipster ở trên nếu bạn muốn dùng phía Client với Angular JS thì bản JHipster của bạn phải là npm install -g
### a)Tạo project:
Thực hiện trên Terminal / cmd :Tạo 1 thư mục trống là nơi sẽ chứa project. mkdir myapplicationChuyển đến thư mục vừa tạo cd myapplication/Generate ứng dụng : jhipsterLựa chọn những thứ phù hợp với project của bạnTạo 1 thư mục trống là nơi sẽ chứa project. mkdir myapplicationChuyển đến thư mục vừa tạo cd myapplication / Generate ứng dụng : jhipsterLựa chọn những thứ tương thích với project của bạn

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_5_8671_700.jpg)
*Bây giờ bạn đã có 1 project với:*

Backend: Spring Boot + Spring SecurityDatabase:Mysql (production)H2 with disk-based (development)Frontend: Bootstrap + SASS + Angular 7 (hoặc thấp hơn tùy vào phiên bản JHipster bạn cài đặt ở trên)Sau khi chạy xong bạn sẽ nhận được kết quả như bên dưới. Đó cũng là hướng dẫn để bạn build project của mình trên local.

Xem thêm:

Backend : Database : Mysql ( production ) H2 with disk-based ( development ) Frontend : Bootstrap + SASS + ( hoặc thấp hơn tùy vào phiên bản JHipster bạn thiết lập ở trên ) Sau khi chạy xong bạn sẽ nhận được hiệu quả như bên dưới. Đó cũng là hướng dẫn để bạn build project của mình trên local. Xem thêm : Nghĩa của từ liquor là gì ? và 4 thông tin có ích cần biết về liqueurRun your Spring Boot application :. / mvnw ( mvnw if using Windows Command Prompt )Client application generated successfully. Start your Webpack development server with :npm startNhững quan tâm khi chọn trong phần config project ở trên :Jhipster hỗ trợ bạn setup đa ngôn ngữ trong projectJHipster đã tạo cho bạn project với cả môi trường của development và môi trường thực tế (production)Ở môi trường development: nếu bạn không muốn cài đặt các database trên local.Bạn có thể sử dụng H2 with disk-based hoặc H2 in -memory. Cả 2 cho phép bạn sử dụng database ngay trong giao diện của ứng dụng.H2 in-memory: data sẽ bị mất khi bạn restart server.H2 with disk-based: data sẽ không bị mất khi bạn restart server.Nếu không dùng 2 loại database trên bạn sẽ phải tạo schema trên local và sửa lại config với database trong phần code.Jhipster tương hỗ bạn setup đa ngôn ngữ trong projectJHipster đã tạo cho bạn project với cả thiên nhiên và môi trường của development và thiên nhiên và môi trường trong thực tiễn ( production ) Ở thiên nhiên và môi trường development : nếu bạn không muốn setup những database trên local. Bạn hoàn toàn có thể sử dụng H2 with disk-based hoặc H2 in – memory. Cả 2 được cho phép bạn sử dụng database ngay trong giao diện của ứng dụng. H2 in-memory : data sẽ bị mất khi bạn restart server. H2 with disk-based : data sẽ không bị mất khi bạn restart server. Nếu không dùng 2 loại database trên bạn sẽ phải tạo schema trên local và sửa lại config với database trong phần code .
Ví dụ bạn dùng Mysql.

Xem thêm: Hệ Thống Hvac Là Gì? Cách Phân Biệt Hvac Và Acmv Là Gì

Trong thư mục project :src / main / resources / config / application-dev.yml

datasource: type: com.zaxxer.hikari.HikariDataSource url: jdbc:mysql://localhost:3306/hello?useUnicode=true&characterEncoding=utf8&useSSL=false&useLegacyDatetimeCode=false&serverTimezone=UTC username: root password:Thì hello sẽ là tên schema mà bạn cần để tạo trên local.

JHipster giúp bạn với 1 dòng lệnh có không thiếu CRUD cả phần backend và frontendBạn hãy thử khám phá nó trên doc của JHipster.
# 4) làm sao để khởi tạo micorservices:
## 1.1)Tạo một dịch vụ nhỏ cho nhà máy bia:
### a)Điều kiện tiên quyết:
sợi toàn cầu thêm máy phát điện-jhipster
### b)Tạo cổng API:
Để truy cập các dịch vụ khác nhau của chúng tôi trong một kiến ​​trúc microservice, chúng tôi sẽ cần một Cổng API . Nó là lối vào microservices của bạn. Nó cung cấp định tuyến HTTP ( Netflix Zuul ) và cân bằng tải ( Netflix Ribbon ), chất lượng dịch vụ ( Netflix Hystrix ), bảo mật ( Spring Security ) và tài liệu API () cho tất cả các dịch vụ nhỏ.
Trong cửa sổ dòng lệnh:

1|mkdir couchbase-jhipster-microservices-example

2|cd couchbase-jhipster-microservices-example

3|mkdir gateway

4|cd gateway

5|jhipster

JHipster hỏi về loại ứng dụng bạn muốn tạo và những tính năng bạn muốn đưa vào. Bạn có thể tìm thấy tất cả thông tin chi tiết về các tùy chọn có sẵn trên Trang web JHipster . Sử dụng các câu trả lời sau để tạo một cổng với sự hỗ trợ của Couchbase.

![image](https://user-images.githubusercontent.com/107382675/174922365-96459a10-f06f-456f-b9fe-ccd7d42bdd69.png)
## c)Tạo ứng dụng dịch vụ vi mô của nhà máy bia:
Trong couchbase-jhipster-microservices-example, hãy tạo một thư mục nhà máy bia, sau đó chạy jhipster để tạo một microservice với cơ sở dữ liệu Couchbase với các câu trả lời sau:

![image](https://user-images.githubusercontent.com/107382675/174922668-ec59e66b-f2f3-43a7-8d86-7b95d333511d.png)
## d)Tạo các thực thể nhà máy bia:
Tạo tệp brewery.jh trong thư mục couchbase-jhipster-microservices-example với phần sau (Ngôn ngữ miền JHipster):

![image](https://user-images.githubusercontent.com/107382675/174922833-8039eab6-3e7b-47cb-b9ce-7ec1b90ddd7a.png)

phân trang Bia bằng máy nhắn tin Phân trang Nhà máy bia với cuộn vô hạn

Trong cửa sổ dòng lệnh, hãy chạy các lệnh sau:

![image](https://user-images.githubusercontent.com/107382675/174922912-46f22285-a2b4-4b9d-a78f-e0ffa2d777dc.png)

Khi được yêu cầu ghi đè tệp, hãy luôn trả lời a.

![image](https://user-images.githubusercontent.com/107382675/174923033-b8d3a24b-c379-4a40-b2eb-6675ddc7a355.png)

## e)Chạy kiến ​​trúc Microservice:
Để chạy kiến ​​trúc của chúng tôi, chúng tôi cần bắt đầu những điều sau:

1.Cơ quan đăng ký JHipster
2.Keycloack : một giải pháp quản lý truy cập và nhận dạng mã nguồn mở
4.Máy chủ Couchbase
5.Dịch vụ nhà máy bia
6.Cổng vào

May mắn thay, JHipster có một trình tạo phụ docker -soạn sẽ khởi động tất cả các dịch vụ cần thiết mà không phải đau đầu. Nhưng trước tiên, chúng ta cần xây dựng các ứng dụng của mình. Trong ví dụ couchbase-jhipster-microservices-:

![image](https://user-images.githubusercontent.com/107382675/174923253-3fd4c5a4-88ff-4d9a-b584-7e1ff3d554b0.png)

Bây giờ, chúng ta có thể tạo docker-compos.yml bằng cách sử dụng lệnh và câu trả lời sau:

>**jhipster docker-compose**

![image](https://user-images.githubusercontent.com/107382675/174923472-81d7fca6-ad00-4193-833c-a88472c14757.png)

Để làm cho ứng dụng của chúng tôi hoạt động với một keycloak cục bộ, chúng tôi cần thêm vào tệp máy chủ của bạn (Windows: C: \ Windows \ System32 \ drivers \ etc \ hosts, Mac / Linux: / etc / hosts) dòng sau:

>**127.0.0.1 keycloak**

Trước khi bắt đầu mọi thứ, hãy đảm bảo rằng bạn đã định cấu hình Docker với đủ bộ nhớ và CPU, sau đó chạy:

>**docker-compose up**

Khi mọi thứ hoàn tất bắt đầu, hãy mở trình duyệt tới Gateway ( http: // localhost: 8080 / ), nhấp vào tài khoản, sau đó đăng nhập.

![image](https://user-images.githubusercontent.com/107382675/174923658-7ea04af9-98ec-49c7-bf6a-c664fff64ac9.png)

Bạn sẽ được chuyển hướng đến keycloak , đăng nhập bằng quản trị viên cho cả người dùng và mật khẩu.

![image](https://user-images.githubusercontent.com/107382675/174923751-67af20fb-4f12-4450-b633-ae7635a3d216.png)

Bạn sẽ quay lại cổng nơi bạn có thể xem các giao diện quản trị, thay đổi ngôn ngữ, xem và chỉnh sửa các thực thể của mình ...

![image](https://user-images.githubusercontent.com/107382675/174923840-37361f26-11ce-41be-9df1-fca4f94abf89.png)


![image](https://user-images.githubusercontent.com/107382675/174923909-338dea04-cde5-484e-8507-54a0590ec5ee.png)
## f) JHipster-registry
![image](https://user-images.githubusercontent.com/107382675/174924059-5db416f9-be82-498c-8812-aec6a122e137.png)

Ngoài việc là xương sống của ứng dụng microservice của bạn, vì nó là máy chủ khám phá xử lý định tuyến, cân bằng tải, khả năng mở rộng và máy chủ cấu hình với Máy chủ cấu hình đám mây mùa xuân cung cấp cấu hình thời gian chạy của các ứng dụng của bạn, sổ đăng ký JHipster cũng là một máy chủ quản trị nơi bạn có thể trực quan hóa các phiên bản ứng dụng, tình trạng, chỉ số và nhật ký của mình.

# 5)làm sao để khởi gạo monolithic :
![image](https://user-images.githubusercontent.com/107382675/174575173-d6e01b56-5220-4d47-a1f3-21c90a25979a.png)

# 6) ý Nghĩa :
trong thời đại công nghệ số để nhanh chống ,tiết kiệm thời giang nhưng vẫn đạt hiệu quả , JHipster  là một công cụ hữu ích giup tiết kiệm thời gian vẫn có thể nhanh chống khởi tạo một dự án.