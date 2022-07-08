## 1)Ngôn ngữ miền JHipster (JDL):
JDL là ngôn ngữ miền dành riêng cho JHipster, nơi bạn có thể mô tả tất cả các ứng dụng, triển khai, thực thể và các mối quan hệ của chúng trong một tệp duy nhất (hoặc nhiều hơn một) với cú pháp thân thiện với người dùng.
Để tạo tệp JDL và trực quan hóa UML của nó. Bạn cũng có thể tạo và xuất hoặc chia sẻ URL của mô hình JDL của mình.

Điều này có thể được sử dụng để thay thế cho việc sử dụng trình tạo phụ thực thể và là cách tiếp cận được khuyến nghị. Ý tưởng là việc quản lý các mối quan hệ bằng cách sử dụng công cụ trực quan sẽ dễ dàng hơn nhiều so với các câu hỏi và câu trả lời cổ điển của người Yeoman.

Dự án JDL có sẵn trên GitHub , nó là một dự án Mã nguồn mở giống như JHipster. Nó cũng có thể được sử dụng như một thư viện nút để phân tích cú pháp JDL.
### a)Tạo nội dung:
#### Sử dụng tệp:
Bạn có thể sử dụng tệp JDL để tạo các thực thể:
- Tạo tệp có phần mở rộng '.jh' hoặc '.jdl',
- Khai báo các ứng dụng, triển khai, thực thể và mối quan hệ của bạn hoặc tạo và tải xuống tệp bằng JDL-Studio hoặc JHipster IDE ,
- Nếu bạn chỉ tạo các thực thể thì hãy chạy jhipster jdl my_file.jdltrong thư mục gốc của ứng dụng JHipster của bạn.
- Nếu bạn đang tạo ứng dụng thì hãy chạy jhipster jdl my_file.jdltrong một thư mục.

Nếu bạn làm việc theo nhóm, có lẽ bạn muốn có nhiều tệp thay vì một. Chúng tôi đã thêm tùy chọn này để bạn không nối tất cả các tệp thành một theo cách thủ công, bạn phải chạy:

 `jhipster jdl my_file1.jdl my_file2.jdl`

 Nếu bạn không muốn tạo lại các thực thể của mình trong khi nhập JDL, bạn có thể sử dụng --json-onlycờ để bỏ qua phần tạo thực thể và chỉ tạo các tệp json trong .jhipsterthư mục.

 `jhipster jdl ./my-jdl-file.jdl --json-only`

 Theo mặc định jdl, chỉ tạo lại các thực thể đã thay đổi, nếu bạn muốn tất cả các thực thể của mình được tạo lại thì hãy chuyển vào --forcecờ. Xin lưu ý rằng điều này sẽ ghi đè lên tất cả các thay đổi cục bộ của bạn đối với các tệp thực thể:

 `jhipster jdl ./my-jdl-file.jdl --force`

 Nếu bạn muốn sử dụng nó trong dự án của mình, bạn có thể thêm nó bằng cách thực hiện:
 - NPM:npm install jhipster-core --save
 - Sợi:yarn add jhipster-core
 #### Sử dụng JDL nội tuyến:
 Cách khác để tạo nội dung là chuyển mã JDL trong CLI của bạn, theo cách này jhipster jdl --inline "application { config { baseName jhipster, applicationType microservice } }":.

Cách tạo nội dung này đặc biệt hữu ích khi tạo các thực thể.

Bây giờ, chúng ta sẽ bắt đầu với nội dung JDL nhỏ để tìm hiểu các cách khác nhau để tạo nội dung. Giải thích sẽ được thực hiện trong các phần khác về cú pháp nhưng sẽ tập trung vào thế hệ ở đây.

Đây là nội dung cơ bản mà chúng tôi sẽ sử dụng:

```js
 application {
  config {
    baseName jhipster
    applicationType microservice
  }
} 
```
Đây là một ứng dụng microservice rất cơ bản có tên là “jhipster” và chúng ta sẽ xem các cách khác nhau để tạo một ứng dụng từ mẫu này.

Bạn sẽ thấy rằng, với mẫu nhỏ này, bạn đã quản lý để tạo một ứng dụng từ đầu.
### b)Sử dụng tệp JDL từ xa:
Bạn cũng có thể sử dụng một URL với jdllệnh. Chỉ cần chuyển URL thay vì tên tệp như bên dưới

