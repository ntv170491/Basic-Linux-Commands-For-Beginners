# Tìm hiểu về ứng dụng Vi trong Linux

Đối vói người dùng Linux thì `Vi` - ứng dụng soạn thảo, chỉnh sửa text chính là 1 trong những công cụ hỗ trợ không thể thiếu.

Không giống như Nano - ứng dụng chỉnh sửa text dưới dạng Terminal, `Vi` có hệ thống các phím tắt chức năng khác đa dạng và hữu ích, với 2 chế độ hoạt động chính là *Insert* và *Command*
## Vi là gì?

Vi là một trình chỉnh sửa dành cho Linux, Unix và các hệ điều hành giống Unix khác.

Vi là viết tắt của **visual instrument**.

Nó là một trình soạn thảo văn bản mặc định được sử dụng rộng rãi cho các hệ thống dựa trên Unix và đi kèm với tất cả các phiên bản Unix.

Nó chỉ sử dụng bàn phím và cung cấp một giao diện rất hiệu quả để chỉnh sửa những chương trình và script.

So với một chương trình xử lý text chung chung, VI được điều chỉnh cho phù hợp với một cấu hình cụ thể hơn về cách sử dụng và người dùng - những người lập trình của các hệ thống dựa trên UNIX.

Không giống như các trình xử lý văn bản dựa trên Window phổ biến rộng rãi (chẳng hạn như Notepad  và Word của Microsoft), VI không cung cấp bất kỳ khả năng định dạng nào.

Chương trình VI ban đầu được viết bởi Bill Joy vào năm 1967 và trở thành một phàn của Single Unix Specification Standar, yêu cầu mọi bản phân phối Unix phù hợp phải bao gồm nó.

Cho đến sự nổi lên của Emacs, một trình soạn thảo văn bản phổ biến khác, vào năm 1984, VI vẫn là trình soạn thảo Unix tiêu chuẩn trên thực tế.

Thậm chí, cuộc khảo sát năm 2009 của đọc giả Linux Jourmal cũng đã đánh giá VI là trình soạn thảo văn bản được sử dụng nhiều nhất, đẩy Emacs xuống vị trí thứ hai.

`Vi` thực sự có một trình chỉnh sửa cơ bản được gọi là `ex`. Vi là chế dộ trực quan của `ex`.

Để thực hiện các lệnh vốn có đối với trình soạn thảo dòng lệnh cũ, dấu hai chấm `:` được sử dụng.

Ngoài ra còn có hai chế độ hoạt động chính: 

- Chế độ lệnh
- chế độ chèn.

Để quay lại chế độ lệnh, chỉ cần nhấn phím `ESC`

## Mở `Vi` trên Linux

Vi thực chất là 1 ứng dụng *Terminal*, so vậy các bạn sẽ phải khởi động từ cửa sổ *Terminal* tương ứng. Dùng cú pháp:

```
vi path/to/file
```

Để mở file text có sẵn bằng Vi, và lệnh đó cũng sẽ hoạt động nếu file text được chỉ định không có sẵn, thay vào đó Vi sẽ tự tạo file text với tên như vậy.

| Phím  | Mô tả                    |
|-------|--------------------------|
| k     | Đưa con trỏ lên trên     |
| j     | Đưa con trỏ xuống dưới   |
| h     | Đưa con trỏ sang trái    |
| l     | Đưa con trỏ sang phải    |

## Các lệnh thông thường trong Vi

**Lưu ý:** Bạn phải ở chế độ Command.

|   Lệnh    |       Mô tả                                               |
|-----------|-----------------------------------------------------------|
|   i       | Chèn văn bản trước vị trí con trỏ hiện tại                |
|   l       | Chèn văn bản ở đầu dòng hiện tại.                         |
|   a       | Chèn văn bản sau vị trí con trỏ hiện tại.                 |
|   A       | Chèn văn bản ở cuối dòng hiện tại                         |
|   o       | Tạo một dòng mới cho mục nhập văn bản bên dưới con trỏ    |
|   O       | Tạo một dòng mới cho mục nhập văn bản bên trên con trỏ    |
|   x       | Xoá ký tự bên dưới con trỏ.                               |
|   X       | Xoá ký tự trước con trỏ.                                  |    
|   dd      | Xoá dòng con trỏ đang được đặt.                           |
|   cc      | Xoá nội dung của dòng, để người dùng ở chế độ Insert      |
|   r       | Thay thế ký tự bên dưới con trỏ.                          |
|   yw      | Sao chép từ hiện tại                                      |
|   p       | Đặt văn bản đã sao chép sau con trỏ.                      |

## Lệnh Vi nâng cao

|   Lệnh        |       Mô tả                                                                                   
|---------------|-----------------------------------------------------------------------------------------------
|   <<          | Tham gia vào dòng hiện tại và dòng tiếp theo. Một số tham gia vào nhiều dòng                  
|   >>          | Căn dòng hiện tại sang bên trái với một chiều rộng có thể thay đổi.                          
|   :nr file    | Đọc file và chèn nó sau dòng n.                                                               
|   ~           | Chuyển đổi kiểu viết hoa/viết thường của ký tự bên dưới con trỏ.                                   
|   ^G          | Nhấn các phím `CTRL` và `C` cùng một lúc để hiển thị tên file và trạng thái hiện tại.        
|   U           | Khôi phục dòng hiện tại về trạng thái trước khi con trỏ nhập vào dòng.                       
|   u           | Hoàn tác thay đổi cuối cùng đối với tệp. Nhập lại `u` một lần nữa sẽ thực hiện lại thay đổi.
|   J           | Tham gia vào dòng hiện tại và dòng tiếp theo. Một số tham gia vào nhiều dòng.             
|   :f          | Hiển thị vị trí hiện tại trong tệp bằng % và tên file, tổng số file.                         
|   :f filename | Đổi tên file hiện tại thành filename.                                                        
|   :w filename | Viết vào filename của file                                                                   
|   :e filename | Mở một file khác với filename                                                                
|   :cd dirname | Thay đổi thư mục làm việc hiện tại thành `dirname`                                           
|   :e #        | Sử dụng để chuyển đổi giữa 2 file đã mở.
|   :n          | Trong trường hợp bạn mở nhiều file bằng Vi, hãy sử dụng `:n` để chuyển đến file tiếp theo trong chuỗi 
|   :N          | Trong trường hợp bạn mở nhiều file bằng Vi, hãy sử dụng `:N` để chuyển đến file trước đó trong chuỗi
|   :r file     | Đọc file và chèn nó sau dòng hiện tại.