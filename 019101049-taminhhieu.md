# BÁO CÁO

# GIỚI THIỆU GIT

## GIT là gì?

 Là một hệ thống quản lý phiên bản phân tán(Distributed Version Control System-DVCS)ra đời vào năm 2005 và hiện được dùng rất phổ biến.So với các hệ thống quản lý phiên bản tập trung khi tất cả các mã nguồn và lịch sử thay đổi chỉ được lưu một nơi là máy chủ thì trong hệ thống phân tán, các máy không chỉ "check out" phiên bản mới nhất của các tập tin mà là sao chép(mirror)toàn bộ kho mã nguồn(repository).Như vậy, nếu như máy chủ ngừng hoạt động , thì bạn hoàn toàn có thể lấy kho chứa từ bắt kì máy khách nào để sao chép ngược trở lại máy chủ để khôi phục lại toàn bộ hệ thống.Mỗi checkout thực sự là một bản sao đầy đủ của tất cả dữ liệu của kho chưá từ máy chủ.

## GIT có tác dụng như thế nào?

1. Lưu lại lịch sử các version của bất kỳ thay đổi nào của dự án. Giúp xem lại các sự thay đổi hoặc khôi phục (revert) lại sau này.

2. Việc chia sẻ code trở nên dễ dàng hơn, lập trình viên có thể để public cho bất kỳ ai, hoặc private chỉ cho một số người có thẩm quyền có thể truy cập và lấy code về.

Vốn là một VCS nên Git cũng ghi nhớ lại toàn bộ lịch sử thay đổi của source code trong dự án. Lập trình sửa file, thêm dòng code tại đâu, xóa dòng code ở hàng nào…đều được Git ghi nhận và lưu trữ lại.

## GIT hoạt động như thế nào?

Sự khác biệt chính giữa Git và bất kỳ VCS nào khác (bao gồm Subversion…) là cách Git nghĩ về dữ liệu của nó.

Về mặt khái niệm, hầu hết các hệ thống khác đều lưu trữ thông tin dưới dạng danh sách các thay đổi dựa trên file. Các hệ thống này (CVS, Subversion, Perforce, Bazaar, v.v.) coi thông tin chúng lưu giữ dưới dạng một tập hợp các file và những thay đổi được thực hiện đối với mỗi file theo thời gian.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173315605-66111018-514a-482e-ba2a-d06e81973cad.png)

## Ưu điểm của GIT là:

- Dễ sử dụng, thao tác nhanh, gọn, lẹ và rất an toàn.

- Sẽ dàng kết hợp các phân nhánh (branch), có thể giúp quy trình làm việc code theo nhóm đơn giản hơn rất nhiều.

- Chỉ cần clone mã nguồn từ kho chứa hoặc clone một phiên bản thay đổi nào đó từ kho chứa, hoặc một nhánh nào đó từ kho chứa là bạn có thể làm việc ở mọi lúc mọi nơi.

- Deployment sản phẩm của bạn một cách không thể nào dễ dàng hơn.

## Hạn chế của GIT là:

- Thuật toán SHA1 sự va chạm giá trị băm làm cho các pc thông thường làm hư hỏng một kho git.

- Sử dụng GIT trên hệ điều hành Microsoft Windows hơi phức tạp.

- Các tập tin không liên quan mà luôn luôn bị thay đổi, Git có thể chịu thiệt thòi hơn các hệ thống khác bởi vì các tập tin không được giữ dấu viết từng cái riêng lẻ.

## Các thuật ngữ GIT quan trọng là:

- Branch - Commit - Checkout - Fetch - Fork - Head - Index - Master - Merge - Origin - Pull - Push - Rebase - Remote - Repository - Stash - Tags - Upstream

## Các lệnh GIT cơ bản là:
1. git config

Tác dụng : Để set user name và email của bạn trong main configuration file.

Cách xài : Để kiểm tra tên và kiểu email trong cấu hình dùng git config -- global user.name và git config -- global user.email. Để set email hoặc tên mới git config -- global user.name = “Hải Nguyễn” và git config -- global user.email = “hainguyen@gmail.com”

2. git init

Tác dụng : Khởi tạo 1 git repository 1 project mới hoặc đã có.

Cách xài: git init trong thư mục gốc của dự án.