`jhipster jdl https://my-site.com/my.jdl`


`jhipster jdl https://gist.githubusercontent.com/user/id/raw/id/myapp.jdl`

`jhipster jdl default.jdl`
### c)Tạo ứng dụng:
#### Cú pháp:
Việc khai báo đơn được thực hiện như sau:
```js
application {
  config {
    <application option name> <application option value>
  }
  [entities <application entity list>]
  [<options>]
}
```
- Các khóa / giá trị cấu hình ứng dụng được chỉ định bên dưới config(phải ở bên trong application)
- Có thể có 0, 1 hoặc bất kỳ tùy chọn ứng dụng nào bạn muốn (miễn là chúng hợp lệ)
- Các thực thể sẽ được tạo bên trong ứng dụng được liệt kê thông qua entities, đây là cách được khuyến nghị để tạo các thực thể trong ứng dụng.
  - Điều này có thể được bỏ qua nhưng việc tạo các thực thể bên trong ứng dụng sẽ yêu cầu thực hiện điều đó:
từ một tệp JDL khác bên trong ứng dụng
hoặc với CLI
- Từ entitieskhóa là tùy chọn: bạn có thể bỏ qua nó, nhưng mọi thực thể trong tệp JDL sẽ được tạo bên trong ứng dụng
- Các ứng dụng có thể có các tùy chọn thông thường (như dtohoặc service), thông tin thêm trong phần tiếp theo .
#### Các tùy chọn trong ứng dụng:
Khai báo tùy chọn ( dto,, v.v. service) skipServerđược hỗ trợ trong các ứng dụng JDL, nhưng với một số quy tắc.

Giả sử chúng ta có tệp JDL này:
```js
application {
  config {
    baseName app1
  }
  entities A, B, C
  dto * with mapstruct
}

application {
  config {
    baseName app2
  }
  entities C, D
  paginate * with pagination except D 
}

application {
  config {
    baseName app3
  }
  entities * except A, B, C, D, F
  service * with serviceClass
}

entity A
entity B
entity C
entity D
entity E
entity F

paginate * with infinite-scroll
```
Trong mẫu này, chúng ta có thể thấy một số điều:

- A, B, C, D, E and FCó 6 thực thể được khai báo trong tệp JDL:.
- Chúng tôi có 3 ứng dụng:app1, app2 and app3
  - app1sử dụngA, B and C
  - app2sử dụngC and D
  - app3sử dụng E( * except A, B, C, D, F)
- Mỗi ứng dụng này khai báo các tùy chọn và một tùy chọn chung cũng được khai báo.
  - app1sử dụng dtochoA, B and C
  - app2sử dụng paginatecho C(vì có một ngoại lệ)
  - app3sử dụng servicechoE
Toàn cầu cũng sử dụng pagination(cho mọi thực thể)

Đây là cách tệp được tạo:

- app1
  - A: sẽ sử dụng paginate with infinite-scroll(tùy chọn chung không bị ghi đè bởi tùy chọn cục bộ) và dto with mapstruct
  - B: sẽ sử dụng các tùy chọn tương tự
  - C: cũng sẽ sử dụng các tùy chọn tương tự
- app2:
  - C: sẽ sử dụng paginate with pagination(và không infinite-scroll, vì cái cục bộ được ưu tiên hơn)
  - D: sẽ sử dụng paginate with infinite-scrollnhư tùy chọn trước đó không bao gồmD
- app3:
  - E: sẽ paginate with infinite-scrollvàservice E with serviceClass

Ví dụ này minh họa nguyên tắc đổ bóng . Các tùy chọn chung được hỗ trợ và sẽ được sử dụng bởi mọi ứng dụng đã khai báo trừ khi các tùy chọn cũng được khai báo trong các ứng dụng.

Cũng lưu ý đoạn mã này được lấy từ mẫu trước đó trong app3:
```js
entities * except A, B, C, D, F
service * with serviceClass
```
Về cơ bản, điều này có nghĩa là app3sẽ chỉ sử dụng Evà các thực thể của ứng dụng sẽ sử dụng servicetùy chọn, có nghĩa là Evà không A to F.

Cuối cùng, Fthực thể không có trong bất kỳ ứng dụng nào và thực thể này sẽ không được tạo vì điều đó.

