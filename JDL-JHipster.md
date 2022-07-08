# JDL-JHipster.

## Tổng quan:

### Ngôn ngữ miền JHipster (JDL)

JDL là ngôn ngữ miền dành riêng cho JHipster, nơi bạn có thể mô tả tất cả các ứng dụng, triển khai, thực thể và các mối quan hệ của chúng trong một tệp duy nhất (hoặc nhiều hơn một) với cú pháp thân thiện với người dùng.

Bạn có thể sử dụng JDL-Studio trực tuyến của chúng tôi hoặc một trong các plugin / tiện ích mở rộng JHipster IDE , có sẵn cho:

Nhật thực ,
Mã VS
để tạo tệp JDL và trực quan hóa UML của nó. Bạn cũng có thể tạo và xuất hoặc chia sẻ URL của mô hình JDL của mình.

Điều này có thể được sử dụng để thay thế cho việc sử dụng trình tạo phụ thực thể và là cách tiếp cận được khuyến nghị. Ý tưởng là việc quản lý các mối quan hệ bằng cách sử dụng công cụ trực quan sẽ dễ dàng hơn nhiều so với các câu hỏi và câu trả lời cổ điển của người Yeoman.

Dự án JDL có sẵn trên GitHub , nó là một dự án Mã nguồn mở giống như JHipster (Giấy phép Apache 2.0). Nó cũng có thể được sử dụng như một thư viện nút để phân tích cú pháp JDL.

## Các ứng dụng:

### Cú pháp:

Việc khai báo đơn được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107390350/177943319-5792e8b5-fea7-457d-a195-f1ce29bc9057.png)

-Các khóa / giá trị cấu hình ứng dụng được chỉ định bên dưới config(phải ở bên trong application)

-Có thể có 0, 1 hoặc bất kỳ tùy chọn ứng dụng nào bạn muốn (miễn là chúng hợp lệ)

-Các thực thể sẽ được tạo bên trong ứng dụng được liệt kê thông qua entities, đây là cách được khuyến nghị để tạo các thực thể trong ứng dụng.

-Điều này có thể được bỏ qua nhưng việc tạo các thực thể bên trong ứng dụng sẽ yêu cầu thực hiện điều đó:từ một tệp JDL khác bên trong ứng dụng
hoặc với CLI

-Từ entitieskhóa là tùy chọn: bạn có thể bỏ qua nó, nhưng mọi thực thể trong tệp JDL sẽ được tạo bên trong ứng dụng

-Các ứng dụng có thể có các tùy chọn thông thường (như dtohoặc service), thông tin thêm trong phần tiếp theo .

### Các tùy chọn trong ứng dụng.

Khai báo tùy chọn ( dto,, v.v. service) skipServerđược hỗ trợ trong các ứng dụng JDL, nhưng với một số quy tắc.

Giả sử chúng ta có tệp JDL này:

