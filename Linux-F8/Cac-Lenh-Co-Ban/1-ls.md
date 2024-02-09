# ls - list

## 1. Lệnh `ls` trên linux

Lệnh `ls` được sử dụng để liệt kê tất cả các tệp và folder có trong thư mục (directory) làm việc hiện tại của bạn.

Bạn cũng có thể nhận được thông tin về các tệp bằng các sử dụng cùng một lệnh.

Vì nó đã được bao gồm trong gói tiện ích cốt lõi GNU, bạn không cần phải cài đặt thêm bất kỳ gói nào trên hệ thống của mình để sử dụng nó.

Bạn cũng có thể xâu chuỗi `ls` với các lệnh `bash` khác.

Ví dụ: đặt câu lệnh (statement) `grep` với `ls` sẽ cho phép bạn tìm kiếm và lọc thư mục cho các tệp cụ thể.

## 2. Cách sử dụng lệnh `ls`:

 ~~~
 ntdee@ntdee-ThinkPad-X260:~$
 ~~~

 1. ntdee@ntdee: user name

 2. ThinkPad-X260/IP Address

 3. ~: /home

 4. $: gõ lệnh

```
ls [option] [directory]
```

Một trong những các sử dụng lệnh đơn giản nhất là liệt kê tất cả các file và folder trong thư mục làm việc hiện tại của bạn
   
~~~
ntdee@ntdee-ThinkPad-X260:~$ ls
~~~
*output*
~~~
Data     Documents  Music     Public     Videos
Desktop  Downloads  Pictures  Templates  Warpinator
~~~


**Xoá màn hình**

~~~
ntdee@ntdee-ThinkPad-X260:~$ clear
~~~

### 2.1 Liệt kê các tệp trong thư mục cụ thể

Để liệt kê các tệp thuộc một thư mục khác (không phải thư mục làm việc hiện tại), bạn sẽ phải chuyển đường dẫn the mục cùng với tên lệnh.

```
ls [directory]
```

Để lấy danh sách tất cả các tệp có trong thư mục `/boot`:

```
ls /boot
```

```
config-5.15.0-56-generic      initrd.img.old
config-5.15.0-91-generic      System.map-5.15.0-56-generic
efi                           System.map-5.15.0-91-generic
grub                          vmlinuz
initrd.img                    vmlinuz-5.15.0-56-generic
initrd.img-5.15.0-56-generic  vmlinuz-5.15.0-91-generic
initrd.img-5.15.0-91-generic  vmlinuz.old
```

Sử dụng flag `-F` với lệnh sẽ thêm ký tự `/` vào cuối mỗi thư mục

```
ntdee@ntdee-ThinkPad-X260:~$ ls /boot -F
```

```
config-5.15.0-56-generic      initrd.img.old@
config-5.15.0-91-generic      System.map-5.15.0-56-generic
efi/                          System.map-5.15.0-91-generic
grub/                         vmlinuz@
initrd.img@                   vmlinuz-5.15.0-56-generic
initrd.img-5.15.0-56-generic  vmlinuz-5.15.0-91-generic
initrd.img-5.15.0-91-generic  vmlinuz.old@
```

Bạn cũng có thể *chuyển nhiều thư mục* bằng cách tách tên đường dẫn với ký tự `Dấu cách`:

```
ntdee@ntdee-ThinkPad-X260:~$ ls /boot /usr
```

```
/boot:
config-5.15.0-56-generic      initrd.img.old
config-5.15.0-91-generic      System.map-5.15.0-56-generic
efi                           System.map-5.15.0-91-generic
grub                          vmlinuz
initrd.img                    vmlinuz-5.15.0-56-generic
initrd.img-5.15.0-56-generic  vmlinuz-5.15.0-91-generic
initrd.img-5.15.0-91-generic  vmlinuz.old

/usr:
bin    include  lib32  libexec  local  share
games  lib      lib64  libx32   sbin   src
```
### 2.2 Liệt kê các tệp trong Thư mục gốc (Root directory)

Thư mục gốc chứa tất cả các thư mục và tệp khác trên hệ thống của bạn.

Đây là thư mục cao nhất trong hệ thống phân cấp thư mục trên máy tính.

Thư mục gốc thường được ký hiệu bằng ký tự `/`.

```
ntdee@ntdee-ThinkPad-X260:~$ ls /
```
*output*
```
bin   cdrom  etc   lib    lib64   lost+found  mnt  proc  run   srv  tmp  var
boot  dev    home  lib32  libx32  media       opt  root  sbin  sys  usr
```

*Dù bạn đang ở thư mục nào tại thời điểm nhập lệnh, lệnh được đề cập ở trên sẽ tạo ra một đầu ra liệt kê tất cả các thư mục con và tệp có bên trong thư mục gốc.*

### 2.3 Liệt kê các tệp trong Thư mục gốc

Thư mục mẹ (parent directory) trong Linux là một thư mục phía trên thư mục hiện tại.

