# Đổi port trên SSH 22-2022

## Dùng lệnh Vim để mở file chứa cài đặt ssh

`sudo nano /etc/ssh/sshd_config`

## Đổi port 22-> 2022.Sau đó lưu lại.

# Chuyển đổi xác thực SSH bằng Key thay cho mật khẩu

## Dùng lệnh dưới để tạo key rsa

`sudo ssh-keygen -t rsa'

## Hệ thống sẽ hỏi nơi Lưu key điền đường dẫn lưu hoặc Nhấn enter để lưu theo mặc định

## Hệ thống sẽ yêu cầu nhập Passphase .Nhấn enter để rỗng

## Sau đó hệ thống sẽ sinh ra 2 key trên hệ thống là Private Key và Public Key:

## Trên máy mình 2 key đó sẽ nằm trong mục /root/ .ssh/id_rsa. Nhớ lưu lại 2 key này để sử dụng




# Chỉ cho ip tòa nhà Núi thành truy cập ssh: 

 `sudo iptables -I INPUT -p tcp -s xxx.xxx.xxx.xxx -m tcp --dport 22 -j ACCEPT`
 
 # Để đổi hostname
 
 ## Sử dụng lệnh vi mở tập tin
 
 `vi /etc/hosts` 
 
#  Sau đó đổi hostname mới mà bạn muốn.Sau đó lưu và thoát.

# Webmin

# Cài Virtualmin

## Nhập lệnh để update

`sudo apt update`

## Để có thể thực thi lệnh wget. Nếu chưa có cần cài công cụ này.Nhập lệnh sau để cài

`sudo apt install wget`

### Nhập lệnh bên dưới để tải Script Vitualmin

`sudo wget wget http://software.virtualmin.com/gpl/scripts/install.sh`

## Lệnh đặt hostname cho Vituralmin:

`sudo hostnamectl set-hostname xxx.xxx`

## Thay xxx.xxx bằng tên miền của bạn

### Gán quyền thực thi cho tệp install.sh

`sudo chmod a+x install.sh`

### Chạy lệnh cài đặt Webmin và Virtual:

   `sudo ./install.sh`
   
## Hệ thống sẽ hỏi bạn nhập y 2 lần 

## Đợi hệ thống tải và cài đặt các package hoàn tất.

# Cấu hình firewall với UFW để giới hạn các cổng được phép kết nối

## Sử dụng lệnh sau để xem trạng thái UFW

`sudo ufw status`

## Sử dụng lệnh sau để kích hoạt UFW

`sudo ufw enable`

## Mở cổng 

`sudo ufw allow 80/tcp`

## Đóng cổng

`sudo ufw deny 80/tcp`

## Cho phép IP truy cập đến cổng nhất định  
 
 `sudo ufw allow from 192.168.0.1 to any port 22`
 
## Từ chối IP truy cập đến cổng nhất định  

`sudo ufw deny from 192.168.0.1 to any port 22`

## Hiện các rule đã set up theo danh sách

`sudo ufw status numbered'

## Xóa 1 rule

`sudo ufw delete 7`

## Mở cổng theo phạm vi 

`sudo ufw allow 35000:35999/tcp`

## Đóng cổng theo phạm vi 

`sudo ufw deny 35000:35999/tcp`

## Cho phép IP truy cập 

`sudo ufw allow from 103.15.48.131`

## Từ chối IP truy cập 

`sudo ufw deny from 103.15.48.131`

## Nếu cần mở IPv6 trên UFW

`sudo vim /etc/default/ufw`

### Sau đó đổi IPV6=no -> IPV6=yes

# Thay đổi múi giờ 

## Nhập lệnh để xem định dạng thời hiện tại trên hệ thống

`sudo timedatectl`

## Để xem danh sách múi giờ

`sudo timedatectl list-timezones`

## Thay đổi timezone

`sudo timedatectl set-timezone Asia/Ho_Chi_Minh`

#