Lưu ý: tất cả các tùy chọn thông thường đều được hỗ trợ tại thời điểm này.

#### Các ví dụ:
Ví dụ cơ bản
```js
application {
  config {
    baseName exampleApp
    applicationType gateway
  }
}
```
Nhiều ứng dụng
```js
application {
  config {
    baseName exampleApp1
    applicationType microservice
    serverPort 9001
  }
}

application {
  config {
    baseName exampleApp2
    applicationType microservice
    serverPort 9002
  }
}

application {
  config {
    baseName exampleApp3
    applicationType gateway
    serverPort 9000
  }
}
```
Với các thực thể
```js
application {
  config {
    baseName exampleApp1
    applicationType microservice
    serverPort 9001
  }
  entities A
}

application {
  config {
    baseName exampleApp2
    applicationType microservice
    serverPort 9002
  }
  entities * except A
}

entity A
entity B
entity C
```
Với các tùy chọn
```js
application {
  config {
    baseName exampleApp1
    applicationType microservice
    serverPort 9001
  }
  entities A
  dto A with mapstruct 
}

application {
  config {
    baseName exampleApp2
    applicationType microservice
    serverPort 9002
  }
  entities * except A
  paginate C with pagination
}

entity A
entity B
entity C
```
Toàn bộ bảng phân tích ví dụ
Ví dụ 1:
```js
application {
  config {
    baseName myMonolith
    applicationType monolith
  }
  entities * except C, D
}
application {
  config {
    baseName myGateway
    applicationType gateway
    serverPort 9042
  }
  entities * except A, B
}
application {
  config {
    baseName microserviceA
    applicationType microservice
  }
  entities C
}
application {
  config {
    baseName microserviceB
    applicationType microservice
    serverPort 8082
  }
  entities D
}
entity A
entity B
entity C
entity D
dto * with mapstruct
service * with serviceClass
paginate D with pagination
```
Bây giờ, một số điều sẽ xảy ra khi tạo các ứng dụng và thư mục này:

- Bốn ứng dụng sẽ được tạo:
  - myMonolith trong ./myMonolith, với cổng máy chủ8080
  - myGateway trong ./myGateway, với cổng máy chủ9042
  - microserviceA trong ./microserviceA, với cổng máy chủ8081
     - Mặc dù chúng tôi không chỉ định cổng máy chủ, JHipster đặt một cổng theo mặc định.
     - Đối với microservices, mặc định là8081
     - Đối với cổng và đá nguyên khối, nó8080
  - microserviceB trong ./microserviceBvới cổng máy chủ8082
- Bốn thực thể sẽ được tạo
   - A và Btrong nguyên khối
   - C và Dcả trong cửa ngõ
      - Ctrong microservice đầu tiên
      - Dtrong microservice thứ hai
- Tùy microservicechọn này ngầm hiểu cho CvàD
   - Vì chúng được tạo trên hai microservices nên tùy chọn này sẽ được đặt theo mặc định.
- Các tùy chọn hoạt động giống như trước đây

Lưu ý rằng trình tạo đặt các giá trị mặc định nếu chúng không có (như databaseType). JHipster Core làm những điều tương tự cho bạn.



#### Quy trình làm việc microservice:
Đối phó với microservices là một công việc gần như phức tạp, nhưng JDL cung cấp cho bạn một số tùy chọn để xử lý các thực thể của bạn khi bạn thấy phù hợp. Với microservice <ENTITIES> with <MICROSERVICE_APP_NAME>bạn, bạn có thể chỉ định thực thể nào được tạo trong microservice nào.

Lấy ví dụ như thiết lập này:
```js
entity A
entity B
entity C
microservice A with firstMS
microservice B with secondMS
```
Với hai ứng dụng JHipster ('firstMS' và 'secondMS'), đây là những gì bạn sẽ nhận được nếu nhập tệp JDL trong hai ứng dụng:

- Trong 'firstMS', các thực thể Avà Csẽ được tạo.
- Trong 'secondMS', các thực thể Bvà Csẽ được tạo.
C được tạo cả hai vì nếu không có tùy chọn microservice chỉ định nơi thực thể này được tạo, nó sẽ được tạo ở mọi nơi.

Nếu bạn quyết định nhập JDL này trong một ứng dụng nguyên khối, mọi thực thể sẽ được tạo (nguyên khối không có tùy chọn hạn chế trong JDL).