Ví dụ như `/usr/bin`. 
- `/bin` là thư mục làm việc hiện tại của bạn
- `/usr` là thư mục mẹ.

Để nhận danh sách tất cả các tệp trong thư mục mẹ:

```
ls ..

ls ../..
```

Thêm một `..` khác sẽ đưa bạn đến thư mục mẹ.

Ví dụ, `/var/log/old` là thư mục làm việc hiện tại của bạn.

`ls ..` sẽ liệt kê các thư mục có trong thư mục `/log` trong khi `ls ../..` sẽ cung cấp cho bạn danh sách tất cả các tệp và thư mục có trong thư mục `/var`.

### 2.4 Liệt kê các tệp trong Thư mục chính (Home Directory)

Thư mục chính trong Linux được ký hiệu bằng ký tự `~`.

Do đó, để liệt kê nội dung có sẵn trong thư mục chính của bạn: `ls ~`

### 2.5 Chỉ liệt kê các thư mục (Không có tệp)

Nếu vì bất kỳ lý do gì mà bạn chỉ muốn liệt kê các folder có trong một thư mục, hãy sử dụng flag `-d` với lệnh `ls` mặc định.

```
ls -d /home
```

### 2.6 Liệt kê các tệp với các thư mục con

Sử dụng ký tự `*` với lệnh `ls` sẽ cung cấp cho bạn danh sách tất cả các tệp và thư mục trong thư mục làm việc hiện tại, cùng với các thư mục con (sub-directory).

```
ls *
```

### 2.7 Liệt kê các tệp một cách đệ quy

Sử dụng flag `-R` với lệnh mặc định sẽ liệt kê tất cả các tệp và folder có bên trong thư mục cho đến cấp cuối cùng.

```
ls -R
```

**Lưu ý** - bạn cũng có thể chuyển đường dẫn thư mục cùng với flag đệ quy. Điều này có nghĩa là `ls /usr/home -R` là một lệnh hợp lệ.

### 2.8 Liệt kê các tệp với kích thước của chúng

Để lấy tên của tất cả các tệp cùng kích thước của chúng, hãy sử dụng flag `-s` với lệnh:

```
ls -s /yay-git
```

```
ntdee@ntdee-ThinkPad-X260:~$ ls -s /home
```

```
total 4
4 ntdee
```

### 2.9 Liệt kê các tệp với thông tin chi tiết

Flag `-l` cho phép bạn nhận danh sách nội dung của thư mục Linux với mô tả chi tiết của từng mục nhập. Thông tin sau được bao gồm trong đầu ra:
1. Quyền đối với file và folder
2. Số lượng liên kết
3. Chủ sở hữu nội dung
4. Kích thước nội dung
5. Tên tệp
6. Ngày giờ sửa đổi lần cuối

```
ls -s
```

```
total 40
drwxrwxr-x 3 ntdee ntdee 4096 Jan  7 19:39 Data
drwxr-xr-x 2 ntdee ntdee 4096 Jan 16 15:35 Desktop
drwxr-xr-x 2 ntdee ntdee 4096 Jan  7 16:21 Documents
drwxr-xr-x 2 ntdee ntdee 4096 Jan 15 18:46 Downloads
drwxr-xr-x 2 ntdee ntdee 4096 Jan  7 16:21 Music
drwxr-xr-x 2 ntdee ntdee 4096 Jan 15 17:50 Pictures
drwxr-xr-x 2 ntdee ntdee 4096 Jan  7 16:21 Public
drwxr-xr-x 2 ntdee ntdee 4096 Jan  7 16:21 Templates
drwxr-xr-x 2 ntdee ntdee 4096 Jan  7 16:21 Videos
drwxrwxr-x 2 ntdee ntdee 4096 Jan  7 16:21 Warpinator
```

Cột đầu tiên được dành riêng cho quyền đối với file và folder.

Ký tự đầu tiên biểu thị loại tệp và chín ký tự tiếp theo biểu thị quyền của tệp.

**Các loại tệp khác nhau mà bạn thường gặp:**

1. Tệp thông thường (Regular file)`-`
2. Chặn các tệp đặc biệt (Block special files)`b`
3. Các tệp đặc biệt của ký tự (Character special file)`c`
4. Thư mục (Directory)`d`
5. Liên kết tượng trưng (Symbolic link)`l`
6. Tệp mạng (Network file)`n`
7. FIFO (p)
8. Ổ căm (Socket)`s`

**Về quyền đối với tệp, các ký tự sau được sử dụng trong đầu ra**

1. Có thể đọc được (Readable)`r`
2. Ghi (Writable)`w`
3. Thực thi (Executable)`x`

Ví dụ như `d rw-r-r-` làm ví dụ. 
- Ký tự đầu tiên cho biết rằng mục nhập (entry) là một thư mục.
- Hai ký tự sau biểu thị rằng người dùng hiện tại có quyền đọc và ghi.
- Các ký tự còn lại cung cấp thông tin về quyền đối với tệp cho những người dùng khác.