3. git clone

Tác dụng: Copy 1 git repository từ remote source.

Cách xài: git clone <:clone git url:>

4. git status

Tác dụng: Để check trạng thái của những file bạn đã thay đổi trong thư mục làm việc. VD: Tất cả các thay đổi cuối cùng từ lần commit cuối cùng.

Cách xài: git status trong thư mục làm việc.

5. git add

Tác dụng: Thêm thay đổi đến stage/index trong thư mục làm việc.

Cách xài: git add

6. git commit

Tác dụng: commit nghĩa là một action để Git lưu lại một snapshot của các sự thay đổi trong thư mục làm việc. Và các tập tin, thư mục được thay đổi đã phải nằm trong Staging Area. Mỗi lần commit nó sẽ được lưu lại lịch sử chỉnh sửa của code kèm theo tên và địa chỉ email của người commit. Ngoài ra trong Git bạn cũng có thể khôi phục lại tập tin trong lịch sử commit của nó để chia cho một branch khác, vì vậy bạn sẽ dễ dàng khôi phục lại các thay đổi trước đó.

Cách dùng: git commit -m ”Đây là message, bạn dùng để note những thay đổi để sau này dễ dò lại”

7. git push/ git pull

Tác dụng: Push hoặc Pull các thay đổi đến remote. Nếu bạn đã added và committed các thay đổi và bạn muốn đẩy nó lên hoặc remote của bạn đã update và bạn apply tất cả thay đổi đó trên code của mình.

Cách dùng: git pull <:remote:> <:branch:> and git push <:remote:> <:branch:>

8. git branch

Tác dụng: liệt kê tất cả các branch (nhánh).

Cách dùng: git branch hoặc git branch -a

9. git checkout

Tác dụng: Chuyển sang branch khác

Cách dùng: git checkout <: branch:> hoặc ** _ git checkout -b <: branch:> nếu bạn muốn tạo và chuyển sang một chi nhánh mới.

10. git stash

Tác dụng: Lưu thay đổi mà bạn không muốn commit ngay lập tức.

Cách dùng: git stash trong thư mục làm việc của bạn.

11. git merge

Tác dụng: Merge 2 branch lại với nahu.

Cách dùng: Chuyển tới branch bạn muốn merge rồi  dùng git merge <:branch_ban_muon_merge:>

12. git reset

Tác dụng: Bạn đã đưa một tập tin nào đó vào Staging Area nhưng bây giờ bạn muốn loại bỏ nó ra khỏi đây để không phải bị commit theo.

Cách dùng: git reset HEAD tên_file

13. git remote

Tác dụng: Để check remote/source bạn có hoặc add thêm remote

Cách dùng: git remote để kiểm tra và liệt kê. Và git remote add <: remote_url:> để thêm.

14. git add

Tác dụng: Để đưa một tập tin vào Staging Area

Cách dùng: git add tên_file hoặc muốn thêm hết file của thư mục thì git add all

## So sánh GIT và các phần mềm khác
Đây là điểm khác biệt quan trọng giữa Git và gần như tất cả các VCS khác. Nó khiến Git phải xem xét lại hầu hết mọi khía cạnh của kiểm soát phiên bản mà hầu hết các hệ thống khác đã sao chép từ thế hệ trước. Điều này làm cho Git giống như một hệ thống tệp nhỏ với một số công cụ cực kỳ mạnh mẽ được xây dựng trên nó, thay vì chỉ đơn giản là một VCS.
## Khi sử dụng GIT

- Lưu lại được các phiên bản khác nhau của mã nguồn dự án phần mềm.

- Khôi phục lại mã nguồn từ 1 phiên bản bất kỳ.

- Dễ dàng so sánh của các phiên bản.

- Phát hiện được ai đã sửa phần nào làm phát sinh lỗi.

- Khôi phục lại tập tin bị mất.

- Dễ dàng thử nghiệm, mở rộng tính năng của dự án mà không làm ảnh hưởng đến phiên bản chính (master branch).

- Giúp phối hợp thực hiện dự án trong một nhóm 1 cách hiệu quả.

## Khi không sử dụng GIT

- Không khôi phục được mã code lỡ xóa gây ra lỗi.

- Không quản lý được những người đã sửa code làm phát sinh lỗi

