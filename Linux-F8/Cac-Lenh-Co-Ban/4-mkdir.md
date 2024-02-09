# Tạo thư mục với Lệnh `mkdir` - Make Directory

```
$ mkdir new-folder
```

## Xoá thư mục

```
$ rmdir new-folder/
```
# Tạo và xoá thư mục trong Linux Terminal

## 1. Tạo một thư mục duy nhất trên Linux

Đây là cách bạn có thể sử dụng hàm `mkdir` để tạo một thư mục:
```
mkdir [option] <directory name>
```
Ví dụ, nếu bạn muốn tạo một thư mục mới, bạn có thể sử dụng lệnh sau:

```
mkdir MUO
```

Lệnh trên tạo thư mục MUO mới trong vị trí hiện tại. Để điều hướng đến thư mục MUO thông qua dòng lệnh, bạn có thể sử dụng lệnh cd:

```
cd ./MUO
```

Lệnh `cd` là một cách linh hoạt để thay đổi các thư mục trong Linux terminal.

## 2. Tạo nhiều thư mục trên Linux

Hàm `mkdir` rất linh hoạt, cho phép bạn tạo nhiều thư mục chỉ bằng một lệnh.

Ví dụ, để tạo nhiều thư mục thông qua dòng lệnh, hãy sử dụng đoạn code bên dưới:

```
mkdir <directory name1><directory name2><directory name3>....<directory name_n>
```

Để tạo 3 thư mục, đây là cách bạn có thể sử dụng lệnh `mkdir`:

```
mkdir MUO_sample1 MUO_sample2 MUO_sample3
```

Khi bạn chạy lệnh trên, chương trình sẽ tạo 3 thư mục: `MUO_sample1`, `MUO_sample2`, `MUO_sample3`.

Bạn có thể chạy lệnh `ls` để liệt kê các thư mục mới tạo.

Cấu trúc thư mục Linux rất phức tạp, vì vậy tốt nhất bạn nên tự làm quen với các thư mục mẹ và con để tránh những rào cản không cần thiết.

## 3. Các tuỳ chòn `mkdir`

Bạn có thể sử dụng một số tuỳ chọn với lệnh `mkdir`, lệnh này giúp bạn nâng cao tiện ich hiện có của lệnh.

a. `-p` hoặc `-parents`: Lệnh `-p` rất hữu ích khi tạo thư mục mẹ và thư mục con cùng nhau. Nếu thư mục mẹ được chỉ định đã tồn tại, nó sẽ tự động tạo thư mục con.

```
mkdir -p MUO/MUO_CHILD
```
b. `-v` hoặc `-verbose`: Lệnh `-v` thêm các thông báo dài dòng vào mỗi thư mục được tạo.

```
mkdir -v file1 file2
```

c.`--versiọn`: Lệnh `version` xuất chi tiết phiên bản của giấy phép

## 3. Xoá các thư mục Linux trống và không trống

Cuối cùng, thì khi bạn đã tạo các thư mục trên hệ điều hành Linux của mình, bạn có thể muốn xoá những thư mục bạn không cần nữa.

Bạn có thể xoá các thư mục trên hệ điều hành Linux của mình theo hai cách:

- rm
- rmdir

Hãy thảo luận chi tiết về cả hai phương pháp này!

Nếu muốn xoá các thư mục trống và không trống, bạn có thể sử dụng lệnh `rm` như sau:

### a. Kiểm tra nội dung của thư mục

Trước khi xoá thư mục, bạn nên kiểm tra nội dung của nó. Để làm như vậy, hãy điều hướng đến vị trí của thư mục bằng lệnh `cd`.

```
cd ./MUO
```

### b. Liệt kê nội dung thư mục:

Khi bạn đã ở vị trí của thư mục, hãy sử dụng lệnh `ls` để liệt kê nội dung của thư mục

```\
ls
```

Lệnh liệt kê tất cả nội dung của thư mục. Bạn sẽ thấy danh sách tất cả các file được lưu trữ trong thư mục này trên màn hình của bạn.