Lưu ý: nếu bạn muốn tạo cùng một thực thể trong hai dịch vụ nhỏ khác nhau, bạn có thể ghi hai tệp JDL thay vì cập nhật tệp JDL. Mỗi lần.

Ví dụ trước không thể được viết như thế này:
```js
entity A
entity B
entity C
microservice * except B with firstMS
microservice * except A with secondMS
```
Đây là kết quả:

- Trong 'firstMS', chỉ thực thể Csẽ được tạo
- Trong 'secondMS', các thực thể Bvà C sẽ được tạo.

Như chúng ta đã thấy trong ví dụ trước, việc tạo ứng dụng khá đơn giản, hãy lấy ví dụ trước và thêm nhiều thứ vào đó:

```js
application {
  config {
    baseName jhipster
    applicationType microservice
    serverPort 4242
    buildTool gradle
  }
}
```
Hãy chia nhỏ nó ra:

- applicationlà từ khóa để nói rằng bạn muốn khai báo một ứng dụng
- configđể nói rằng bạn muốn chỉ định cấu hình
sau này chúng ta sẽ thấy rằng bạn cũng có thể khai báo các thực thể trong các ứng dụng
- baseName, applicationTypev.v. là các từ khóa để điều chỉnh ứng dụng
### d)Tạo thực thể:
#### Cú pháp:
Việc khai báo thực thể được thực hiện như sau:
```js
[<entity javadoc>]
[<entity annotation>*]
entity <entity name> [(<table name>)] {
  [<field javadoc>]
  [<field annotation>*]
  <field name> <field type> [<validation>*]
}
```
- <entity name>tên của thực thể,
- <field name>tên của một trường của thực thể,
- <field type>loại trường được hỗ trợ JHipster,
- và như một tùy chọn:
  - <entity javadoc>tài liệu của thực thể,
  - <entity annotation>các tùy chọn cho thực thể (xem Tùy chọn để có danh sách đầy đủ các tùy chọn có sẵn),
  - <table name>tên bảng cơ sở dữ liệu (nếu bạn muốn chỉ định một cái gì đó khác mà tên được tính tự động từ tên thực thể),
  - <field javadoc>tài liệu của lĩnh vực này,
  - <field annotation>các tùy chọn cho trường,
  - <validation>các xác nhận cho trường.
#### Các ví dụ:
##### Ví dụ cơ bản :

`entity A`

Điều này tương đương với:

`entity A(a) {}`

Trước đây là dạng đơn giản hơn, không chỉ định “body” (dấu ngoặc nhọn cho các trường) và tên bảng.

##### Với tên bảng tùy chỉnh:
Chỉ định tên bảng tùy chỉnh cũng có thể:

` entity A(my_super_entity)`

##### Với các lĩnh vực:
```js
entity A {
  name String required
  age Integer
}
```
##### Với xác thực trường:
```js
entity A {
  name String required
  age Integer min(42) max(42)
}
```
##### Tuyên bố Blob:
JHipster cung cấp một sự lựa chọn tuyệt vời vì người ta có thể chọn giữa một loại hình ảnh hoặc bất kỳ loại nhị phân nào. JDL cho phép bạn làm điều tương tự. Tạo một loại tùy chỉnh (xem DataType) bằng trình chỉnh sửa, đặt tên cho nó theo các quy ước sau:

- AnyBlobhoặc Blobđể tạo một trường thuộc loại nhị phân "bất kỳ";
- ImageBlobđể tạo một trường có nghĩa là một hình ảnh.
- TextBlobđể tạo trường cho CLOB (văn bản dài).
Và bạn có thể tạo bao nhiêu DataTypes tùy thích.

##### Biểu thức chính quy:
Đây là một xác thực nhất định (chỉ có sẵn cho các loại Chuỗi) và cú pháp của nó là:
```js
entity A {
  name String pattern(/^[A-Z][a-z]+\d$/)
}
```
Hãy chia nhỏ nó ra:

- patternlà từ khóa để khai báo xác thực regex (với dấu ngoặc đơn bình thường)
- /.../mẫu được khai báo bên trong hai dấu gạch chéo
- \chống chém không cần thiết phải thoát
##### Bình luận:
Có thể nhận xét trong JDL cho các thực thể và trường, và sẽ tạo ra tài liệu (Javadoc hoặc JSDoc, tùy thuộc vào phần phụ trợ).
```js
/**
 * This is a comment
 * about a class
 * @author Someone
 */
entity A {
  /**
   * This comment will also be used!
   * @type...
   */
   name String
   age Integer // this is yet another comment
}
```
Những bình luận này sau đó sẽ được thêm vào dưới dạng bình luận Javadoc của JHipster. JDL sở hữu loại nhận xét riêng của nó:

- // một bình luận bị bỏ qua
- / ** không phải là một bình luận bị bỏ qua * /
Do đó, bất kỳ thứ gì bắt đầu bằng //đều được coi là nhận xét nội bộ cho JDL và sẽ không được tính là Javadoc. Xin lưu ý rằng các lệnh JDL Studio bắt đầu bằng #sẽ bị bỏ qua trong quá trình phân tích cú pháp.

Một dạng nhận xét khác là các nhận xét sau:
```js
entity A {
  name String /** My super field */
  count Integer /** My other super field */
}
```
Ở đây tên của A sẽ được nhận xét với My super field, B với My other super field.

Có, dấu phẩy không phải là bắt buộc nhưng sẽ khôn ngoan hơn nếu có chúng để không mắc lỗi trong mã. Nếu bạn muốn kết hợp dấu phẩy và nhận xét sau, hãy cẩn thận!
```js
entity A {
  name String, /** My comment */
  count Integer
}
```
Tên của A sẽ không có nhận xét, vì số lượng.
#### Tạo một thực thể cơ bản:
`entity A`

Thực thể này không có các trường hoặc thậm chí là một tên bảng rõ ràng (mặc dù JHipster đặt một cho bạn từ tên của thực thể). Đây là cách đơn giản nhất có thể để khai báo một thực thể.

Lưu ý rằng biểu mẫu này tương đương với:

`entity A(a) {}`

Chúng tôi đã thêm tên bảng và dấu ngoặc nhọn. Theo mặc định, JHipster tạo tên bảng dựa trên tên thực thể được chỉ định.

Dấu ngoặc nhọn cần thiết khi khai báo các trường.
#### Thêm nhận xét:
Đây là cách để thêm nhận xét vào một thực thể:
```js
/**
 * This is a simple entity
 */
entity A

```
Nếu chương trình phụ trợ bằng Java, điều này sẽ thêm nhận xét Javadoc.

#### Các thực thể trong ứng dụng:
Để chỉ tạo một số thực thể trong một ứng dụng, entities từ khóa có thể được sử dụng:
```js
application {
  config {}
  entities A, B
}

application {
  config {}
  entities C
}

entity A
entity B
entity C
```
Điều này đặc biệt hữu ích trong các kiến ​​trúc microservice.
### e)Tạo trường:
Các trường được khai báo trong các thực thể, bằng cách chỉ định một phần thân cho một thực thể:
```js
entity MyEntity {
  name String
  closed Boolean
}
```
Có nhiều hơn hai loại này, hãy xem chúng trong trang thực thể & trường .

#### Thêm nhận xét và xác nhận:
Giống như cách chúng tôi đã thêm nhận xét vào các thực thể, chúng tôi có thể thêm nhận xét vào các trường:
```js
entity MyEntity {
  /** My field */
  name String required minlength(2) maxlength(50)
}
```
Việc xác thực phụ thuộc vào loại trường 

### f)Bảng kê 
#### Cú pháp:
Việc khai báo điều tra được thực hiện như sau:
```js
enum <enum name> {
  <ENUM KEY> [(<enum value>)]
}
```

- Giá trị mục nhập liệt kê là bắt buộc

  - Và các phím chữ hoa phải được sử dụng

- Giá trị mục nhập liệt kê là tùy chọn và phải được đặt bên trong dấu ngoặc đơn
#### Các ví dụ:
##### Ví dụ cơ bản:
```js
enum Country {
  BELGIUM,
  FRANCE,
  ITALY
}
##### Và công dụng của nó:
```js
enum Country {}

