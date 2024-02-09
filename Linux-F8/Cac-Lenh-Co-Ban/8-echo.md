#  Cách sử dụng lệnh `echo` trong Linux

Cho dù bạn là người hoàn toàn mới đối với Linux hoặc đã sử dụng desktop Linux trong một thời gian dài, có một số lệnh dường như không có ý nghĩa.

Điều này đặc biệt đúng nếu bạn không bao giờ đi sâu vào dòng lệnh.

Nhưng đó mới là nơi mà phần lớn sức mạnh thực sự của Linux và các hệ điều hành tương tự Unix khác phát huy tác dụng.

Một trong số đó là lệnh `echo`. Thoạt nhìn, đây có vẻ như là một lệnh vô dụng. Nhưng nếu tìm hiểu sâu hơn, bạn sẽ thấy nó hữu ích một cách đáng ngạc nhiên.

## Lệnh `echo` thực hiện nhiệm vụ gì?

Nhìn vào tài liệu hướng dẫn cho `echo`, bạn sẽ khyông thấy chúng hữu ích lắm.

Nó cho biết `echo` có nhiệm vụ *display a line of text* (hiển thị một dòng văn bản).

Đây có lẽ là điều bạn có thể suy ra từ tên của lệnh.

Về cơ bản, những gì `echo` làm là gửi đối số đến đầu ra tiêu chuẩn cùng với một số tuỳ chọn định dạng cơ bản.

Lý do chính khiến lệnh này tồn tại là để hoạt động bên trong các script khác, cho phép bạn hiển thị đầu ra cho người đang chạy script.

## Những điều cơ bản

Ở mức độ cơ bản, echo thực hiện chính xác những gì ta có thể suy ra từ tên lệnh. Dưới đây là một ví dụ:

```
echo Can anybody hear me
```

Lệnh này sẽ xuất đầu ra **Can anybody hear me**. Nếu chỉ gõ lệnh này, nó thực sự trong giống như một *tiếng vọng* lại chính xác nội dung bạn đã nói (đó là lý do tại sao lệnh này tên là `echo`).

Tuy nhiên, nếu thêm một dấu hỏi vào lệnh trên, bạn sẽ gặp lỗi. Hãy gõ như sau:

```
echo "Can anybody hear me?"
```

Văn bản kết quả không có các dấu ngoặc kép xung quanh, nhưng sẽ hiển thị đúng dâu chẩm hỏi.

Bạn cũng có thể sử dụng các biến với lệnh `echo`.

```
x=256

echo $x
```

Lệnh trên sẽ in kết quả `256` đến terminal.

## Các lệnh nâng cao hơn

Lệnh `echo` hoạt động khác nhau trên các hệ thống nhất định.

Ví dụ, trên Linux, có một số tuỳ chọn mà bạn không thể thấy trên các hệ điều hành giống như Unix khác.

Ví dụ, tuỳ chọn `-e` cho phép bạn chèn các ký tự, như `\n` cho dòng mới hoặc `\t` cho các tab.

```
echo -e "I sure hope this quote is attributed. \n\t--Me"
```

Lệnh trên có thể trông hơi khó hiểu ở phần cuối, nhưng nó sẽ in ra một cái gì đó tương tự như sau:

```
I sure hope this quote ís attributed. 
	--Me
```

Bạn cũng có thể sử dụng `\b` cho `Backspace`\

## Ví dụ thực tế

Như đã giải thích, trường hợp sử dụng thực tế cho lệnh `echo` là trong các script bạn viết.

Bạn cũng có thể sử dụng nó để dọn dẹp một chút cho đầu ra của các script khác.

Đối với trường hợp sử dụng đó, có nhiều công cụ tốt như `grep` và `sed`.

Một trường hợp sử dụng tuyệt vời khác cho lệnh `echo` là trong các file cấu hình được sửa đổi một chút.

Chỉ cần sử dụng ký hiệu chuyển hướng tiêu chuẩn `>`. Ví dụ:

```
echo "Just some text" >> ~/just-a-file.txt
```

Lệnh này sẽ nối văn bản vào file "just-a-file.txt".

Hãy chạy nó lại và dòng này sẽ xuất hiện 2 lần.

Khi đọc qua các ví dụ này, bạn có thể tự hỏi tại sao mọi người lại sử dụng chúng.

Thậm chí chúng có thể khiến bạn thắc mắc tại sao mọi người muốn sử dụng Linux thay vì Windows hoặc macOS.

Thông thường, khi một cái gì đó về Linux có vẻ kỳ lạ, thì điều này thường có nguồn gốc từ cách sử dụng trong nhiều thập kỷ trước.

