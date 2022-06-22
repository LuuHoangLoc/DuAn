## 4.0 JHipter
# 4.1 Khái niệm về JHipster.

JHipster( viết tắt của Java Hipster) là phần mềm để chúng ta tạo ra một project xung quanh những công nghệ được ưa thích nhất với Spring technologies và Angular/React một cách đơn giản.Khi chúng ta bắt đầu dự án chúng ta sẽ quan tâm đến 3 khía cạnh:Server side stack trông như thế nào.Client side stack  trông như thế nào. Cách để để chúng ta có thể deploy project.

**Server side**

-  Server side xây dựng backend với nhiều công nghệ:
![Mosaic of Pluto in true color](https://images.viblo.asia/2e292e0f-0ab8-4eac-987d-fa352d43df20.png)

**Client side**

-  Với những framework frontend mạnh mẽ:

![Mosaic of Pluto in true color](https://images.viblo.asia/39141588-d471-4faf-aaa5-c50fbc9a37ba.png)

**Deployment**

-  Deply dự án dễ dàng:

![Mosaic of Pluto in true color](https://images.viblo.asia/70452aa0-1ec8-41ad-b205-a879bd84e5bb.png)

# 4.2 Cách khởi tạo Monolithic và Microservices.

**B1: Cài đặt java, node.js, Git**

Windows -> Run -> cmd

Kiểm tra java:

-  java --version

Kiểm tra node js:

-  node --version

![Screenshot 2022-06-22 084051](https://user-images.githubusercontent.com/107389916/174925815-f5327182-086c-4b1c-9e0f-a3d153997e13.png)

**B2: Cài đặt Jhipster**

Lệnh cài đặt sau khi cài java, node.js, git:

-  npm install -g generator-jhipster

![image](https://user-images.githubusercontent.com/107389916/174926325-096b99a9-5b2a-4cc5-a925-519eda89280c.png)

**Lệnh kiểm tra cài đặt npm:**

-  npm -version*

![Screenshot 2022-06-22 085516](https://user-images.githubusercontent.com/107389916/174926668-1fc6b63d-3aa2-4ab2-9447-c9cda1aae52b.png)

**B3: Khởi tạo kiến trúc**

-  Cách tạo Monolithic

![image](https://user-images.githubusercontent.com/107389916/174926900-8f83b1f2-b4ce-4ddd-a0b0-3d1579df672e.png)

**Cách tạo Microservices**

![image](https://user-images.githubusercontent.com/107389916/174927031-d923705b-b8a7-460c-9ae7-ef31d666f487.png)

# 4.3 Những câu hỏi cơ bản để khởi tạo project trong jhipster

![image](https://user-images.githubusercontent.com/107389916/174927582-47c09b8c-22ce-4895-bd95-df232c7a30cf.png)

-	Lựa chọn kiến trúc
-	Tên project
-	Chọn port
-	tên package
-	Chọn máy chủ khám phá dịch vụ
-	Chọn xác thực
-	Chọn database liên kết
-	Triển khai database
-	Chọn bộ nhớ đệm
-	Có sử dụng bộ nhớ thứ 2
-	Chọn thư viện maven hoặc gradle
-	Chọn công nghệ
-	Bật công cụ hỗ trợ
-	Chọn ngôn ngữ app
-	Chọn ngôn ngữ tải về
-	Khung thử nghiệm
-	Sử dụng Jhipster Marketplace
-	Chọn module

# 4.4 Tác dụng của việc lựa chọn

Các lựa chọn trên giúp người dùng lựa chọn và sử dụng các công nghệ phù hợp với dự án của mình để phát triển.

Tạo ra một project nhanh chóng dễ sử dụng.

# 4.5 Tác dụng của công nghệ jHipster

-  Người dùng có thể tạo ra 1 project java web một cách nhanh chóng và đầy đủ các chức năng cần thiết.

-  Phía Backend người dùng thể dùng nhiều công nghệ như Spring boot, Spring Sercurity, Maven, Grandle,..

-  Phía Frontend người dùng có thể dùng các framework như React, Angular, VueJs, ...

-  Người dùng cũng có thể sử dụng nhiều loại cơ sở dữ liệu khác nhau cả Sql và NoSql như MySql, Cassandra, MongoDb,...

-  Sau khi generate code người dùng còn có thể tùy chọn việc deloy code của người dùng lên server, Jhipster hỗ trợ nhiều cách khác nhau như: Docker, Aws, HeroKu, Google Cloud Flatform,...
# 4.6 Ý nghĩa:

- Giúp hoàn thiện dự án một cách nhanh chóng.

- Tạo project dễ dàng.





