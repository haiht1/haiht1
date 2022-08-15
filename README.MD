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
 
##  Sau đó đổi hostname mới mà bạn muốn.Sau đó lưu và thoát.

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






   
