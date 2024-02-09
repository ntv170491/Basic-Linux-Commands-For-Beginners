# Lệnh Touch Linux

*Hướng dẫn cách dùng và các ví dụ sử dụng*

Lệnh `touch` Linux được dùng để tạo file trống, đổi `timestampts` của files và folders.

Thông tin `timestamps` chứa 3 attribute - thời gian truy cập, thời gian sửa file,i và thời gian thay đổi.

Hướng dẫn này sẽ giải thích cách dùng Linux `touch`, options của nó và cách dùng bằng ví dụ cụ thể.

## Timestamps Linux là gì?

Trong Linux, mỗi file và folders đều có timestamps (dấu thời gian) cung cấp thông tin liên quan đến thời gian của file.

Có 3 loại `timestamps` bên dưới:

- Access time `atime`- thời gian lần cuối file được đọc
- Modification time `mtime` - thời gian của file được chỉnh sửa. Giống với access time nó cũng là attribute của file.
- Changed time `ctime` - lần cuối metadata của file bị thay đổi (như là, quyền file).

Vì `atime` và `mtime` là một phần của status metadata của file, thay đổi `atime` hoặc `mtime` của file sẽ dẫn đến `ctime` tự động đặt thời gian vào thời điểm hiện tại.

Không có cách thay đổi `ctime` thủ công.

Lệnh linux touch command được dùng chủ yếu để thay đổi thời gian truy cập và thời gian được sửa của file cho một số các mục đích bên dưới.

Để sử dụng lệnh `touch` Linux, bạn có thể cần truy cập `VPS hosting` thông qua `SSH`!

## Cú pháp lệnh `touch` Linux

```
touch [options] [file_name]
```

Danh sách bên dưới là một số ví dụ cách dùng của Linux touch command

### Tạo một file sử dụng `touch`

Lệnh `touch` mà không có option nào sẽ tạo một file.\

Nếu file đã tồn tại, lệnh touch sẽ cập nhật thời gian truy cạp và chỉnh sửa đến thời gian hiện tại mà không thay đổi nội dung của nó:

```
touch file_name.txt
```

### Tạo nhiều file cùng lúc bằng `touch` linux

Bạn cũng có thể tạo nhiều file bằng một lệnh `touch` duy nhất.

Để làm vậy, hãy xác định tên file và khoảng trống giữa chúng.

Lệnh cần được viết tương tự như sau:

```
touch file_name1.txt file_name2.txt file_name3.txt
```

Bạn cũng có thể tạo file bằng dấu `ngoặc nhọn {..}` để tạo nhiều file như sau:

```
touch file_name {1..3}.txt
```
Lệnh `touch` command ở trên sẽ tạo 3 file có tên là `file_name1.txt`, `file_name2.txt`, và `file_name3.txt`.

### Đổi thời gian truy cập bằng `touch`

Để thay đổi thời gian truy cập của file tới thời điểm hiện tại, sử dụng option `-a` trước tên file bằng lệnh `touch` linux như sau:

```
touch -a file_name.txt
```

### Đổi thời gian chỉnh sửa file bằng lệnh `touch`

Tuỳ chọn `-m` sẽ thay đổi thời gian chỉnh sửa file tới thời gian hiện hành:

```
touch -m file_name1.txt
```

### Đổi thời gian truy cập và chỉnh sửa bằng lệnh `touch`

Để thay đổi cả thời gian truy cập và thời gian chỉnh sửa bằng một lệnh duy nhất thì bạn dùng cả 2 optioh `a` và `m`:

```
touch -am file_name1.txt
```

### Đổi Access Time mà không phải tạo file mới

Trong vài tình huống, nếu bạn muốn đổi thời gian truy cập và chỉnh sửa của file đã tồn tại tới thời gian hiện hành mà không tạo file, vậy bạn cần dùng option `c` trước tên file.

```
touch -c file_name.txt
```

### Đặt thời gian nhất định cho thời gian truy cập và chỉnh sửa bằng lệnh `touch`

Bạn cũng có thể đặt thời gian truy cập và chỉnh sửa đến một ngày giờ nhất định bằng option `t`, tiếp sau là ngày giờ, nó sẽ như sau:

```
touch -t 2201903081047.30 file_name.txt
```

Cấu trúc ngày giờ phải đúng là `CCYYMMDDhhmm.ss`, theo mô tả sau:

- CC - 2 số đầu của năm
- YY - 2 số cuối của năm
- MM - tháng trong năm `[01-12]`
- DD - ngày trong tháng `[01-31]`
- hh - giờ của ngày `[00-23]`
- mm - phút `[00-59]`
- ss - giây `[00-59]`

### Thay đổi timestamps của symbolic linked file

Khi bạn sử dụng một `symbolic link file` bằng lệnh Linux `touch` command, timestamps cho file gốc sẽ được thay đổi. Để thay đổi thời gian truy cập và thời gian chỉnh sửa tới thời gian hiện hành cho symbolic link file thôi thì dùng option `h`:

```
touch -h symbolic_link_file
```

### Đặt Timestamp bằng cách dùng file khác làm tham chiếu

Lệnh Linũ `touch` cũng có thể thiết lập thời gian access và modify bằng cách dùng timestamp của một file khác.

Ví dụ, lệnh `touch` bên dưới có option `r` sẽ quét timestamp của file reference.txt và dùng nó đặt giá trị timestamp cho `file_name.txt`. Đây là ví dụ của lệnh này:

```
touch -r reference.txt file_name.txt
```
### Xác định ngày và giờ bằng chuỗi với lệnh `touch`

Bạn có thể đặt ngày giờ bằng chuỗi với optio `d`.

Cách dùng như sau, với thời gian ngày giờ đặt thành 00:00

```
touch -d '8 Mar' file_name.txt
```

Thay vì dùng ngày, bạn cũng có thể dùng thời gian làm chuỗi nhập vào cho timestamps, ngày sẽ được đặt thành ngày hiện tại:

```
touch -d '20:10' file_name.txt
```
