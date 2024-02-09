# Cách thay đổi thư mục trong Linux bằng lệnh `cd`

Duyệt qua hệ thống là một trong những tác vụ cơ bản nhất mà người dùng có thể thực hiện trên hệ điều hành.

Mặc dù nhiều trình quản lý tệp có sẵn cho phép bạn chuyển đổi thư mục và điều hướng ổ đĩa của bạn theo cách đồ hoạ, nhưng làm điều này qua dòng lệnh có thể giúp bạn kiểm soát hệ thống của mình tốt hơn.

Linux cung cấp cho bạn một lệnh được gọi là `cd`, cho phép bạn dễ dàng thay đổi thư mục (directory) làm việc hiện tại trên terminal.

Đây là cách bạn có thể sử dụng lệnh `cd` trên Linux, tiện ích duy nhất mà bạn cần để duyệt qua các thư mục trên bộ nhớ hệ thống của mình.

# 1. Cách sử dụng lệnh `cd` trong Linux

Là một trong những lệnh cơ bản nhất trong Linux, lệnh cd là viết tắt của `Change Directory` (thay đổi thư mục).

## 1.1 Cú pháp cơ bản

Cú pháp cơ bản của lệnh cd là:

```
cd [options] [path]
```

... trong đó `options` là các đối số được truyền bằng lệnh và `path` là đường dẫn tuyệt đối (absolute path) hoặc tương đối (relative path) đến thư mục.

## 1.2 Tên đường dẫn tuyệt đối và tương đối

Trước khi bạn có thể sử dụng lệnh `cd`, bạn phải biết sự khác biệt giữa tên đường dẫn tuyệt đối và tương đối.

Tên đường dẫn dẫn *tuyệt đối* là đường dẫn đầy đủ đến thư mục, bắt đầu từ thư mục `/(root)`.

Mặt khác, tên đường dẫn *tương đối* có nguồn gốc từ thư mục làm việc hiện tại.

Bạn có thể di chuyển lên và xuống cây thư mục một cách hiệu quả bằng lệnh `cd` nếu bạn đã thông thạo các đường dẫn tương đối.

Ví dụ: nếu thư mục làm việc hiện tại của bạn là `/home` và bạn muốn thay đổi thư mục thành `/Desktop`, hãy sử dụng tên đường dẫn tuyệt đối:

```
cd /home/username/Desktop
```

Mặt khác, nếu bạn muốn chuyển sang thư mục `/Desktop` bằng đường dẫn tương đối, bạn cần gõ:
```
cd /Desktop
```

`cd` theo dõi những thư mục nào ở trên và dưới thư mục hiện tại, để cho phép người dùng nhanh chóng chuyển sang các thư mục khác mà không cần phải nhập toàn bộ tên đường dẫn.

Nếu bạn không biết tên chính xác của thư mục con mà bạn muốn chuyển sang, hãy sử dụng lệnh `ls` để liệt kê mọi thư mục trong thư mục đó.

## 1.3 Chuyển sang Thư mục chính

Trên hệ thống Linux, thư mục `/home` là một thư mục đặc biệt dành riêng cho các tệp, chương trình và thư mục con cá nhân của người dùng.

Khi bạn đăng nhập vào hệ thống của mình, thư mục chính được đặt làm thư mục làm việc hiện tại theo mặc định.

Thư mục chính có một ký tự đặc biệt được gán cho nó - ký tự `~` (dấu ngã). Thay vì chỉ định đường dẫn đầy đủ đến thư mục chính của bạn (`/home/username`), bạn có thể chỉ cần thêm ký tự `~` vào lệnh `cd` để thay đổi thư mục làm việc hiện tại thành `/home`.

```
cd ~
```

Tương tự, bạn có thể điều hướng đến thư mục chính của người dùng khác như sau:

```
cd ~username
```

Trong phần trước, chúng ta đã chuyển thư mục làm việc hiện tại thành `/Desktop`. 

Trong lệnh này, bạn có thể sử dụng ký tự `~` để biểu thị thư mục `/home` và rút ngắn độ dài của lệnh còn một nửa.

```
cd ~/Desktop
```

## 1.4 Điều hướng đến Thư mục gốc

