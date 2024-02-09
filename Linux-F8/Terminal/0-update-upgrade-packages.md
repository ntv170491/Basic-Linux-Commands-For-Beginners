# Update, Upgrade Packages

2 câu lệnh được sử dụng trong bài học này:

~~~
sudo apt update
 
và

sudo apt upgrade
~~~

## Lệnh `apt-get` update

Lệnh sudo `apt-get` update được sử dụng để tải xuống thông tin gói từ tất cả các nguồn được cấu hình.

Các nguồn thường được xác định trong tệp **/etc/apt/sources.list** và các tệp khác nằm trong thư mục **/etc/apt/sources.list.d**.

Vì vậy, khi bạn chạy lệnh cập nhật, nó sẽ tải xuống thông tin gói từ Internet.

Sẽ rất hữu ích khi nhận thông tin về phiên bản cập nhật của các gói hoặc các gói phụ thuộc của chúng.

Cách xem tệp `/etc/apt/sources.líst`, gõ lệnh cat:
~~~
cat /etc/apt/source.list
~~~

Chạy lệnh `sudo apt-get update` để cập nhật package index.

Chỉ cần gõ lệnh `apt-get` hoặc lệnh `apt`:

~~~
sudo apt update

hoặc

sudo apt-get update
~~~
---

## Lệnh `apt-get upgrade`

1. Bây giờ bạn đã biết lệnh `sudo-get update` giúp bạn có một danh sách cập nhật các gói từ internet.
2. Nhưng, làm thế nào để bạn cài đặt các gói đã bị lỗi thời? Làm cách nào để áp dụng các bản vá bảo mật cho các gói và giữ an toàn cho hệ thống của bạn? Làm thế nào để bạn tìm thấy các gói mới để cài đặt.
3. Bạn chạy `sudo apt-get upgrade` để cài đặt các bản nâng cấp có sẵn của tất cả các gói hiện được cài đặt trên hệ thống từ các nguồn được cấu hình thông qua tệp `sources.list`.
4. Các gói mới sẽ được cài đặt nếu được yêu cầu để đáp ứng các phụ thuộc, nhưng các gói hiện có sẽ không bao giờ bị xoá.
   
---

## Sự khác biệt giữa cập nhật và lệnh nâng cấp.

### apt-get update:

Cập nhật được sử dụng để đồng bộ hoá lại các index file từ các nguồn của chúng.

Index của các gói có sẵn được tìm nạp từ (các) vị trí được chỉ định trong `/etc/apt/sources.list`.

Ví dụ, khi sử dụng kho lưu trữ Debian, lệnh này truy xuất và quét các tệp Packages.gz để có sẵn thông tin về các gói mới và cập nhật.

*Cập nhật phải luôn được thực hiện trước khi nâng cấp hoặc nâng cấp bản phân phối.*

**Xin lưu ý rằng** thanh đo tiến độ tổng thể sẽ không chính xác vì không thể biêt trước kích thước của tệp gói.

### apt-get upgrade:

Upgrade được sử dụng để cài đặt phiên bản mới nhất của tất cả các gói hiện được cài đặt trên hệ thống từ các nguồn được liệt kê trong `/etc/apt/sources.list`.

Các gói hiện được cài đặt với phiên bản mới có sẵn được truy xuất và nâng cấp;

Trong mọi trường hợp, các gói hiện đã được cài đặt bị xoá hoặc các gói chưa được cài đặt được truy xuất và cài đặt.

Phiên bản mới của các gói hiện được cài đặt không thể nâng cấp mà không thay đổi trạng thái cài đặt của gói khác sẽ được giữ nguyên ở phiên bản hiện tại của chúng.

**Update** phải được thực hiện trước tiên để `apt-get` biết rằng các phiên bản mới của gói có sẵn.

---

###

Câu lệnh tải xuống và cài đặt một package

~~~
sudo apt install [tên_package]
~~~

---

## Kết luận

Tóm lại, việc thực thi `sudo apt-get update` sẽ tìm nạp cho bạn danh sách các gói cho tất cả các kho lưu trữ và **PPA** của bạn và đảm bảo rằng nó được cập nhật.

Trong khi `sudo apt-get upgrade` thực hiện nâng cấp phần mềm thực tế. 

Do đó, tùy chọn được khuyến nghị là luôn chạy lệnh `update` trước lệnh `upgrade` để cập nhật các gói đã cài đặt cho hệ thống Ubuntu hoặc Debian:

~~~
sudo apt-get update && sudo apt-get upgrade
~~~

Chúng ta có thể chạy nhiều lệnh trong sudo như sau:

~~~
sudo sh -c 'apt update && apt upgrade'
~~~
