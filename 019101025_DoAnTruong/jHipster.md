# Chương 4: jHipster

## 1. Khái niệm jHipster

JHipster( viết tắt của Java Hipster ) là một phương pháp đơn giản để tạo ra một project xung quanh những công nghệ được ưa thích nhất với Spring technology, Angular/React và các microservices Spring.

- Server side xây dựng backend với công nghệ Spring Boot + Spring security.

![image](https://user-images.githubusercontent.com/107389856/174565126-e0d02950-83e3-4da5-af70-2f5c01b75c6d.png)

- Client side với những Framework mạnh mẽ.

![image](https://user-images.githubusercontent.com/107389856/174565258-ec967162-1958-4309-a6f0-73d80dd771d2.png)

- Deployment dự án dễ dàng.

![image](https://user-images.githubusercontent.com/107389856/174565379-b7a25904-d79a-4f53-a832-bc86e0853f7b.png)

## 2. Cách khởi tạo Monolithic và Microservices

#### B1: Cài đặt java, node.js, Git

Windows -> Run -> cmd

Kiểm tra java:

- java --version

Kiểm tra node js:

- node --version

![image](https://user-images.githubusercontent.com/107389856/174553288-207f80c8-53bd-47d2-b4f3-c295b09a31d3.png)

#### B2: Cài đặt Jhipster

Lệnh cài đặt sau khi cài java, node.js, git:

- npm install -g generator-jhipster

![image](https://user-images.githubusercontent.com/107389856/174553818-c8ba5351-ed98-4b32-b2b4-e1fd358a11cf.png)

Lệnh kiểm tra cài đặt npm:

- npm -version

![image](https://user-images.githubusercontent.com/107389856/174556415-dca1d2ae-9acc-48c7-b127-0b38aaedc58f.png)

#### B3: Khởi tạo kiến trúc

Cách tạo Monolithic

![image](https://user-images.githubusercontent.com/107389856/174552971-fc0ff004-080d-435a-adc1-c899e157a55f.png)

Cách tạo Microservices

![image](https://user-images.githubusercontent.com/107389856/174554904-23cf10ae-2c80-42d0-acd4-000808fa0e65.png)

## 3. Những câu hỏi cơ bản để khởi tạo project trong jhipster

![image](https://user-images.githubusercontent.com/107389856/174557813-7ffc1f0f-6605-403e-be69-b152a75a51bb.png)

- Lựa chọn kiến trúc
- Tên project
- Chọn port
- tên package
- Chọn máy chủ khám phá dịch vụ
- Chọn xác thực
- Chọn database liên kết
- Triển khai database
- Chọn bộ nhớ đệm
- Có sử dụng bộ nhớ thứ 2
- Chọn thư viện maven hoặc gradle
- Chọn công nghệ
- Bật công cụ hỗ trợ
- Chọn ngôn ngữ app
- Chọn ngôn ngữ tải về
- Khung thử nghiệm
- Sử dụng Jhipster Marketplace
- Chọn module

## 4. Tác dụng của việc lựa chọn

Các lựa chọn trên giúp người dùng lựa chọn và sử dụng các công nghệ hiện đại theo ý người dùng để phát triển.

Tạo ra một project nhanh chóng dễ sử dụng.

## 5. Tác dụng của công nghệ jHipster

- Một công cụ rất hữu ích giúp các người dùng có thể tạo ra 1 project java web một cách nhanh chóng và đầy đủ các chức năng cần thiết.
- Phía Backend người dùng thể dùng nhiều công nghệ như Spring boot, Spring Sercurity, Maven, Grandle,..
- Phía Frontend người dùng có thể dùng các framework như React, Angular, VueJs, ...
- Người dùng cũng có thể sử dụng nhiều loại cơ sở dữ liệu khác nhau cả Sql và NoSql như MySql, Cassandra, MongoDb,...
- Sau khi generate code người dùng còn có thể tùy chọn việc deloy code của người dùng lên server, Jhipster hỗ trợ nhiều cách khác nhau như: Docker, Aws, HeroKu, Google Cloud Flatform,...