### 2.10 Liệt kê các tệp có kích thước có thể đọc được

Lệnh `-s` cung cấp cho bạn một giá trị số được liên kết với mỗi mục nhập. Và hiển nhiên, bạn sẽ không biết ý nghĩa của giá trị này là gì.

Do đó, để liệt kê các tệp và kích thước của chúng theo cách có thể đọc được, hãy sử dụng flag `-lh` cùng với lệnh.

```
ls -lh
```

```
total 40K
drwxrwxr-x 3 ntdee ntdee 4,0K Jan  7 19:39 Data
drwxr-xr-x 2 ntdee ntdee 4,0K Jan 16 15:35 Desktop
drwxr-xr-x 2 ntdee ntdee 4,0K Jan  7 16:21 Documents
drwxr-xr-x 2 ntdee ntdee 4,0K Jan 17 19:20 Downloads
drwxr-xr-x 2 ntdee ntdee 4,0K Jan  7 16:21 Music
drwxr-xr-x 2 ntdee ntdee 4,0K Jan 15 17:50 Pictures
drwxr-xr-x 2 ntdee ntdee 4,0K Jan  7 16:21 Public
drwxr-xr-x 2 ntdee ntdee 4,0K Jan  7 16:21 Templates
drwxr-xr-x 2 ntdee ntdee 4,0K Jan  7 16:21 Videos
drwxrwxr-x 2 ntdee ntdee 4,0K Jan  7 16:21 Warpinator
```

Các chỉ định kích thước cho byte (B), megabyte (MB), gigabyte (GB) và terabyte (TB) được sử dụng trong đầu ra.

### 2.11 Liệt kê các tệp ẩn

Lệnh `ls` mặc định không bao gồm các tệp ẩn trong đầu ra.

Để liệt kê nội dung được người dùng đặt là ẩn, hãy dùng flag `-a` với lệnh `ls`.

```
ls -a
```

```
.              Desktop      .mozilla                   Templates
..             Documents    Music                      .themes
.bash_history  .dotnet      Pictures                   Videos
.bash_logout   Downloads    .pki                       .vscode
.bashrc        .ecryptfs    .presage                   Warpinator
.cache         .gtkrc-2.0   .Private                   .Xauthority
.config        .gtkrc-xfce  .profile                   .xinputrc
Data           .linuxmint   Public                     .xsession-errors
.dbus          .local       .sudo_as_admin_successful  .xsession-errors.old
```

### 2.12 Dùng ls với lệnh Grep

Lệnh `grep` được sử dụng để so khớp các mẫu tuân theo một biểu thức (expression) cụ thể.

Bạn có thể xâu chuỗi lệnh này với `ls` để tìm kiếm các tệp có trong hệ thống của bạn.

Trong thư mục gốc của bạn, hãy nhập:

```
ls | grep l
```

```
Downloads
Public
Templates
```

Thao tác này sẽ liệt kê tất cả các file và folder bắt đầu bằng ký tự `|`.

Bạn cũng có thể lọc các tệp của mình theo phần mở rộng (extension) của chúng bằng cách sử dụng `grep`.

### 2.13 Sắp xếp các tập tin theo thời gian và ngày tháng

Để liệt kê tất cả các tệp và sắp xếp chúng theo thời gian và ngày tạo/sửa đổi, hãy sử dụng flag `-t` cùng với ls.

```
ls -t
```

### 2.14 Sắp xếp tệp theo kích thước

Flag `-S` sẽ cho phép bạn sắp xếp các tệp và thư mục phù hợp với kích thước tệp của chúng.

```
ls -S
```

Theo mặc định, các tệp sẽ được sắp xếp theo thứ tự giảm dần (tệp lớn nhất trước). Tuy nhiên, bạn có thể dễ dàng đảo ngược hành vi này bầng cách thêm `r` vào flag `-S`

```
ls -Sr
```

### 2.15 Liệt kê tệp và gửi đầu ra tới tệp

Sử dụng ký tự `>`, bạn có thể gửi đầu ra của lệnh ls tới bất kỳ tệp nào.

```
ls > ls-output.txt
```

Sau đó, bạn có thể đọc nội dung của tệp mới tạo bằng cách nhập `cat ls-output.txt` vào terminal của bạn.

## 3. Hiển thị nội dung của một thư mục lệnh ls

Lệnh ls là một trong những lệnh mạnh nhất được cung cấp cho người dùng Linux. Để khai thác tối đa các lệnh của bạn trong terminal, bạn có thể thử xâu chuỗi các lệnh cùng nhau.

Mẹo số một để làm quen với Linux là ghi nhớ một số lệnh cơ bản. Điều này chắc chắn sẽ giúp bạn trở nên hiệu quả và nhanh chóng trong khi sử dụng hệ thống của bạn.