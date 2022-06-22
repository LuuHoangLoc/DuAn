## 1)JHipster là gì:
JHipster is a development platform to generate, develop and deploy Spring Boot + Angular/React Web applications and Spring microservices.

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_1_8671_700.jpg)

Nói một cách đơn giản, JHipster( viết tắt của Java Hipster) là phương pháp đơn giản để chúng ta tạo ra một project xung quanh những công nghệ được ưa thích nhất với Spring technologies và Angular/React.Khi chúng ta bắt đầu dự án chúng ta sẽ quan tâm đến 3 khía cạnh:Server side stack sẽ trông như thế nào?Client side stack sẽ trông như thế nào?Làm sao để chúng ta khả năng deploy project của chúng ta?
### 1.1)Server side:
Khi chúng ta bắt đầu build phần backend có những câu hỏi mà chúng ta quan tâm đó là:

Ngôn ngữ chúng ta lựa chọn là gì?Tầng dữ liệu sẽ như thế nào?Hệ thống sẽ bảo mật ra sao?Khả năng bảo trì và mở rộng hệ thống?Cách cung cấp API document?Kiểm thử ứng dụng thế nào?Câu trả lời sẽ có khi bạn nhìn vào danh sách công nghệ mà JHipster cung cấp :

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_2_8671_700.jpg)

### 1.2)Client side:

Với những framework frontend mạnh mẽ
![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_3_8671_700.jpg)

### 1.3)Deployment:
Deply dự án đơn giản 

