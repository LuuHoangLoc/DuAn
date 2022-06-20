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

![image](https://user-images.githubusercontent.com/107382675/174574173-f987c35a-f771-43de-9c96-3861579d2559.png)

# 5)làm sao để khởi gạo monolithic :
![image](https://user-images.githubusercontent.com/107382675/174575173-d6e01b56-5220-4d47-a1f3-21c90a25979a.png)