entity A {
  country Country
}
```
##### Với các giá trị:
Bắt đầu từ JHipster Core v6, các giá trị enum có thể có các giá trị rõ ràng:
```js
enum Country {
  BELGIUM (Belgium),
  FRANCE (France),
  ITALY (Italy),
  CHINA ("中国")
}
```
##### Bình luận:
Cũng giống như các mối quan hệ, thực thể và trường, có thể nhận xét đối với enums, với các quy tắc tương tự.

Các bình luận sau đó sẽ được thêm vào dưới dạng bình luận Javadoc của JHipster. JDL sở hữu loại nhận xét riêng của nó:

- // một bình luận bị bỏ qua
- / ** không phải là một bình luận bị bỏ qua * /
Do đó, bất kỳ thứ gì bắt đầu bằng //đều được coi là nhận xét nội bộ cho JDL và sẽ không được tính là Javadoc. Xin lưu ý rằng các lệnh JDL Studio bắt đầu bằng #sẽ bị bỏ qua trong quá trình phân tích cú pháp.
```js
/** This comment will be taken into account */
enum Country {
  // But not this one!
  FRANCE
}
```

Liệt kê là loại có giá trị cố định:
```js
enum Type {
  A,
  B(b)
}

entity E {
  name Type
}
```
Lưu ý rằng các giá trị của kiểu liệt kê là tùy chọn.

Họ chỉ có một xác nhận `required:.`

### g)Thêm các mối quan hệ:
#### Các kiểu quan hệ:
Được đề cập sau relationshiptừ khóa.

Có bốn kiểu quan hệ:

- OneToOne
- OneToMany
- ManyToOne
- ManyToMany

Lưu ý về tên số nhiều: JHipster xử lý chúng để bạn không cần phải đặt tên trong các mối quan hệ của mình.

#### Các phương pháp quan hệ:
Được đề cập sau thực thể nguồn và đích, được sử dụng với withtừ khóa.

Các phương pháp được hỗ trợ:

- jpaDerivedIdentifier: @MapsIdđược sử dụng cho liên kết ( chỉ áp dụng cho OneToOne )

#### Nhiều cơ quan quan hệ:
Nếu bạn cảm thấy mệt mỏi với n mối quan hệ cùng loại trong tệp JDL của mình, đừng lo lắng! Có một giải pháp.

Lấy ví dụ mẫu JDL này:
```js
relationship OneToOne {
  A to B
}
relationship OneToOne {
  B to C
}
relationship OneToOne {
  C to D
}
relationship OneToOne {
  D to A
}
```
Giải pháp bao gồm việc đưa mọi phần thân của mối quan hệ vào bên trong khai báo mối quan hệ, như sau:
```js
relationship OneToOne {
  A to B,
  B to C,
  C to D,
  D to A
}
```
Cú pháp này thực sự hữu ích khi:

- Bạn có nhiều mối quan hệ cùng loại,
- Bạn muốn biết các mối quan hệ là gì,
- Bạn không muốn mất thời gian tìm kiếm chúng trong (các) tệp JDL của mình
#### Cú pháp:
Khai báo mối quan hệ được thực hiện như sau:
```js
relationship (OneToMany | ManyToOne | OneToOne | ManyToMany) {
  <from entity>[{<relationship name>[(<display field>)]}] to <to entity>[{<relationship name>[(<display field>)]}]+
}
```
- (OneToMany | ManyToOne| OneToOne | ManyToMany)là kiểu mối quan hệ của bạn,
- <from entity>là tên của chủ sở hữu thực thể của mối quan hệ: nguồn,
- <to entity>là tên của thực thể mà mối quan hệ đi đến: đích,
- <relationship name>là tên của trường có đầu kia là loại,
- <display field>là tên của trường sẽ hiển thị trong các hộp chọn (mặc định id:),
- requiredtrường được tiêm có được yêu cầu hay không.
- with jpaDerivedIdentifiercó @MapsIdđược sử dụng cho liên kết hay không (chỉ áp dụng cho một đối một)
- Và bạn có thể có nhiều hơn một cơ quan quan hệ
#### Các ví dụ:
##### Ví dụ cơ bản:
```js
relationship OneToOne {
  A to B
}
```
Lưu ý rằng ví dụ này giống như:
```js
relationship OneToOne {
  A{b} to B{a}
}
```
Không chỉ định trường được đưa vào là một dạng ngắn của việc có mối quan hệ hai chiều.

Một vi dụ khac:
```js
relationship OneToOne {
  A{b} to B
}
```
Điều này sẽ tạo ra một mối quan hệ một chiều. Bạn chỉ có thể tìm thấy thực thể B thông qua thực thể A, nhưng bạn không thể tìm thấy thực thể A thông qua thực thể B.

##### Với các trường được tiêm:
```js
relationship ManyToMany {
  A{b} to B{a}
}
```
Đây là mối quan hệ hai chiều, có nghĩa là cả hai thực thể sẽ được tạo với một “bản sao” của thực thể kia.

##### Với các phương pháp:
```js
relationship OneToOne {
  A to B with jpaDerivedIdentifier
}
```
##### Với các mặt được yêu cầu:
Được sử dụng để thực hiện ít nhất một bên quan hệ được yêu cầu.
```js
relationship ManyToMany {
  A{b required} to B{a}
}

