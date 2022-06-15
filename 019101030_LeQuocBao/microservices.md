# BÀI BÁO CÁO

## 2.0 GIỚI THIỆU VỀ MICRISERVICES

## 2.1 Microservices là gì?
Microservices là tên gọi của các dịch vụ nhỏ thuộc dạng tách biệt đại diện cho 1 phần nhỏ tương ứng bên trong các Business domain của lập trình viên. Với kiến thức Monolithic thì bạn sẽ sở hữu một server lớn với khả năng chịu mọi trách nhiệm giải quyết hầu hết các requests. Và việc này sẽ gây ra khá nhiều khó khăn trên các phương tiện đối với tất cả requests. 

## 2.2 Kiến trúc Microservices

Khác biệt với kiến trúc Monolith, hay vì gom tất cả module thành một khối (monolith), ta tách các module thành những service siêu nhỏ. Mỗi service sẽ được đặt trên một server riêng (Có thể dùng server cloud như AWS hoặc Azure), giao tiếp với nhau thông qua mạng (Gửi nhận message qua giao thức HTTP hoặc sử dụng MessageQueue)...

## 2.3 Và một phần mềm xây dựng theo kiến trúc Microservices trông sẽ như nào?

Còn hình dưới sẽ minh họa việc ứng dụng ở trên khi được xây dựng theo kiến trúc Microservices

![Mosaic of Pluto in true color](https://images.viblo.asia/77613fcb-3b84-4de7-a463-d10a85eee9db.png)

## 2.4Các ưu điểm của Kiến trúc Microservices với các kiến trúc khác

Hiện nay, các ứng dụng thường rất lớn và liên tục được update ví dụ như facebook, linkin,... . Với kiến trúc monolith, việc gom toàn bộ ứng dụng vào một khối làm việc nâng cấp trở nên khó khăn và mất thời gian. Để giải quyết vấn đề đó, các ứng dụng lớn cần thiết được tách ra thành các service nhỏ. Mỗi service quản lý một cơ sở dữ liệu riêng, nằm trên một server riêng, tách biệt hoàn toàn với nhau. Các ưu điểm như sau:

- Điều quan trọng nhất là rất dễ nâng cấp và scale up, scale down. Giả sử bạn làm một trang web liên quan tới vận tải, kho bãi. Khi số lượng xe hay hàng hóa tăng lên, chỉ việc nâng cấp server cho service liên quan đến nghiệp vụ kho vận(ngược lại, có thể giảm server nếu cần thiết). Với cloud computing, việc nâng cấp server vô cùng dễ dàng chỉ với vài cú click chuột. Điều này rất khó thực hiện với monolith.

- Do tách biệt nên nếu một service bị lỗi, toàn bộ hệ thống vẫn hoạt động bình thường. Với monolith, một module bị lỗi có thể sẽ kéo sập toàn bộ hệ thống.

- Các service nằm tách biệt nhau, chúng có thể được sử dụng các ngôn ngữ lập trình riêng, database riêng. VD service xử lý ảnh có thể viết bằng C++, service tổng hợp data có thể viết bằng Python.

- Có thể áp dụng được các quy trình tự động hóa, như build, deploy, monitoring,...

- Khi chia nhỏ các service, team size sẽ giảm và mọi người sẽ làm việc hiệu quả hơn

- Về tính bảo mật nó sẽ có độ an toàn cao hơn bởi vì mỗi feature nằm ở từng service riêng biệt và mỗi service có cơ chế bảo mật riêng và khác nhau. nên sẽ rất khó sâm nhập vào hết được

