# Portfolio Nguyễn Ngọc Hải

Website portfolio cá nhân dạng một trang, giới thiệu Nguyễn Ngọc Hải, kỹ năng, dự án, hồ sơ kỹ thuật và thông tin liên hệ. Dự án dùng HTML, CSS và JavaScript thuần, không cần cài thư viện hay chạy bước build.

## Mục tiêu và chức năng

- Giới thiệu cá nhân và điều hướng tới các phần Giới thiệu, Kỹ năng, Dự án, Hồ sơ kỹ thuật và Liên hệ.
- Trình bày kỹ năng và các dự án mẫu; ảnh dự án hiện được nhúng trực tiếp trong HTML.
- Thích ứng với màn hình nhỏ và lớn; hỗ trợ trạng thái focus bàn phím, giảm chuyển động theo cài đặt của hệ điều hành và hiệu ứng xuất hiện khi cuộn.
- Cung cấp biểu mẫu liên hệ có kiểm tra dữ liệu ở phía trình duyệt. Biểu mẫu mở ứng dụng email qua `mailto:`; website không gửi hoặc lưu dữ liệu.

## Công nghệ

- HTML5
- CSS3 (CSS Grid, Flexbox, custom properties, media queries)
- JavaScript thuần
- Google Fonts: Chakra Petch và Be Vietnam Pro, có font dự phòng hệ thống

Không có backend, cơ sở dữ liệu, framework, dependency hoặc công cụ build được khai báo trong dự án.

## Cấu trúc dự án

```text
sv01-main/
├── index.html    # Nội dung, bố cục ngữ nghĩa và ảnh nhúng
├── style.css     # Giao diện, responsive, focus và chuyển động
├── script.js     # Kiểm tra biểu mẫu, mailto và hiệu ứng xuất hiện
├── README.md     # Hướng dẫn dự án
├── AI_LOG.md     # Nhật ký hỗ trợ AI có thể xác minh
└── test-data/
    └── contact-form-cases.txt # Dữ liệu nhập mẫu để kiểm thử biểu mẫu liên hệ
```

## Cài đặt và chạy

Không cần cài đặt dependency. Mở `index.html` trực tiếp bằng trình duyệt, hoặc từ thư mục dự án chạy máy chủ tĩnh:

```powershell
py -m http.server 8000
```

Sau đó truy cập <http://localhost:8000>. Nếu lệnh `py` không khả dụng, có thể mở trực tiếp file hoặc dùng một máy chủ tĩnh khác.

Google Fonts được tải từ Internet; khi ngoại tuyến, trang dùng font dự phòng. Ảnh đang nhúng trong `index.html`, nên không cần tải ảnh riêng.

## Hướng dẫn sử dụng

1. Dùng menu ở đầu trang hoặc các nút kêu gọi hành động để chuyển tới từng phần.
2. Xem thông tin, kỹ năng và các thẻ dự án trên trang.
3. Trong phần Liên hệ, nhập họ tên, email hợp lệ và tin nhắn từ 10 đến 500 ký tự.
4. Chọn **Gửi tin nhắn**. Trình duyệt mở ứng dụng email mặc định với người nhận và nội dung được điền sẵn; kiểm tra rồi nhấn **Gửi** trong ứng dụng đó để hoàn tất.

Thông tin liên hệ trên trang được công khai. Biểu mẫu không có dịch vụ gửi thư phía máy chủ và không lưu dữ liệu; việc mở email phụ thuộc ứng dụng email trên thiết bị.

## Phát triển và kiểm tra

- Sửa nội dung, liên kết và ảnh trong `index.html`; chỉnh giao diện trong `style.css`; thay đổi kiểm tra biểu mẫu hoặc hiệu ứng trong `script.js`.
- Ảnh dự án hiện là dữ liệu nhúng trong HTML. Nếu bổ sung nhiều ảnh, cân nhắc tách chúng thành file riêng, nén ảnh và dùng định dạng phù hợp.
- Không có cấu hình package manager, lệnh build hoặc bộ kiểm thử tự động trong các file dự án hiện có.
- Để kiểm tra responsive, dùng công cụ responsive của trình duyệt ở các kích thước như `360 × 800`, `768 × 1024` và `1280 × 900`; kiểm tra menu, nội dung, biểu mẫu và tràn ngang.
- Bộ dữ liệu nhập mẫu cho biểu mẫu nằm trong [test-data/contact-form-cases.txt](./test-data/contact-form-cases.txt). Đây là dữ liệu để nhập thủ công; website không có chức năng đọc file TXT.
- Kiểm tra thủ công bằng trình duyệt ngày 25/11/2026: các trường hợp tên trống/chỉ khoảng trắng, email sai định dạng, tin nhắn 9 ký tự/chỉ khoảng trắng đều bị từ chối và focus đúng trường; bộ đếm tại 10 và 500 ký tự đúng; nhập 501 ký tự bằng bàn phím bị giới hạn ở 500. Không gửi biểu mẫu hợp lệ vì thao tác đó mở ứng dụng email bên ngoài.
- `index.html` có ghi kết quả kiểm thử Playwright ngày 04/11/2026. Đây là ghi chú đã có trong dự án; lần cập nhật tài liệu này không chạy lại kiểm thử đó.

## File TXT

Mã nguồn không đọc file `.txt`; file kiểm thử trong `test-data/` chỉ là bộ dữ liệu mẫu để nhập vào biểu mẫu khi kiểm tra thủ công. Không cần TXT nào khác cho ứng dụng.

## Nhật ký AI

Xem [AI_LOG.md](./AI_LOG.md) để biết phạm vi hỗ trợ AI có thể xác nhận trong phiên cập nhật tài liệu này. Nhật ký không suy diễn lịch sử hỗ trợ AI trước đó hoặc quyền tác giả của mã nguồn.