// or

relationship ManyToMany {
  A{b} to B{a required}
}

or

relationship ManyToMany {
  A{b(name) required} to B{a required}
}
```
##### Các mối quan hệ phản xạ:
Mối quan hệ phản xạ là mối quan hệ có các thực thể nguồn và đích giống nhau.
```js
relationship ManyToMany {
  A{parent} to A{child}
}
```
Một lưu ý về các mối quan hệ phản xạ bắt buộc
Như đã lưu ý ở đây , các mối quan hệ bắt buộc với cùng một thực thể không được hỗ trợ. Vấn đề là một đứa trẻ phải luôn có cha mẹ, đến lượt nó cũng phải có cha mẹ, v.v. Một giải pháp khả thi là có các thực thể gốc và con rõ ràng.

#### Bình luận:
Có thể thêm nhận xét cho các mối quan hệ:
```js
relationship OneToOne {
  /** This comment will be put before b in entity A*/
  A{b}
  to
  /** This comment will be put before a in entity B*/
  B{a}
}
```
Các quy tắc bình luận tương tự được áp dụng ở đây. Những bình luận này sau đó sẽ được thêm vào dưới dạng bình luận Javadoc của JHipster. JDL sở hữu loại nhận xét riêng của nó:

- // một bình luận bị bỏ qua
- / ** không phải là một bình luận bị bỏ qua * /
Do đó, bất kỳ thứ gì bắt đầu bằng //đều được coi là nhận xét nội bộ cho JDL và sẽ không được tính là Javadoc. Xin lưu ý rằng các lệnh JDL Studio bắt đầu bằng #sẽ bị bỏ qua trong quá trình phân tích cú pháp.

Mối quan hệ giữa các thực thể cũng có sẵn và được khai báo bằng `relationship`từ khóa.
```js
entity A
entity B

relationship OneToOne {
  A{a} to B{b}
}
```
Đây là những gì chúng ta có thể thấy:

- OneToOnelà kiểu quan hệ

  - cũng có OneToMany, ManyToManyvàManyToOne

- chúng tôi khai báo nguồn và đích của mối quan hệ (từ Ađến B)
- chúng tôi cũng khai báo các trường được đưa vào trong mỗi thực thể ( atrong Bvà btrong A)
  - điều này có nghĩa là mối quan hệ là hai chiều

#### Mối quan hệ một chiều hay hai chiều:
Tùy thuộc vào cách bạn thiết kế mô hình của mình, bạn có thể muốn các mối quan hệ một chiều thay vì các mối quan hệ hai chiều. Điều này đạt được bằng cách không chỉ định một trường được đưa vào như thế này:
```js
relationship OneToOne {
  A{a} to B
}
```
Bạn cũng không thể chỉ định chúng và ít nhất một sẽ được đưa vào theo mặc định (nguồn)
```js
relationship OneToOne {
  A to B
}
```
#### Nhận xét và xác thực mối quan hệ:
Các mối quan hệ cũng có nhận xét, xác nhận (chỉ một `required`:):
```js
relationship OneToOne {
  A{a} to B{b required}
}
```
Trong ví dụ này, chúng ta có thể thấy:

- requiredđể chỉ định xem một bên của mối quan hệ có được yêu cầu hay không
  - thay vì có 0..1, mối quan hệ One to One này yêu cầu 1 bên không được là con số không

### h)Tùy chọn
Tương tự như cách bạn có thể áp dụng các tùy chọn cho các thực thể trong CLI, bạn cũng có thể làm điều đó trong JDL:
```js
entity A
entity B
entity C