- Không khôi phục được tập tin đã bị mất.

- Khả năng phối hợp dự án trong nhóm bị hạn chế.

## Cách sử dụng GIT

1. Tạo tài khoản GitHub

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173311849-7d286b02-3547-407d-a44a-b53d2495219f.png)

Để tạo tài khoản của bạn, bạn cần truy cập trang web của GitHub và điền vào mẫu đăng ký.

2. Cài đặt Git

Bây giờ chúng ta cần cài đặt các công cụ của Git trên máy tính. Chúng ta sẽ sử dụng CLI để liên lạc với GitHub.

Đối với Ubuntu:

Đầu tiên, cập nhật các gói của bạn.
- sudo apt update

Tiếp theo, cài đặt Git và GitHub với apt-get
- sudo apt-get install git

Cuối cùng, xác minh rằng Git đã được cài đặt đúng
- git –version

Chạy các lệnh sau với thông tin của bạn để đặt tên người dùng và email mặc định khi bạn sẽ lưu công việc của mình.

- git config –global user.name “MV Thanoshan”

- git config –global user.email “example@mail.com”

3. Sử dụng Git theo hai cách

_Cách thứ 1: Tạo kho lưu trữ, sao chép nó vào pc của bạn và làm việc với nó.

Tạo một kho lưu trữ mới bằng cách nhấp vào nút Kho lưu trữ mới của Wikipedia trên trang web GitHub.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173312121-da4ea5a0-24ff-43d0-9941-954f247d446d.png)

Chọn tên cho kho lưu trữ đầu tiên của bạn, thêm một mô tả nhỏ, đánh dấu vào ô ‘Khởi tạo kho lưu trữ này với README’ và nhấp vào nút Tạo kho lưu trữ.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173312279-72bcd828-7ad6-4e1d-a339-b8bf801a04d0.png)

Kho GitHub đầu tiên của bạn được tạo.

Nhiệm vụ đầu tiên của bạn là lấy một bản sao của kho lưu trữ vào máy tính của mình. Để làm được điều đó, bạn cần phải sao chép lại kho lưu trữ trên máy tính của bạn.

Để sao chép một kho lưu trữ có nghĩa là bạn đang lấy một kho lưu trữ trên máy chủ và sao chép nó vào máy tính của bạn – giống như tải xuống. Trên trang kho lưu trữ, bạn cần lấy địa chỉ HTTPS.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173312470-1204e5b4-324c-4c3c-9177-e0bb07166734.png)

Khi bạn có địa chỉ của kho lưu trữ, bạn cần sử dụng terminal của mình. Sử dụng lệnh sau trên terminal của bạn. Khi bạn đã sẵn sàng, bạn có thể nhập lệnh này:

- git clone [HTTPS ADDRESS]

Lệnh này sẽ tạo một bản sao cục bộ của kho lưu trữ tại địa chỉ đã cho.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173314285-4c3091bc-4070-41d4-95ef-7be64fd44910.png)

Thông báo đầu ra của lệnh git clone bản sao

Bây giờ, kho lưu trữ của bạn là trên máy tính của bạn. Bạn cần di chuyển trong nó bằng lệnh sau.

- cd [NAME OF REPOSITORY]

Như bạn có thể thấy trong hình trên, tên kho lưu trữ của tôi là tên My- GitHub-Project, và lệnh này đã đưa tôi đến thư mục cụ thể đó.

*LƯU Ý: Khi bạn sao chép, Git sẽ tạo một kho lưu trữ trên máy tính của bạn. Nếu bạn muốn, bạn có thể truy cập dự án của mình bằng giao diện người dùng máy tính thay vì sử dụng lệnh ‘cd’ trên terminal.

Bây giờ, trong thư mục đó, chúng ta có thể tạo các tệp, làm việc với chúng và lưu chúng cục bộ. Để lưu chúng ở một nơi xa xôi – như GitHub – chúng ta đã thực hiện một quy trình gọi là commit. Để làm điều này, quay trở lại terminal của bạn. Nếu bạn đã đóng nó, như tôi đã nói trước đây, hãy sử dụng lệnh ‘cd’.

- cd [NAME OF REPOSITORY]

