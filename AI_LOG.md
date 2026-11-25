# AI_LOG

## Phạm vi ghi nhận

Nhật ký này ghi lại phần hỗ trợ AI có thể xác nhận trong phiên cập nhật tài liệu ngày 25/11/2026. Không có nhật ký trao đổi cũ hoặc thông tin đủ để xác minh lịch sử sử dụng AI trước phiên này.

## Hoạt động trong lần cập nhật README trước

| Nội dung AI hỗ trợ | Mục đích | Kết quả |
| --- | --- | --- |
| Kiểm tra cấu trúc dự án và đọc các file `index.html`, `style.css`, `script.js` cùng README có sẵn | Xác định loại dự án, công nghệ, cấu trúc và hành vi để viết tài liệu đúng với mã nguồn | Xác định đây là website portfolio tĩnh, không có backend hoặc bước build; biểu mẫu dùng `mailto:` |
| Soạn và cập nhật `README.md` | Cung cấp mô tả, hướng dẫn chạy và sử dụng, cấu trúc file, giới hạn và hướng phát triển | README được cập nhật theo nội dung quan sát được trong mã nguồn |
| Tạo nhật ký AI này và đánh giá nhu cầu file TXT | Ghi nhận trung thực phần hỗ trợ AI hiện tại, tránh tạo file không cần thiết | Nhật ký được thêm; không tạo TXT vì mã nguồn không yêu cầu dữ liệu hoặc chức năng dựa trên TXT |

## Phân biệt đóng góp và giới hạn xác minh

- Người yêu cầu cung cấp phạm vi công việc và tiêu chí tài liệu.
- Trong lần cập nhật README trước, AI hỗ trợ khảo sát các file hiện có và soạn hai tài liệu Markdown.
- Trong lần cập nhật README trước, không sửa mã nguồn ứng dụng hoặc giao diện.
- Các file mã nguồn đã tồn tại trước khi cập nhật tài liệu; nguồn gốc và người viết ban đầu không thể xác định từ các file đã kiểm tra. Nhật ký này không gán quyền tác giả cho bất kỳ ai.
- README và trang HTML có sẵn nhắc tới việc dùng ChatGPT để học tập/gỡ lỗi, nhưng không có chi tiết về các lần trao đổi trước. Nội dung đó không được xem là bằng chứng để tái dựng lịch sử sử dụng AI.
- Lần cập nhật README trước không chạy lại website hoặc kiểm thử Playwright. Ngày và kết quả kiểm thử được nhắc trong `index.html` là ghi chú có sẵn trong dự án, không phải kết quả kiểm thử do lần đó thực hiện.

## Bổ sung: bộ dữ liệu kiểm thử TXT

Ngày 25/11/2026, theo yêu cầu tiếp theo, AI phân tích quy tắc kiểm tra của biểu mẫu trong `script.js` và giới hạn `maxlength` trong `index.html`, sau đó tạo `test-data/contact-form-cases.txt`. Bộ dữ liệu bao gồm giá trị hợp lệ, sai định dạng, rỗng/chỉ khoảng trắng, biên 10 và 500 ký tự, thử vượt giới hạn và ký tự đặc biệt. Đây là fixture để nhập thủ công; ứng dụng không tự đọc TXT.

### Kết quả kiểm tra trên trình duyệt

- Mở trang cục bộ trong trình duyệt tích hợp và nhập các bộ giá trị mẫu tương ứng. Trường hợp họ tên trống/chỉ khoảng trắng, email sai định dạng (thiếu `@` hoặc dấu chấm), tin nhắn 9 ký tự và tin nhắn chỉ có khoảng trắng đều bị từ chối; thông báo và focus đúng trường.
- Tin nhắn 10 ký tự và 500 ký tự lần lượt hiển thị bộ đếm `10/500` và `500/500`. Khi gõ 501 ký tự vào textarea, giá trị bị giới hạn ở 500.
- Đã nhập thử chuỗi tiếng Việt/ký tự đặc biệt; bộ đếm hiển thị `38/500`. Chưa xác minh nội dung mailto được encode vì không gửi biểu mẫu hợp lệ.
- Không gửi email. Các ca cần mở ứng dụng email, xác minh mã hóa mailto, thao tác dán 501 ký tự và responsive chưa được chạy trong lần kiểm tra này. Không có bộ kiểm thử tự động trong dự án.
- Không phát hiện lỗi trong các trường hợp đã chạy; không thay đổi mã nguồn ứng dụng để xử lý lỗi.