Tuy nhiên, việc này không nhất thiết có ý nghĩa tiêu cực. Nếu bạn không chắc chắn về Linux, hãy xem bài viết: [8 lý do chuyển từ Window sang Linux](https://quantrimang.com/cong-nghe/8-ly-do-chuyen-tu-windows-sang-linux-69588) để trả lời những thắc mắc của mình.

---

# Echo Command

`echo` là một shell được xây dựng trong Bash và hầu hết các loại shell phổ biến khác như Zsh và Ksh. Hành vi của nó hơi khác nhau từ shell này sang shell khác.

Ngoài ra còn có một tiện ích độc lập `/usr/bin/echo`, nhưng thông thường phiên bản tích hợp shell sẽ được ưu tiên. Chúng sẽ bao gồm phiên bản Bash builtin của `echo`.

Cú pháp cho lệnh như sau:

```
echo [-neE] [ARGUMENTS]
```

- Khi tuỳ chọn `-n` được sử dụng, dòng mới bị chặn ở cuối.
- Nếu tuỳ chọn `-e` được đưa ra, các ký tự thoát sau dấu gạch chéo ngược sau sẽ được hiểu:
  + \\\ - Hiển thị một ký tự gạch chéo ngược.
  + \\a - Cảnh báo (BEL)
  + \\b - Hiển thị ký tự backspace
  + \\c - Ngăn chặn bất kỳ đầu ra nào khác.
  + \\e - Hiển thị `escape` character 
  + \\f - Hiển thị một ký tự nguồn cấp biểu mẫu
  + \\n - Hiển thị một dòng mới
  + \\r - Hiển thị dấu xuống dòng.
  + \\t - Hiển thị `tab` ngang
  + \\v - Hiển thị một `tab` dọc.
- Tuỳ chọn `-E` vô hiệu hoá việc giải thích các ký tự thoát. Đây là mặc định.

Có một vài điểm cần xem xét khi sử dụng lệnh `echo`.

- Shell sẽ thay thế tất cả các biến, khớp ký tự đại diện và ký tự đặc biệt trước khi chuyển các đối số sang lệnh `echo`.
- Mặc dù không cần thiết, nhưng theo đúng quy tắc đối số được truyền nên trong dấu ngoặc kép hoặc ngoặc đơn.
- Khi sử dụng dấy nháy đơn `'`, giá trị chữ của mỗi ký tự được bao trong dấu ngoặc kép sẽ được giữ nguyên. Các biến và lệnh sẽ không được mở rộng.

# Ví dụ:

Các ví dụ sau đây cho thấy cách sử dụng lệnh `echo`:

## Hiển thị một dòng văn bản trên đầu ra tiêu chuẩn.

```
echo Hello, World!
```

```
Hello, World!
```

## Hiển thị một dòng văn bản có chứa dấu ngoặc kép.

```
echo 'Hello "Hocdevops"'
echo "Hello \"Hocdevops\""
```

```
Hello "Hocdevops"
```

## Hiển thị một dòng văn bản có chứa một trích dẫn duy nhất.

Để in một báo giá duy nhất, hãy kèm theo nó trong báo giá đôi hoặc sử dụng **Trích dẫn ANSI-C**.

```
echo "I'm a Linux user."
echo $'I\'m a Linux user.'
```

## Hiển thị thư chứa các ký tự đặc biệt.

Sử dụng tuỳ chọn `-e` để cho phép giải thích các ký tự `escape`.

```
echo -e "You know nothing, Jon Snow.\n\t- Ygritte"
```
```
You know nothing, Jon Snow.
	- Ygritte
```

## Các ký tự phù hợp với mẫu

Lệnh `echo` có thể được sử dụng với các ký tự khớp mẫu, chẳng hạn như các ký tự đại diện.

Ví dụ: lệnh dưới đây sẽ trả về tên của tất cả các tệp `.php` trong thư mục hiện tại.

```
echo The PHP files are: *.php
```

```
The PHP files are: index.php contact.php functions.php
```


## Hiển thị các biến

Cũng có thể hiển thị các biến. Trong ví dụ sau, chúng ta sẽ in tên của người dùng hiện đang đăng nhập:

```
echo $USER
```

```
ntdee@ntdee-ThinkPad-X260:~$ echo $USER
ntdee
```

`$USER` là một biến `shell` giữ tên của người dùng của bạn.

## Hiển thị đầu ra của lệnh

Sử dụng biểu thức `$(command)` để bao gồm đầu ra lệnh trong đối số của `echo`.

Lệnh sau sẽ hiển thị `ngày hiện tại`.

```
echo "The date is: $(date +%D)"
```

```
ntdee@ntdee-ThinkPad-X260:~$ echo "The date is: $(date +%D)"
The date is: 02/09/24
```

## Hiển thị màu

Sử dụng trình tự thoát `ANSI` để thay đổi màu nền trước và nền sau hoặc đặt các thuộc tính văn bản như gạch dưới và in đậm.

```
echo -e "\033[1;37mWHITE"
echo -e "\033[0;30mBLACK"
echo -e "\033[0;31mRED"
echo -e "\033[0;32mGREEN"
echo -e "\033[0;33mYELLOW"
echo -e "\033[0;34mBLUE"
echo -e "\033[0;35mPURPLE"
echo -e "\033[0;36mCYAN"
echo -e "\033[1;30mGRAY"
```

![alt text](color.png)