Bây giờ, trong terminal, bạn đang ở trong thư mục kho lưu trữ của bạn. Có 4 bước trong một commit: ‘status’, ‘add’, ‘commit’ và ‘push’. Tất cả các bước sau đây phải được thực hiện trong dự án của bạn. Chúng ta hãy đi qua từng cái một.

‘status’: Điều đầu tiên bạn cần làm là kiểm tra các tập tin bạn đã sửa đổi. Để làm điều này, bạn có thể gõ lệnh sau để làm cho một danh sách các thay đổi xuất hiện.

- git status

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173314394-3f9665ca-eaa4-4a36-b723-1434985bc2f7.png)

‘add’: Với sự trợ giúp của danh sách thay đổi, bạn có thể thêm tất cả các tệp bạn muốn tải lên bằng lệnh sau,

- git add [FILENAME] [FILENAME] […]

Trong trường hợp của chúng ta, chúng ta sẽ thêm một tệp HTML đơn giản.

- git add sample.html

‘commit’: Bây giờ chúng ta đã thêm các tệp mà chúng ta chọn, chúng ta cần viết một thông điệp để giải thích những gì chúng ta đã làm. Thông báo này có thể hữu ích sau này nếu chúng ta muốn kiểm tra lịch sử thay đổi. Dưới đây là một ví dụ về những gì chúng ta có thể đặt trong trường hợp của chúng ta.

- git commit -m “Added sample HTML file that contain basic syntax”

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173314466-a25831b8-6ffd-4ac6-b2f4-c281cd16c8dc.png)

‘push’: Để làm điều đó, chúng ta phải ‘đẩy’ các tệp của mình lên Remote. Remote là một bản sao trùng lặp của kho lưu trữ ở một nơi khác trên máy chủ từ xa. Để làm điều này, chúng ta phải biết tên của Remote (Chủ yếu là từ xa được đặt tên gốc). Để tìm ra tên đó, gõ lệnh sau.

- git remote

Như bạn có thể thấy trong hình trên, nó nói rằng tên từ là origin. Bây giờ chúng ta có thể ‘đẩy’ công việc của mình một cách an toàn bằng lệnh sau.

- git push origin master

Bây giờ, nếu chúng ta truy cập kho lưu trữ của mình trên trang web GitHub, chúng ta có thể thấy tệp sample.html mà chúng ta đã đẩy đến từ xa – GitHub!

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173312470-1204e5b4-324c-4c3c-9177-e0bb07166734.png)

*LƯU Ý : Đôi khi, khi bạn đang sử dụng các lệnh Git trong terminal, nó có thể dẫn bạn đến trình soạn thảo văn bản VIM (trình soạn thảo văn bản dựa trên CLI). Vì vậy, để thoát khỏi nó, bạn phải gõ

- :q

và ENTER.

Mô tả cách pull và push làm việc:

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173314720-36352134-acfd-4d8d-bb88-a9086a1a4474.png)

Pull là hành động nhận từ GitHub.

Push là hành động gửi đến GitHub.

_Cách thứ 2: Làm việc trên dự án của bạn cục bộ sau đó tạo kho lưu trữ trên github và đẩy nó vào remote.

Loại 2 cho phép bạn tạo một kho lưu trữ mới từ một thư mục hiện có trên máy tính và gửi nó đến GitHub. Trong rất nhiều trường hợp, bạn có thể đã thực sự tạo ra một cái gì đó trên máy tính mà bạn muốn đột nhiên biến thành một kho lưu trữ trên GitHub.

khi thực hiện bất kỳ lệnh Git nào, chúng ta phải đảm bảo rằng chúng ta đang ở đúng thư mục trong terminal.

Theo mặc định, bất kỳ thư mục nào trên máy tính không phải là kho lưu trữ Git – nhưng chúng ta có thể biến nó thành kho lưu trữ Git bằng cách thực hiện lệnh sau trong terminal.

- git init

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173314840-f64fce8b-75cc-42bb-bd9f-3e40889e85bd.png)

Sau khi chuyển đổi thư mục của chúng ta sang kho lưu trữ Git, điều đầu tiên chúng ta cần làm là kiểm tra các tệp chúng ta có bằng cách sử dụng lệnh sau.

- git status

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173314953-09ded956-8592-4059-b9f2-1e3d3c79e9f0.png)