![image](https://user-images.githubusercontent.com/107390350/177943872-ee4399f7-eaaa-4587-ae02-e1b02a9d0ffc.png)

Trong mẫu này, chúng ta có thể thấy một số điều:

A, B, C, D, E and FCó 6 thực thể được khai báo trong tệp JDL:.
Chúng tôi có 3 ứng dụng:app1, app2 and app3
app1sử dụngA, B and C
app2sử dụngC and D
app3sử dụng E( * except A, B, C, D, F)
Mỗi ứng dụng này khai báo các tùy chọn và một tùy chọn chung cũng được khai báo.
app1sử dụng dtochoA, B and C
app2sử dụng paginatecho C(vì có một ngoại lệ)
app3sử dụng servicechoE
Toàn cầu cũng sử dụng pagination(cho mọi thực thể)
Đây là cách tệp được tạo:

app1
A: sẽ sử dụng paginate with infinite-scroll(tùy chọn chung không bị ghi đè bởi tùy chọn cục bộ) và dto with mapstruct
B: sẽ sử dụng các tùy chọn tương tự
C: cũng sẽ sử dụng các tùy chọn tương tự
app2:
C: sẽ sử dụng paginate with pagination(và không infinite-scroll, vì cái cục bộ được ưu tiên hơn)
D: sẽ sử dụng paginate with infinite-scrollnhư tùy chọn trước đó không bao gồmD
app3:
E: sẽ paginate with infinite-scrollvàservice E with serviceClass
Ví dụ này minh họa nguyên tắc đổ bóng . Các tùy chọn chung được hỗ trợ và sẽ được sử dụng bởi mọi ứng dụng đã khai báo trừ khi các tùy chọn cũng được khai báo trong các ứng dụng.

Cũng lưu ý đoạn mã này được lấy từ mẫu trước đó trong app3:

entities * except A, B, C, D, F
service * with serviceClass
Về cơ bản, điều này có nghĩa là app3sẽ chỉ sử dụng Evà các thực thể của ứng dụng sẽ sử dụng servicetùy chọn, có nghĩa là Evà không A to F.

Cuối cùng, Fthực thể không có trong bất kỳ ứng dụng nào và thực thể này sẽ không được tạo vì điều đó.

### Các ví dụ

Ví dụ cơ bảnPermalink to "Basic example"

![image](https://user-images.githubusercontent.com/107390350/177944177-0f2a42e3-3afd-4939-8c92-25abefe77ed6.png)

Nhiều ứng dụng

![image](https://user-images.githubusercontent.com/107390350/177944177-0f2a42e3-3afd-4939-8c92-25abefe77ed6.png)

Với các thực thể

![image](https://user-images.githubusercontent.com/107390350/177944475-89ca2c8d-640f-4677-a437-c3600e4c5020.png)

Với các tùy chọn

![image](https://user-images.githubusercontent.com/107390350/177944714-99b47fe8-810f-4e98-89ce-c5385bc7a5d5.png)


### Toàn bộ bảng phân tích ví dụ

![image](https://user-images.githubusercontent.com/107390350/177944873-b1bedb70-64a8-4355-9de7-271bc6d456b6.png)

Bây giờ, một số điều sẽ xảy ra khi tạo các ứng dụng và thư mục này:

Bốn ứng dụng sẽ được tạo:

myMonolith trong ./myMonolith, với cổng máy chủ8080
myGateway trong ./myGateway, với cổng máy chủ9042
microserviceA trong ./microserviceA, với cổng máy chủ8081

Mặc dù chúng tôi không chỉ định cổng máy chủ, JHipster đặt một cổng theo mặc định.

Đối với microservices, mặc định là8081

Đối với cổng và đá nguyên khối, nó8080
microserviceB trong ./microserviceBvới cổng máy chủ8082

Bốn thực thể sẽ được tạo

Avà Btrong nguyên khối

Cvà Dcả trong cửa ngõ

Ctrong microservice đầu tiên

Dtrong microservice thứ hai

Tùy microservicechọn này ngầm hiểu cho CvàD

Vì chúng được tạo trên hai microservices nên tùy chọn này sẽ được đặt theo mặc định.

Các tùy chọn hoạt động giống như trước đây

Lưu ý rằng trình tạo đặt các giá trị mặc định nếu chúng không có (như databaseType). JHipster Core làm những điều tương tự cho bạn.

Đối phó với microservices là một công việc gần như phức tạp, nhưng JDL cung cấp cho bạn một số tùy chọn để xử lý các thực thể của bạn khi bạn thấy phù hợp. Với microservice <ENTITIES> with <MICROSERVICE_APP_NAME>bạn, bạn có thể chỉ định thực thể nào được tạo trong microservice nào.

Lấy ví dụ như thiết lập này:

![image](https://user-images.githubusercontent.com/107390350/177945309-1236cffd-4757-4b93-96ad-9e3536b440d0.png)

Với hai ứng dụng JHipster ('firstMS' và 'secondMS'), đây là những gì bạn sẽ nhận được nếu nhập tệp JDL trong hai ứng dụng:

Trong 'firstMS', các thực thể Avà Csẽ được tạo.
Trong 'secondMS', các thực thể Bvà Csẽ được tạo.
Cđược tạo cả hai vì nếu không có tùy chọn microservice chỉ định nơi thực thể này được tạo, nó sẽ được tạo ở mọi nơi.

Nếu bạn quyết định nhập JDL này trong một ứng dụng nguyên khối, mọi thực thể sẽ được tạo (nguyên khối không có tùy chọn hạn chế trong JDL).

Lưu ý: nếu bạn muốn tạo cùng một thực thể trong hai dịch vụ nhỏ khác nhau, bạn có thể ghi hai tệp JDL thay vì cập nhật tệp JDL. Mỗi lần.

Ví dụ trước không thể được viết như thế này:

![image](https://user-images.githubusercontent.com/107390350/177945459-2cf9e2fe-0f79-4bab-a1bf-746bd2a95b09.png)

Đây là kết quả:

Trong 'firstMS', chỉ thực thể Csẽ được tạo
Trong 'secondMS', các thực thể Bvà Csẽ được tạo.
Đó là bởi vì, tại thời điểm phân tích cú pháp, nếu một tùy chọn trùng lặp với một tùy chọn khác, thì tùy chọn sau sẽ được ưu tiên hơn. Bạn cũng có thể tạo toàn bộ ngăn xếp microservice bằng JDL, hãy xem bài đăng trên blog này chẳng hạn

### Các tùy chọn cấu hình ứng dụng có sẵn.

Dưới đây là các tùy chọn ứng dụng được hỗ trợ trong JDL:

![image](https://user-images.githubusercontent.com/107390350/177946047-056ecfc4-15bc-4772-b3ea-9d4e15ff7acd.png)
![image](https://user-images.githubusercontent.com/107390350/177946194-bc7f29ef-8e36-435b-ada0-ec10ba36a5f5.png)

## Thực thể:

### Cú pháp

Việc khai báo thực thể được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107390350/177946425-44006ac6-269b-484d-8a09-d5eb3417c475.png)

<entity name>tên của thực thể,
<field name>tên của một trường của thực thể,
<field type>loại trường được hỗ trợ JHipster,
và như một tùy chọn:
<entity javadoc>tài liệu của thực thể,
<entity annotation>các tùy chọn cho thực thể (xem Tùy chọn để có danh sách đầy đủ các tùy chọn có sẵn),
<table name>tên bảng cơ sở dữ liệu (nếu bạn muốn chỉ định một cái gì đó khác mà tên được tính tự động từ tên thực thể),
<field javadoc>tài liệu của lĩnh vực này,
<field annotation>các tùy chọn cho trường,
<validation>các xác nhận cho trường.

Tuyên bố Blob
JHipster cung cấp một sự lựa chọn tuyệt vời vì người ta có thể chọn giữa một loại hình ảnh hoặc bất kỳ loại nhị phân nào. JDL cho phép bạn làm điều tương tự. Tạo một loại tùy chỉnh (xem DataType) bằng trình chỉnh sửa, đặt tên cho nó theo các quy ước sau:

AnyBlobhoặc Blobđể tạo một trường thuộc loại nhị phân "bất kỳ";
ImageBlobđể tạo một trường có nghĩa là một hình ảnh.
TextBlobđể tạo trường cho CLOB (văn bản dài).
Và bạn có thể tạo bao nhiêu DataTypes tùy thích.

Biểu thức chính quy
Đây là một xác thực nhất định (chỉ có sẵn cho các loại Chuỗi) và cú pháp của nó là:

![image](https://user-images.githubusercontent.com/107390350/177946664-dd9efec5-c3b4-43d4-8a0c-3792f006562f.png)

Hãy chia nhỏ nó ra:

patternlà từ khóa để khai báo xác thực regex (với dấu ngoặc đơn bình thường)
/.../mẫu được khai báo bên trong hai dấu gạch chéo
\chống chém không cần thiết phải thoát
Bình luận
Có thể nhận xét trong JDL cho các thực thể và trường, và sẽ tạo ra tài liệu (Javadoc hoặc JSDoc, tùy thuộc vào phần phụ trợ).

![image](https://user-images.githubusercontent.com/107390350/177946816-19578aab-0858-4e22-ba55-6bfa76e8ea32.png)

Những bình luận này sau đó sẽ được thêm vào dưới dạng bình luận Javadoc của JHipster. JDL sở hữu loại nhận xét riêng của nó:

// một bình luận bị bỏ qua
/ ** không phải là một bình luận bị bỏ qua * /
Do đó, bất kỳ thứ gì bắt đầu bằng //đều được coi là nhận xét nội bộ cho JDL và sẽ không được tính là Javadoc. Xin lưu ý rằng các lệnh JDL Studio bắt đầu bằng #sẽ bị bỏ qua trong quá trình phân tích cú pháp.

Một dạng nhận xét khác là các nhận xét sau:

![image](https://user-images.githubusercontent.com/107390350/177947133-be3100a2-2841-450c-98a0-fa02ba6096bf.png)

Ở đây tên của A sẽ được nhận xét với My super field, B với My other super field.

Có, dấu phẩy không phải là bắt buộc nhưng sẽ khôn ngoan hơn nếu có chúng để không mắc lỗi trong mã. Nếu bạn muốn kết hợp dấu phẩy và nhận xét sau, hãy cẩn thận!

![image](https://user-images.githubusercontent.com/107390350/177947260-09bd4fda-4860-4cc3-a7e2-291e424876f7.png)

### Các loại trường và xác thực

![image](https://user-images.githubusercontent.com/107390350/177947649-921bf2bd-d722-46bc-897d-74124e002042.png)

## EnumsPermalink to " JHipster Domain Language (JDL) - Enums"

### Cú pháp

Việc khai báo điều tra được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107390350/177947961-e20e9e4e-4c56-48a5-a249-c29d49538764.png)

Giá trị mục nhập liệt kê là bắt buộc
Và các phím chữ hoa phải được sử dụng
Giá trị mục nhập liệt kê là tùy chọn và phải được đặt bên trong dấu ngoặc đơn

## Mối quan hệ:

### Các kiểu quan hệ

Được đề cập sau relationshiptừ khóa.

Có bốn kiểu quan hệ:

OneToOne

OneToMany

ManyToOne

ManyToMany

Để biết thêm về các mối quan hệ và những gì có thể đạt được, bạn có thể truy cập trang dành riêng .

### Các phương pháp quan hệ

Cú pháp này thực sự hữu ích khi:

Bạn có nhiều mối quan hệ cùng loại,

Bạn muốn biết các mối quan hệ là gì,

Bạn không muốn mất thời gian tìm kiếm chúng trong (các) tệp JDL của mình

### Cú pháp

![image](https://user-images.githubusercontent.com/107390350/177948556-9a06b5d0-b6d2-47d7-acdd-4d72e6f29776.png)

(OneToMany | ManyToOne| OneToOne | ManyToMany)là kiểu mối quan hệ của bạn,

<from entity>là tên của chủ sở hữu thực thể của mối quan hệ: nguồn,

<to entity>là tên của thực thể mà mối quan hệ đi đến: đích,

<relationship name>là tên của trường có đầu kia là loại,

<display field>là tên của trường sẽ hiển thị trong các hộp chọn (mặc định id:),

requiredtrường được tiêm có được yêu cầu hay không.
with jpaDerivedIdentifiercó @MapsIdđược sử dụng cho liên kết hay không (chỉ áp dụng cho một đối một)

#### OneToMany

Tạo Car:

![image](https://user-images.githubusercontent.com/107390350/177953533-b61023ca-6a97-4fb8-b09b-2afc712e615d.png)

Điều tương tự cũng có thể đạt được bằng cách sử dụng JDL bên dưới

![image](https://user-images.githubusercontent.com/107390350/177953629-e2d26ead-ae7f-4ccf-9959-ce30bd69174e.png)

#### ManyToOne

Điều này tương đương với mối quan hệ một-nhiều hai chiều sau khi đảo các cạnh trong tệp JDL:

![image](https://user-images.githubusercontent.com/107390350/177953974-10cab4a9-0be3-452f-8830-312d05612e7d.png)

Thực hiện mối quan hệ đó vì hai lý do:

Theo quan điểm kinh doanh, bạn chỉ sử dụng các thực thể của mình theo cách này. Vì vậy, bạn không muốn có một API cho phép các nhà phát triển làm điều gì đó không có ý nghĩa.

Bạn có một mức tăng hiệu suất nhỏ khi sử dụng Ownerthực thể

Tạo Owner:

![image](https://user-images.githubusercontent.com/107390350/177954405-368d9bd9-8250-4d28-840e-e4b58333e830.png)

Trên giao diện người dùng ứng dụng Angular / React được tạo, bạn sẽ có một menu thả xuống Carđể chọn Owner. Đây là JDL tương ứng:

![image](https://user-images.githubusercontent.com/107390350/177954645-686a8dca-df5b-4a45-bd4d-6aebfd3bebad.png)

#### OneToMany

Mối quan hệ một chiều một-nhiều có nghĩa là Ownercá thể có thể nhận được bộ sưu tập xe của nó, nhưng không phải ngược lại. Nó ngược lại với ví dụ trước

![image](https://user-images.githubusercontent.com/107390350/177954926-465a5cf7-b21b-4ddd-ad51-2ad56a7e2fea.png)

Loại mối quan hệ này không được cung cấp theo mặc định trong JHipster vào lúc này, hãy xem # 1569 để biết thêm thông tin.

Bạn có hai giải pháp cho việc này:

Thực hiện ánh xạ hai chiều và sử dụng nó mà không cần sửa đổi: đây là cách tiếp cận được đề xuất của chúng tôi, vì nó đơn giản hơn nhiều

Thực hiện ánh xạ hai chiều, sau đó sửa đổi nó để biến nó thành ánh xạ một hướng:

Xóa thuộc tính “mappedBy” trên @OneToManychú thích của bạn

Tạo bảng tham gia bắt buộc: bạn có thể thực hiện mvn liquibase:diffđể tạo bảng đó, xem tài liệu về cách sử dụng Liquibase diff

Điều này không được hỗ trợ với JDL vì nó không có trong JHipster.

#### TwoOneToMany

Đối với ví dụ này, a Personcó thể là chủ sở hữu của nhiều ô tô và cũng có thể là người điều khiển nhiều ô tô:

![image](https://user-images.githubusercontent.com/107390350/177955267-11a12a7e-54de-4995-a9eb-ce43609f7d5d.png)

Tạo Personthực thể, có hai mối quan hệ một-nhiều với Carthực thể:

![image](https://user-images.githubusercontent.com/107390350/177955400-e039f78e-8bb4-4559-b1a0-7a69adf1e37b.png)

Tạo Carthực thể, sử dụng cùng một tên quan hệ đã được định cấu hình trong Personthực thể

![image](https://user-images.githubusercontent.com/107390350/177955493-ef006a24-99bf-4ab7-b99d-97de1537aadf.png)

Điều tương tự cũng có thể đạt được bằng cách sử dụng JDL bên dưới

![image](https://user-images.githubusercontent.com/107390350/177955577-ca6f7b34-bae0-4f20-80c6-b80b8e93f3af.png)

#### ManyToMany

A Drivercó thể lái nhiều ô tô, nhưng một Carcan cũng có nhiều tài xế.

![image](https://user-images.githubusercontent.com/107390350/177955853-afd99ace-6a23-4638-995e-a3ad7f98cb07.png)

 Tạo ra mặt không sở hữu của mối quan hệ, Drivervới mối quan hệ nhiều-nhiều:

 ![image](https://user-images.githubusercontent.com/107390350/177956038-7d663640-75e2-4303-a69f-4ade13a60900.png)

 Tạo Car, với mặt riêng của mối quan hệ nhiều-nhiều:

 ![image](https://user-images.githubusercontent.com/107390350/177956171-5d1c4618-f068-4caf-acf7-cedc7f1e596d.png)

 Điều tương tự cũng có thể đạt được bằng cách sử dụng JDL bên dưới

 ![image](https://user-images.githubusercontent.com/107390350/177956297-b00afbb8-057b-438f-8fab-e8207a30c7b6.png)

 ### Triển khai

#### Cú pháp

Khai báo triển khai được thực hiện như sau:

![image](https://user-images.githubusercontent.com/107390350/177956892-7358fe09-0a61-4c17-9318-0307382d4bdf.png)

#### Các ví dụPermalink to "Examples"

![image](https://user-images.githubusercontent.com/107390350/177957088-1446e921-05d1-4fdc-a946-65ead849285a.png)

Nhiều triển khai

![image](https://user-images.githubusercontent.com/107390350/177957219-2514cbd4-c922-4979-8b6f-71f3e594a3ff.png)

#### Các tùy chọn triển khai có sẵnPermalink to "Available deployment options"

![image](https://user-images.githubusercontent.com/107390350/177957514-e81beaef-3858-4cc9-ba28-d1715c328629.png)

#### Xử lý sự cố

Chúng tôi đã cố gắng giữ cho cú pháp thân thiện nhất có thể đối với các nhà phát triển. Bạn có thể làm những điều này với nó:

Khai báo các ứng dụng với các tùy chọn và thực thể của chúng,

Khai báo các thực thể với các thuộc tính của chúng,

Khai báo các mối quan hệ giữa chúng,

Và khai báo một số tùy chọn cụ thể của JHipster.

