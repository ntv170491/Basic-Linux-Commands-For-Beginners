# Lệnh `cat` trong Linux: Cú pháp và cách dùng cụ thể

![alt text](image.png)

Lệnh `cat` (viết tắt của **concatenate**) là một trong những lệnh được sử dụng thường xuyên nhất trong các hệ điều hành như Linux/Unix.

Lệnh `cat` cho phép người dùng tạo *một hoặc nhiều file*, *xem nội dung file*, *nối file* và c*huyển hướng đầu ra* trong terminal hoặc file.

## Cú pháp lệnh `cat` trong Linux

```
cat [OPTION] [FILE] ...
```

## 1. Hiển thị nội dung của file

```
ntdee@ntdee-ThinkPad-X260:~$ cat /etc/hosts
```

```
127.0.0.1	localhost
127.0.1.1	ntdee-ThinkPad-X260

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```

## 2. Xem nội dung của nhiều file trong Terminal

```
cat test.txt test1.txt
```

```
Hello everybody
Hi world,
```

## 3. Tạo file bằng lệnh `cat`

```
cat >test2
```

Chờ đầu vào từ người dùng, nhập văn bản mong muốn và nhấn `CTRL + D` (giữ phím Ctrl và nhập d) để thoát.

Văn bản sẽ được viết trong file test2.

Bạn có thể xem nội dung của file bằng lệnh `cat` sau:

```
cat test 2
```

```
hello everyone, how do you do?
```

## 4. Sử dụng lệnh `cat` với các tuỳ chọn more và less

Nếu file có số lượng lớn nội dung không vừa terminal đầu ra và màn hình cuộn lên rất nhanh, bạn có thể sử dụng các tham số `more` và `less` với lệnh `cat` như sau:

```
cat song.txt | more
```

```
cat song.txt | less
```

## 5. Hiển thị số dòng trong file

Với tuỳ chọn `-n`, bạn có thể thấy số dòng của file song.txt trong terminal đầu ra:

```
cat -n song.txt
```
```
    1	"Heal The World"
    2	There's A Place In
    3	Your Heart
    4	And I Know That It Is Love
    5	And This Place Could
    6	Be Much
    7	Brighter Than Tomorrow
    8	And If You Really Try
    9	You'll Find There's No Need
    10	To Cry
    11	In This Place You'll Feel
    12	There's No Hurt Or Sorrow
```

## 6. Hiển thị `$` ở cuối file

Trong phần bên dưới, bạn có thể thấy với tuỳ chọn `-e`, `$` được hiển thị ở cuối dòng và trong khoảng trắng giữa các đoạn văn.

Tuỳ chọn này rất hữu ích để ép nhiều dòng thành một dòng.

```
cat -e test
``` 

```
hello everyone, how do you do?$
$
Hey, am fine.$
How's your training going on?$
$
``` 

## 7. Hiển thị các dòng được phân tách bằng `tab` trong file

Trong đầu ra bên dưới, bạn có thể thấy không gian TAB được lấp đầy bởi ký tự ^|

```
cat -t test
```

```
hello ^Ieveryone, how do you do?

Hey, ^Iam fine.
^I^IHow's your training ^Igoing on?
Let's do ^Isome practice in Linux.
``` 

## 8. Hiển thị nhiều file cùng một lúc

Trong ví dụ dưới đây, có 3 file test, test1 và test2.

Bạn có thể xem nội dung của các file đó như được hiển thị ở trên.

Nhớ tách từng file với dấu chấm phẩy.

```
cat test; cat test1; cat test2
```

```
This is test file
This is test1 file.
This is test2 file.
```

## 9. Sử dụng đầu ra tiêu chuẩn với toán tử chuyển hướng

Bạn có thể chuyển hướng đầu ra tiêu chuẩn của một file thành một file mới khác file hiện có với ký hiệu `>`.

Hãy cẩn thận, nội dung hiện có của test1 sẽ bị ghi đề bởi nội dung của file test.

```
cat test > test1
```

## 10. Nối đầu ra tiêu chuẩn với toán tử chuyển hướng

Hãy nối thêm nội dung trong file hiện có với ký hiệu `>>`.

Tại đây, nội dung của file test sẽ được thêm vào cuối file test1.

```
cat test >> test1
```

## 11. Chuyển hướng đầu vào chuẩn với toán tử chuyển hướng

Khi bạn sử dụng chuyển hướng với đầu vào tiêu chuẩn `<`, lệnh sử dụng file *test2* làm đầu vào cho một lệnh và đàu ra sẽ được hiển thị trong một terminal.

```
cat < test2
```

```
This is test2 file
```

## 12. Chuyển hướng nhiều đầu ra vào một file duy nhất

Thao tác này sẽ tạo một file có tên là *test3* và tất cả các đầu ra sẽ được chuyển hướng tới file mới được tạo.

```
cat test test1 test2 > test3
```

## 13. Sắp xếp nội dung của nhiều file trong một file duy nhất.

Thao tác này sẽ tạo một file *test4* và đầu ra của lệnh `cat` được phân loại để sắp xếp và kết quả sẽ được chuyển hướng tới một file mới được tạo.

```
cat test test1 test2 test3 | sort > test4
```

## 14. Hiển thị file đảo nghịch bằng `cat`

Để xem nội dung file theo thứ tự đảo nghịch, từ dưới lên, bắt đầu bằng dòng cuối cùng và kết thúc ở dòng đầu tiên, sử dụng lệnh `tac` tức là từ `cat` viết ngược lại:

```
tac filename.txt
```

Bạn sẽ có thể vận dụng tốt nó khi vận hành máy chủ. 

Để tìm hiểu thêm thông tin về nó bạn hãy luôn nhớ lệnh sau `man cat`. Nó sẽ xuất ra tài liệu hướng dẫn cho bạn.