Cũng giống như thư mục chính, ký tự `/` biểu thị thư mục `/root` trên hệ điều hành dựa trên Linux. Để chuyển sang thư mục gốc bất kỳ lúc nào:

```
cd /
```

## 1.5 Chuyển Thư mục làm việc trước đó

Nếu bạn đang làm việc với nhiều thư mục cùng một lúc, bạn có thể dễ dàng chuyển đổi qua lại thư mục làm việc trước đó bằng cách sử dụng ký tự `- (gạch nối)`.

Ví dụ, nếu thư mục làm việc hiện tại là `/home` và bạn chuyển thư mục `/root`. `/root` sẽ trở thành thư mục làm việc hiện tại và `/home` sẽ là thư mục làm việc trước đó.

Gõ lệnh sau sẽ đưa bạn đến thư mục trước đó, tức là `/home`.

```
cd -
```

Ngoài ra, việc phát hành lệnh `cd` theo sau là một ký tự `khoảng trắng` sẽ đưa người dùng đến thư mục làm việc trước đó.
```
cd [khoảng trắng]
```

## 1.6 Chuyển sang Thư mục gốc

Một thư mục bao gồm một hoặc nhiều thư mục con được gọi là thư mục mẹ.

Nói một cách đơn giản, nếu bạn có các thư mục `/Desktop` và `/Downloads` trong thư mục `/home`, thì thư mục `/home` sẽ là thư mục mẹ cho `/Desktop` và `/Downloads`.

Các ký tự `..` và `.` lần lượt là đại diện cho thư mục mẹ và thư mục hiện tại.

Sử dụng ký tự `dấu chấm đôi (..)` để chuyển sang thư mục mẹ.

```
cd ..
```

Lệnh nói trên sẽ đưa bạn lên một cấp trong cây thư mục. Bạn cũng có thể thêm nhiều ký tự `..` để di chuyển lên nhiều cấp trên cây thư mục.

Để di chuyển hai cấp trên thư mục làm việc hiện tại:

```
cd ../../
```

Bạn cũng có thể chuyển một thư mục cụ thể lên trên một cấp so với thư mục làm việc hiện tại.

```
cd ../Folder
```

## 1.7 Chuyển sang một thư mục tên có dấu cách

Không phải mọi thư mục trên hệ thống của bạn đều có tên là một từ.

Một số trong số chúng có thể bao gồm ký tự `khoảng trắng`.

Ví dụ: `/home/username/Important Documents`.

Trong những tình huống như vậy, việc chỉ định tên thư mục sẽ trả về một lỗi.

```
cd /Important Documents
```

Đầu ra:

```
bash: cd: too many arguments
```

Để chuyển sang các thư mục có khoảng trắng trong tên, hãy đặt tên đường dẫn trong `dấu ngoặc kép` như sau.

Lưu ý rằng bạn có thể sử dụng cả dấu nháy đơn và dấu hoặc kép  trong lệnh.

```
cd 'Important Documents'
```

```
cd "Important Documents"
```

Ngoài ra, bạn có thể sử dụng ký tự gạch chéo ngược `\`

```
cd Important\ Documents
```

# 2. Duyệt hệ thống thông qua dòng lệnh

Terminal Linux là một giao diện dưa trên văn bản mạnh mẽ để kiểm soát hoạt động của máy tính.

Bạn có thể thực hiện hầu hết mọi tác vụ bằng cách sử dụng dòng lệnh. `Thay đổi thư mục`, `sao chép tệp` và `thư mục từ xa`, l`iệt kê thông tin tệp`, `chỉnh sửa cấu hình`...

Có một lệnh cho mọi thứ bạn muốn thực hiện trên Linux.

Tuy nhiên, có một vấn đề là có quá nhiều lệnh. Nhưng là một người dùng Linux mới bắt đầu, bạn sẽ không sử dụng tất cả các tiện ích có sẵn trên hệ thống của mình.

Thay vào đó, học một số lệnh cơ bản sẽ giúp bạn thực hiện các thao tác cơ bản là quá đủ để bắt đầu với hệ điều hành Linux.

[9 lệnh cơ bản giúp bạn bắt đầu với Linux](https://funix.edu.vn/chia-se-kien-thuc/9-lenh-co-ban-giup-ban-bat-dau-voi-linux/).