![Mosaic of Pluto in true color](https://truonggiathien.com.vn/wp-content/uploads/2021/10/imager_3_8671_700.jpg)
 
## 2)Cách khởi tạo Monolithic và Microservices
### a) yêu cầu cài đặt:
####  1. Cài đặt Java 11. Chúng tôi khuyên bạn nên sử dụng các bản dựng AdoptOpenJDK , vì chúng là mã nguồn mở và miễn phí.
####  2. Cài đặt Node.js từ trang web Node.js (vui lòng sử dụng phiên bản LTS 64 bit, các phiên bản không phải LTS không được hỗ trợ)
####  3. Cài đặt JHipster:npm install -g generator-jhipster
####  4. (tùy chọn) Nếu bạn muốn sử dụng một mô-đun hoặc một bản thiết kế (ví dụ: từ JHipster Marketplace ), hãy cài đặt Yeoman :npm install -g yo
 ### b) kiểm tra xem đã cài  java, node.js, Git,npm :
 #### B1 để mở cmd :
 Windows -> Run -> cmd
 #### B2 kiểm tra xem máy ban đã có java, node.js, Git,npm:
#### .Kiểm tra java:
java --version
#### .Kiểm tra node js:
node --version
#### .Lệnh kiểm tra cài đặt npm:
npm -version

![image](https://user-images.githubusercontent.com/107382675/174943769-3a5d9f66-5a1f-4cd2-9e04-523673840e09.png)
#### B3 cày đăt npm và Jhipster:
##### a)Cài đặt Jhipster:
Lệnh cài đặt java, node.js, git:
###### .npm install -g generator-jhipster
![image](https://user-images.githubusercontent.com/107382675/174944299-4e84eb9a-0f7e-42b0-9a6b-889e08f559ef.png)

#### B4 Khởi tạo Monolithic và Microservices:
Khởi tạo Monolithic 
![image](https://user-images.githubusercontent.com/107382675/174944729-95eace9c-64a5-448f-bb8b-0a82319ea10e.png)
Khởi tạo Microservices
![image](https://user-images.githubusercontent.com/107382675/174944859-6c592711-2a66-468c-b004-773923512c11.png) 
###### a)Tạo microservices :
Microservices là một loại ứng dụng JHipster, không có giao diện người dùng (giao diện người dùng Angular phải được tạo trên một cổng) và hoạt động với JHipster Registry để được định cấu hình, phát hiện và quản lý.
###### b)Các thực thể trong kiến ​​trúc microservices:
Thực thể Người dùng không được tạo trong một microservice khi sử dụng JWT hoặc DTO. Khi OAuth 2.0 được sử dụng, có một cơ chế trong microservice để trích xuất dữ liệu người dùng từ mã thông báo và lưu nó vào cơ sở dữ liệu của microservice. Vì vậy, đối với JWT và DTO, bạn không thể sử dụng và / hoặc xác định mối quan hệ với thực thể Người dùng vì nó chỉ tồn tại trong cơ sở dữ liệu của cổng.

Mối quan hệ giữa các thực thể từ các dịch vụ vi mô khác nhau không được hỗ trợ.
###### c)Tạo thực thể:
Đối với các thực thể trong một microfrontend, hãy xem Microfrontends .

Việc sử dụng trình tạo phụ thực thể hoạt động hơi khác một chút trong kiến ​​trúc microservices, vì mã front-end và back-end không nằm trong cùng một ứng dụng.

Đầu tiên, tạo các thực thể trong ứng dụng microservice: điều này hoạt động như bình thường và bạn cũng có thể sử dụng JHipster UML hoặc JDL Studio để giúp bạn tạo các thực thể và mối quan hệ phức tạp. Vì microservices không có giao diện người dùng nên sẽ không có mã giao diện người dùng nào được tạo.

Sau đó, trên (các) cổng, hãy chạy lại trình tạo phụ thực thể. Một câu hỏi mới sẽ xuất hiện ở phần đầu, dành riêng cho các cổng:
###### .Bạn sẽ có lựa chọn để tạo một thực thể mới thông thường (một cổng cũng là một ứng dụng JHipster tiêu chuẩn, vì vậy điều này sẽ hoạt động giống như một ứng dụng nguyên khối) hoặc sử dụng cấu hình JHipster hiện có từ một microservice.
###### .Nếu bạn chọn tạo thực thể từ một microservice, bạn sẽ cần nhập đường dẫn đến microservice này trên máy tính cục bộ của mình và sau đó JHipster sẽ tạo mã giao diện người dùng trên cổng.
###### d)Microfrontends:
Hỗ trợ microfrontend đang được tiến hành. Việc triển khai có thể thay đổi và khác nhau giữa các khuôn khổ. Tham khảo Hỗ trợ Microfrontend để biết trạng thái mới nhất.

Việc triển khai microfrontends của JHipster sử dụng Liên kết mô-đun Webpack và cho phép việc triển khai các thực thể phía trước được đặt trong microservice thay vì trong cổng.

Một cổng vẫn được yêu cầu để chạy trong quá trình phát triển do quá trình xác thực.

Bạn có thể tìm thêm thông tin về cách bắt đầu microfrontends bằng cách sử dụng cổng hoặc một mình trong README đã tạo.
###### e)Bộ nhớ đệm phân tán với Hazelcast
Nếu ứng dụng của bạn sử dụng cơ sở dữ liệu SQL, JHipster đề xuất giải pháp bộ nhớ đệm cấp 2 khác với microservices:

###### .Giải pháp bộ nhớ đệm mặc định của JHipster với microservices là Hazelcast
###### .Bạn vẫn có thể chọn Ehcache (giải pháp mặc định với các ứng dụng nguyên khối) hoặc Caffeine hoặc chọn hoàn toàn không sử dụng bộ đệm
Giải pháp này là giải pháp mặc định với microservices, vì trong kiến ​​trúc này, ý tưởng là bạn sẽ mở rộng các dịch vụ của mình:

###### .với bộ nhớ cache cục bộ, các phiên bản dịch vụ của bạn sẽ không có bộ nhớ cache được đồng bộ hóa, dẫn đến dữ liệu không chính xác
###### .mà không có bất kỳ bộ nhớ cache nào, gánh nặng của việc mở rộng quy mô sẽ được chuyển sang cơ sở dữ liệu, điều này sẽ không tốt lắm (trừ khi bạn sử dụng tùy chọn Cassandra của chúng tôi)
Sử dụng Hazelcast với microservices sẽ dẫn đến một cấu hình cụ thể:

###### .Khi khởi động, ứng dụng của bạn sẽ kết nối với JHipster Registry để tìm xem các phiên bản khác của cùng một dịch vụ có đang chạy hay không
###### .Với devhồ sơ, JHipster sẽ tạo một cụm các trường hợp đó trên localhost ( 127.0.0.1), sử dụng một cổng khác nhau cho mỗi trường hợp. Theo mặc định, cổng Hazelcast là your application's port + 5701(vì vậy nếu cổng của ứng dụng của bạn là cổng 8081, thì Hazelcast sẽ sử dụng cổng 13782)
###### .Với prodcấu hình, JHipster sẽ tạo một cụm với tất cả các nút khác mà nó tìm thấy, sử dụng cổng Hazelcast mặc định ( 5701)

###### f)Microservices không có cơ sở dữ liệu:
Chỉ có thể tạo các ứng dụng microservices mà không có cơ sở dữ liệu. Điều này là do microservices nhỏ và không có mã quản lý người dùng.

Một microservice không có cơ sở dữ liệu là rất nhỏ và có thể được sử dụng để kết nối với một back-end cụ thể như một hệ thống kế thừa.
## 3)Tại sao lựa chọn JHipster:
 Chúng ta sẽ dễ dàng có được một project đủ mạnh mẽ đầy đủ những thứ cơ bản để bắt đầu với thời gian nhanh nhất.Và nếu bạn đang tập tành với Spring để trở thành 1 Java Web developer thì bạn nên quan tâm đến công nghệ này.
 ## 4)Tác dụng JHipster:
 ##### . Tao một ứng dụng 
 ##### . Tạo một thực thể
 ##### . Tạo một Sring Controller
 ##### . Tạo một Sring Service
 ##### . Tạo DTO
 ##### . Quản Lý Các mối quan hệ
 ##### . Quốc Tế hóa
 ##### . Nâng Cấp Ưng Dụng

 