Vì vậy, có hai tập tin trong thư mục đó mà chúng ta cần để thêm vào Repo của chúng ta.

- git add [FILENAME] [FILENAME] […]

*LƯU Ý: Để thêm vào tất cả các tệp trong Kho lưu trữ của chúng ta, chúng ta có thể sử dụng lệnh sau:

- git add .

Sau khi khu vực tổ chức (quá trình thêm) hoàn tất, chúng ta có thể kiểm tra xem các tệp có được thêm thành công hay không bằng cách thực hiện git status

Nếu những tệp cụ thể đó có màu xanh lục như hình dưới đây, bạn đã hoàn thành công việc của mình!

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173315080-cc952a08-b46f-497c-9d76-614af3f94fab.png)

Sau đó, chúng ta phải commit với một mô tả trong đó.

- git commit -m “Adding web Survey form”

Nếu kho lưu trữ của tôi bắt đầu trên GitHub và tôi đã đưa nó xuống máy tính của mình, một Remote đã được gắn vào nó (Loại 1). Nhưng nếu tôi đang khởi động kho lưu trữ của mình trên máy tính thì nó không có Remote, vì vậy tôi cần thêm Remote đó (Loại 2).

Vì vậy, để thêm Remote, chúng ta phải vào GitHub trước. Tạo một kho lưu trữ mới và đặt tên cho nó bất cứ điều gì bạn muốn lưu trữ trong GitHub. Sau đó nhấp vào nút Tạo kho lưu trữ.

*LƯU Ý: Trong Loại 2, Vui lòng không khởi tạo kho lưu trữ với tệp README khi tạo kho lưu trữ mới trên trang web GitHub.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173312279-72bcd828-7ad6-4e1d-a339-b8bf801a04d0.png)

Sau khi nhấp vào nút Tạo kho lưu trữ, bạn sẽ tìm thấy dạng trang web.

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173313680-0926ac3f-ab44-43cd-a21c-83769318aefb.png)

Sao chép địa chỉ HTTPS. Bây giờ chúng ta sẽ tạo Remote cho kho lưu trữ của mình.

- git remote add origin [HTTPS ADDRESS]

Sau khi thực hiện lệnh này, chúng ta có thể kiểm tra xem chúng ta đã thêm thành công Remote hay chưa bằng lệnh sau

- git remote

Và nếu nó xuất ra Origin thì bạn đã thêm Remote vào dự án của mình.

*LƯU Ý: Chỉ cần nhớ rằng chúng ta có thể nêu bất kỳ tên nào cho Remote bằng cách thay đổi tên xuất xứ. Ví dụ:

- git remote add [REMOTE NAME] [HTTPS ADDRESS]

Bây giờ, chúng ta có thể đẩy dự án của mình lên GitHub mà không gặp vấn đề gì!

- git push origin master

Sau khi hoàn thành từng bước một, nếu bạn truy cập GitHub, bạn có thể tìm thấy kho lưu trữ của mình với các tệp!