readOnly A
dto * with mapstruct
service * with serviceImpl
paginate A, B with pager
```
Có một số điều thú vị đang xảy ra ở đây:

- dtopaginatevà là servicecác tùy chọn nhị phân vì chúng cần một danh sách thực thể và một giá trị
  - withđược sử dụng để chỉ định giá trị tùy chọn
  - lưu ý *điều đó có nghĩa là tùy chọn sẽ được áp dụng cho tất cả các thực thể
- readOnlylà một tùy chọn đơn nguyên, điều đó có nghĩa là các tùy chọn đó chỉ lấy một danh sách thực thể
Có nhiều cách để khai báo danh sách thực thể:

- bạn có thể liệt kê từng cái một:A, B, C
- bạn có thể chọn tất cả chúng: *hoặcall
  - bạn có thể có các ngoại lệ để loại trừ các thực thể:service * with serviceImpl except A, B
#### Chú thích:
Chú thích là một cách khác để khai báo các tùy chọn, hãy viết lại ví dụ trước:
```js
@readOnly
@dto(mapstruct)
@service(serviceImpl)
@paginate(pager)
entity A

@dto(mapstruct)
@service(serviceImpl)
@paginate(pager)
entity B

@dto(mapstruct)
@service(serviceImpl)
entity C
```
Tương tự như Java, hoặc Typescript, chú thích là "trình trang trí", các tùy chọn cho các thực thể.

Ví dụ này và ví dụ trước tương đương nhau vì chúng có thể được sử dụng để tạo cùng một mã.


### i)Triển khai:
Cuối cùng, các triển khai cũng có thể được tạo từ tệp JDL bằng `deployment`từ khóa, tương thích với JHipster v5.7 trở lên:
```js
deployment {
  deploymentType docker-compose
  appsFolders [foo, bar]
  dockerRepositoryName "yourDockerLoginName"
}
```
Để nhập một hoặc một số triển khai, bạn không cần phải ở trong thư mục ứng dụng JHipster.

Triển khai JHipster có cấu hình với các giá trị mặc định cho tất cả các thuộc tính khác và việc sử dụng cú pháp trước đó sẽ đảm bảo việc triển khai của bạn sẽ sử dụng các giá trị mặc định (như thể bạn không thực hiện bất kỳ lựa chọn cụ thể nào). Việc triển khai kết quả sẽ có:

- deployType:docker-compose
- ứng dụngfoo, bar
- dockerRepositoryName:yourDockerLoginName
- serviceDiscoveryType:eureka
- gatewayType:SpringCloudGateway
- directoryPath:../
- vân vân.

Bây giờ, nếu bạn muốn một số tùy chọn tùy chỉnh:
```js
deployment {
  deploymentType kubernetes
  appsFolders [store, invoice, notification, product]
  dockerRepositoryName "yourDockerLoginName"
  serviceDiscoveryType no
  istio autoInjection
  kubernetesServiceType Ingress
  kubernetesNamespace jhipster
  ingressDomain "jhipster.192.168.99.100.nip.io"
}
```


### j)Hằng số
JDL hỗ trợ các hằng số. Đây là một ví dụ:
```js
DEFAULT_MIN_LENGTH = 1
DEFAULT_MAX_LENGTH = 42
DEFAULT_MIN_BYTES = 20
DEFAULT_MAX_BYTES = 40
DEFAULT_MIN = 0
DEFAULT_MAX = 41

entity A {
  name String minlength(DEFAULT_MIN_LENGTH) maxlength(DEFAULT_MAX_LENGTH)
  content TextBlob required
  count Integer min(DEFAULT_MIN) max(DEFAULT_MAX)
}
```
### k)Xuất sang tệp JDL:
Nếu bạn đã có các thực thể trong ứng dụng của mình và muốn có tệp JDL, đừng lo lắng! Bạn không cần phải viết nó từ đầu vì có một trình tạo phụ làm điều đó cho bạn.

Chạy jhipster export-jdl <FILE_NAME>trong thư mục gốc của ứng dụng và bạn sẽ có tất cả các ứng dụng, thực thể, mối quan hệ và tùy chọn xuất trong một tệp JDL duy nhất.

Lưu ý: bạn cũng không thể cung cấp tên tệp cho trình tạo phụ, tệp JDL được xuất sẽ được đặt theo tên cơ sở của ứng dụng. Ví dụ: nếu ứng dụng của bạn có tên là 'mySuperApp' thì tệp JDL của bạn sẽ là mySuperApp.jdl.