### c. Xoá thư mục qua Terminal

Nhập lệnh `rm`, theo sau là các lệnh khác nhau và tên thư mục bạn muốn xoá.

```
rm -option <directory name>
```

Bạn có thể sử dụng lại lệnh `ls` để xác nhận thư mục không còn nữa.

Dưới đây là một số tuỳ chọn được sử dụng phổ biến nhất với lệnh `rm`:
- `-f`: Buộc xoá các file và folder khỏi thư mục.
- `-i`: Yêu cầu quyền trước khi xoá thư mục
- `-r`: Xoá các thư mục và file được lưu trữ theo cách đệ quy.
- `-d`: Xoá thư mục trống

Bạn thậm chí có thể loại bỏ nhiều thư mục trong một lần.

Ví dụ, khi bạn muốn xoá các thư mục `MUO_sample1`, `MUO_sample2` và `MUO_sample3` bằng một lệnh, đây là cách bạn có thể thực hiện:


```
rm -d MUO_sample1 MUO_sample2 MUO_sample3
```

Có một phương pháp thay thế mà bạn có thể sử dụng để xoá các thư mục trống. Bạn có thể sử dụng lệnh `rmdir` để xoá thư mục nhanh chóng như sau:

```
rmdir <directory name>
```

Để xoá thư mục MUO3 khi nó không có bất kỳ file/thư mục con nào trong đó, bạn có thể sử dụng lệnh `rmdir` như dưới đây:

```
rmdir MUO3
```

Tuy nhiên, nếu thư mục không trống, bạn sẽ nhận được thông báo lỗi bất cứ khi nào bạn cố xoá thư mục bằng lệnh `rmdir`.

**Lưu ý**: Sử dụng lệnh `rm` và `rmdir` một cách cẩn thận vì không thể truy xuất được các thư mụ
## Tạo thư mục kèm cấp thư mục cha

Để tạo thư mục kèm theo thư mục cấp cha của nó phải được tạo ra ngay cả khi cấp thư mục cha chưa tồn tại.

Thì bạn hãy dùng option `-p`. Giả sử, thư mục  `/root/blogkdata_parent` chưa được tạo mới, nhưng giờ mình có nhu cầu tạo thư mục con của nó `/root/blogkdata_parent/blogkdata_dir` thì muốn tạo cả cấp thư mục cha và con luôn.

### Cú pháp lệnh

```
mkdir -p <path_name>
```

Giờ ta dùng option `-p` và `-v` để xem cách lệnh `mkdir` xử lý. Bạn sẽ thấy đầu tiên nó tạo thư mục cấp cha của `blogkdata_dir` nếu nó chưa tồn tại. Sau đó sẽ tạo thư mục con `blogkdata_dir` kế đến.

```
mkdir -p -v /root/blogkdata_parent/blogkdata_dir
```

Ta dùng lệnh `TREE` trong Linux để xem thông tin các thư mục và file thuộc thư mục `/root/` theo dạng cây.

```
tree /root/
```

```
/root/
└── blogkdata_parent
    └── blogkdata_dir
```

## Tạo thư mục với phân quyền cụ thể

Liệu ta có thể set luôn phân quyền khi mà tạo một thư mục mới hay không?

Tất nhiên là được với option `-m`.

Option này chấp nhận format và giá trị `permission` (775,...).

Nếu bạn dùng option `-m` mà không đi kèm giá trị phân quyền thì thư mục sẽ được tạo ra theo giá trị `umask` mặc định.

### Cú pháp lệnh

```
mkdir -p <permission_value> <path_name>
```

## Hiển thị quá trình tạo thư mục

Với option `-v` của lệnh MKDIR sẽ buộc phải in ra output thông tin như Khởi tạo thư mục thành công hay không? Khởi tạo thất bại! Thư mục đã tồn tại!

### Cú pháp lệnh

```
mkdir -v <path_name>
```

## Manual lệnh MKDIR trong Linux

Bạn có thể xem hướng dẫn sử dụng của lệnh MKDIR trong Linux với lệnh `man`.

```
man dir
```