![Mosaic of Pluto in true color](https://user-images.githubusercontent.com/107382675/173312470-1204e5b4-324c-4c3c-9177-e0bb07166734.png)

## MICROSERVICES là gì

 - Microservices là tên gọi của các dịch vụ nhỏ thuộc dạng tách biệt đại diện cho 1 phần nhỏ tương ứng bên trong các Business domain của lập trình viên. Với kiến thức Monolithic thì bạn sẽ sở hữu một server lớn với khả năng chịu mọi trách nhiệm giải quyết hầu hết các requests. Và việc này sẽ gây ra khá nhiều khó khăn trên các phương tiện đối với tất cả requests.

- Microservices được xem như giải pháp có thể cân bằng được tất cả các traffic dựa theo yêu cầu của doanh nghiệp. Và nếu như bạn đang nhận một lượng lớn các thanh toán thì hầu hết bạn sẽ có thể scale up thiết bị thanh toán và giữ cho các dịch vụ nằm ở mức sử dụng 1 lượng nhỏ hơn so với các services.

## Kiến trúc của Microservices là gì?

- Kiến trúc

    Bên trong kiến trúc của Microservices thì các services sẽ tồn tại độc lập nhau về xử lý, lưu trữ và cả request.

![image](https://user-images.githubusercontent.com/107390677/173483350-2650661b-9640-4d2e-88e3-6f1561075c96.png)

- Tính chất của khối Monolithic ảnh hưởng đến cấu trúc Microservices

    - Được thiết kế, phát triển và triển khai dựa theo một khối duy nhất.

    - Các ứng dụng monolithic rất phức tạp và nó sẽ gây ra nhiều khó khăn cho quá trình nâng cấp, bảo trì hoặc thêm các tính năng mới. 

    - Thường rất khó để có thể áp dụng triển khai dựa theo kiểu agile.

    - Bạn cần phải triển khai lại toàn bộ một hệ thống mặc dù chỉ phải cập nhật hoặc nâng cấp một phần duy nhất. 

    - Mở rộng được các khối ứng dụng nếu như gặp khó khăn thì sẽ có các yêu cầu về những tài nguyên khác nhau. 
    
    - Một service thường không có độ ổn định nên có thể làm sập cả hệ thống.

    - Khó đổi mới: Bởi vì ứng dụng monolithic cần phải sử dụng chung một công nghệ vì vậy nó rất khó có thể thay đổi hoặc áp dụng thêm các công nghệ mới. 

![image](https://user-images.githubusercontent.com/107390677/173483656-1c6d07f9-963a-4aff-a5ac-89dab67ee361.png)

## Ưu điểm và nhược điểm của Microservices

- Ưu điểm

    - Microservices cho phép dễ dàng continuous delivery và deployment các ứng dụng lớn và phức tạp hơn. 

    - Có thể cải thiện khả năng bảo trì: bởi vì các service tương đối nhỏ nên dễ hiểu và dễ thay đổi hơn. 
    - Có khả năng testing dễ dàng: nhờ các services nhỏ
    - Có thể triển khai tốt hơn: các services thường rất dễ cho việc triển khai độc lập. 
    - Cho phép các services được phát triển nhanh chóng bởi những team khác nhau. Khi đó, mỗi team đều sẽ được phát triển và thử nghiệm để triển khai cũng như mở rộng được quy mô của dịch vụ của mình một cách độc lập nhất với tất cả các team. 
    - Nếu như có lỗi xảy ra trong một service thì chỉ có service đó bị ảnh hưởng và các service khác sẽ thực hiện xử lý các yêu cầu cần thiết. Trong khi đó, thì mỗi một thành phần nếu như hoạt động sai của kiến trúc một khối thì nó sẽ làm ảnh hưởng đến toàn bộ hệ thống. 
    - Lập trình viên có thể thay đổi dễ dàng bằng cách sử dụng công nghệ mới khi triển khai các service. Tương tự như khi có thay đổi lớn thì các service đều có thể thực hiện và bạn dễ dàng thay đổi được công nghệ hơn.

- Nhược điểm
    - Bởi vì các nhà phát triển thường xuyên phải đối phó với sự phức tạp khi tạo ra một hệ thống phân tán. 
    - Cần phải implement việc communication giữa các inter-services
    - Handle partial failure rất phức tạp bởi vì luồng xử lý cần phải đi qua nhiều service khác nhau. 
    - Khi thực hiện các requests trải rộng trên nhiều service khó khăn thì điều này cần đòi hỏi sự phối hợp giữa các team. 
    - Thường rất khó khăn trong việc đảm bảo toàn vẹn cho CSDL nếu như triển khai theo các cấu trúc cơ sở dữ liệu dạng phân vùng. 
    - Việc triển khai và quản lý microservices nếu như làm thủ công theo cách làm với ứng dụng thì sẽ rất phức tạp.
    - Lập trình viên cần phải xử lý các sự cố kết nối chậm, lỗi nếu như thông điệp không được gửi hoặc nếu như thông điệp được gửi đến nhiều đích đến vào các thời điểm khác nhau. 
    ![image](https://user-images.githubusercontent.com/107390677/173484274-9e6c4159-a225-42d3-9f2c-4e59fef104d2.png)

## Các lợi ích Microservices mang lại

Microservices được sử dụng ngày càng phổ biến nhờ mang lại vô số lợi ích như: 
- Source code rất tinh gọn: Bởi vì hệ thống được cấu thành từ các dự án nhỏ, và mỗi dự án đều rất đơn giản cũng như tập trung vào 1 hoặc 1 vài nghiệp vụ chính. Vì vậy, các code base và độ phức tạp của chúng đều không cao. Nhờ vậy, nó sẽ giúp mang lại tính gọn nhẹ, dễ bảo trì cũng như mở rộng hơn. 
- Bảo mật tối ưu cho source code: Khi nhân viên làm việc ở các dự án thì chỉ truy cập được vào một source code của dự án đó. 
- Được tồn tại độc lập: Bởi vì đây là 4 dự án khác nhau và chúng có thể có cách deploy riêng biệt và một service nào đó chết thì các service khác vẫn sẽ hoạt động một cách bình thường. 
- Scale hoàn toàn độc lập: Tùy thuộc vào nhu cầu sử dụng của hệ thống mà bạn có thể scale riêng cho service đó. Có thể như service đơn hàng mà sử dụng thường xuyên nên chạy từ 2 đến 3 server để gia tăng performance. 

## Sử dụng Microservices hợp lý khi nào?

Với những thách thức đối với nhu cầu sử dụng Microservices thì bạn nên dùng cấu trúc này khi: 
Khi phát triển những phiên bản đầu tiên cho một ứng dụng, khi đó bạn thường không phải gặp những vấn đề mà Microservices cần phải giải quyết. Hơn nữa, việc sử dụng một kiến trúc phân tán hoặc phức tạp sẽ làm chậm đi quá trình phát triển của ứng dụng. 
Đây là một trong những vấn đề lớn đối với các start-up bởi vì họ buộc phải phát triển nhanh mô hình kinh doanh của mình cũng như ứng dụng kèm theo. Chính vì vậy, trừ khi bạn đã có một hệ thống phức tạp để quản lý bằng Monolithic hoặc bạn đã xác định được tương lai của ứng dụng sẽ ra sao; thì có thể dùng Microservices.

## Các sai lầm về Microservices

- Hiểu sai về Microservices

    - Một số dòng code/kích cỡ của một đội lập trình thường là chỉ số tồi.
    - Mico là một từ khóa dễ gây hiểu nhầm và bạn nghĩ rằng nên tạo ra services nhỏ hết mức thì đó là cách hiểu hoàn toàn sai. 
    - Services trở thành các cục monolithic với nhiều hàm, chức năng khác được hỗ trợ nhau. Chính vì thế, khi phát triển services kiểu SOA rồi dán nhãn Microservices hoàn toàn bị đánh lạc hướng và không mang lại bất kỳ lợi ích nào. 
    ![image](https://user-images.githubusercontent.com/107390677/173484985-16d291bd-fe50-44ea-beb5-9b94964da751.png)

- Những vấn đề cần tuân thủ

    - Một Service có phạm vi và chức năng giới hạn thì việc tập trung vào một nhiệm vụ sẽ giúp cho quá trình phát triển cũng như triển khai dịch vụ trở nên nhanh chóng hơn. 
    - Khi thiết kế, bạn nên xác định và giới hạn cho các service dựa theo chức năng nghiệp vụ thực tế. 
    - Hãy đảm bảo microservices có thể phát triển cũng như được triển khai độc lập. 
    - Mục tiêu thiết kế là đưa ra phạm vi cho một microservices phục cụ cho một nghiệp vụ chứ không đơn giản là làm những dịch vụ nhỏ hơn. Khi đó, kích thước hợp lý của một services đó chính là kích thước đủ để đáp ứng cho các yêu cầu của một chức năng bên trong hệ thống.
    - Khác biệt so với services trong SOA thì một microservice không nên có quá nhiều hàm hoặc chức năng hỗ trợ xung quanh cũng như định dạng thông báo gửi hoặc gửi tin đơn giản. 

 ## Sự khác nhau giữa kiến trúc Microservices và  kiến trúc API

API là các phương thức, giao thức kết nối với các thư viện và ứng dụng khác. Nó là viết tắt của Application Programming Interface – giao diện lập trình ứng dụng. API cung cấp khả năng cung cấp khả năng truy xuất đến một tập các hàm hay dùng. Và từ đó có thể trao đổi dữ liệu giữa các ứng dụng.

![image](https://user-images.githubusercontent.com/107390677/173485943-142467ef-5912-4e1b-8d44-20de81af4e54.png)
