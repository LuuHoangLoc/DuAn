# 3.0 GIỚI THIỆU VỀ SPRING BOOT

## 3.1 Spring Boot là gì?

**Spring Boot** là một dự án phát triển bởi JAV (ngôn ngữ java) trong hệ sinh thái Spring framework. Nó giúp cho các lập trình viên chúng ta đơn giản hóa quá trình lập trình một ứng dụng với Spring, chỉ tập trung vào việc phát triển business cho ứng dụng, giúp giảm tải công việc cấu hình(configuration).

 **Spring Boot** chính là một Java framework siêu to và khổng lồ và có nhiều khả năng hữu ích vì nó có thể giúp lập trình viên giải quyết rất nhiều vấn đề. So với framework Spring thông thường, Spring Boot tỏ ra những lợi thế vượt trội. Khi sử dụng Spring Boot, rất nhiều thứ được cải tiến hỗ trợ lập trình viên như:

 - Auto config: tự động cấu hình thay lập trình viên, bạn chỉ cần viết code và tiến hành chạy hệ thống là được.
 - Dựa trên các Annotation để tạo lập các bean thay vì XML.
 - Server Tomcat có thể được nhúng ngay trong file JAR build ra và có thể chạy ở bất kì đâu mà java chạy được.

 Khi sử dụng **Spring Boot**, lập trình viên chỉ cần:
- Sử dụng Spring Initializr: nhập các thông tin của dự án (project), chọn thư viện (Library) rồi tải code về máy.
- Mở mã nguồn (source code) và bắt đầu viết code.
- Có thể chạy ngay trong IDE, hoặc build thành file JAR mà không cần cấu hình config cho server nữa.

## 3.2 Tại sao Spring Boot áp dụng trong microservice?

Vì Spring Boot tự động hóa thiết lập, nhúng máy chủ và đơn giản hóa việc quản lý phụ thuộc, nên rất dễ sử dụng kiến trúc microservice. Spring Boot cho phép các nhóm phát triển xây dựng dịch vụ một cách dễ dàng và hiệu quả vì quá trình thiết lập ban đầu và tải xuống các máy chủ hoặc gói ứng dụng cần thiết mất rất ít thời gian.