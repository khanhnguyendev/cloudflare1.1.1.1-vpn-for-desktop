Tạo Repl workspace
Vào trang https://repl.it/ -> Start coding -> BASH -> Create repl (Như hình minh họa)



Download wgcf tool
Cửa sổ mới xuất hiện, gõ vào vùng màu đen (Terminal) bên phải dòng lệnh như bên dưới và Enter. Dòng lệnh chạy thành công, nhìn vào panel bên trái sẽ thấy có 1 file wgcf xuất hiện

wget -O wgcf https://github.com/ViRb3/wgcf/releases/download/v1.0.5/wgcf_1.0.5_linux_386; chmod +x wgcf


./wgcf


Tạo tài khoản Cloudflare mới
Bây giờ, để thực hiện câu trả lời chính, mình sẽ đi các bước như sau: register -> Copy key từ điện thoại, set vào biến môi trường và chạy câu lệnh update -> chạy lệnh generate để tạo ra Profile của Wiguard -> Copy nội dung đó vào Tool Wireguard -> Xong. Mình sẽ làm các bước liên tục bằng các lệnh và ảnh minh họa. (copy lệnh dưới vào terminal)

./wgcf register


Sau khi chạy lệnh register, bạn sẽ phải chọn YES để accept TOS (Term of Services). Khi hoàn thành, sẽ có một file wgcf-account.toml xuất hiện bên trái, đây là file chứa thông tin account Cloudflare. Ở màn hình đen, bạn cũng sẽ thấy các thông số của account, gồm data còn lại, data đã dùng, loại account (pc/mobile), account type...

Update license key 1.1.1.1 từ điện thoại vào account vừa được tạo
Đây là license key trên mobile của mình (mình xin cover nó lại để tránh bị dùng chung), danh sách devices đang sử dụng chung hiện tại chỉ có mỗi điện thoại của mình

 

Bây giờ các bạn chạy lệnh (copy lệnh dưới vào terminal, thay thế giá trị của WGCF_LICENSE_KEY tương ứng với điện thoại của bạn )

WGCF_LICENSE_KEY="Điền license key từ điện thoại của bạn vào đây" ./wgcf update
Nếu thành công, sẽ hiện ra như sau



Check lại trên phần quản lý devices thì bạn cũng sẽ thấy có thêm ID mới. Trường hợp nếu lỗi ở đây, cái license key của bạn có vấn đề



Tạo Wireguard Profile
Tới bước này rồi thì bạn chỉ cần tạo Wireguard Profile và xài trên máy tính thôi. Chạy lệnh tiếp theo (copy lệnh dưới vào terminal)

./wgcf generate
Khi chạy lệnh này, một file wgcf-profile.conf được sinh ra ở bên trái. Chọn file đó và copy tất cả nội dung của nó

   

Làm sao điểm tra dung lượng còn lại cho account trên máy tính?
Quá đơn giản, chỉ cần gõ

./wgcf status


Mình sẽ quay lại với bài viết hướng dẫn cách tăng dung lượng, đi sâu hơn tí về kĩ thuật :D
