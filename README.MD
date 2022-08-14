# Đổi port trên SSH 22-2022

#### Dùng lệnh Vim để mở file chứa cài đặt ssh

`sudo nano /etc/ssh/sshd_config`

##### Đổi port 22-> 2022.Sau đó lưu lại.

# Chuyển đổi xác thực SSH bằng Key thay cho mật khẩu

## Dùng lệnh dưới để tạo key rsa

`sudo ssh-keygen -t rsa'

## Hệ thống sẽ hỏi nơi Lưu key điền đường dẫn lưu hoặc Nhấn enter để lưu theo mặc định

## Hệ thống sẽ yêu cầu nhập Passphase .Nhấn enter để rỗng

## Sau đó hệ thống sẽ sinh ra 2 key trên hệ thống là Private Key và Public Key:

## trên máy mình 2 key đó sẽ nằm trong mục /root/ .ssh/id_rsa. Nhớ lưu lại 2 key này để sử dụng







# chỉ cho ip tòa nhà Núi thành truy cập ssh: 

 iptables -I INPUT -p tcp -s xxx.xxx.xxx.xxx -m tcp --dport 22 -j ACCEPT`

# Webmin

## Cài Virtualmin

### Nhập lệnh để update

`sudo apt update`

#### Để có thể thực thi lệnh wget. Nếu chưa có cần cài công cụ này.Nhập lệnh sau để cài

`sudo apt install wget`

### Nhập lệnh bên dưới để tải Script Vitualmin

`sudo wget wget http://software.virtualmin.com/gpl/scripts/install.sh`

#### Lệnh đặt hostname cho Vituralmin:

`sudo hostnamectl set-hostname demo.how2shout.com`

#### Thay demo.how2shout.com bằng tên miền của bạn

### Gán quyền thực thi cho tệp install.sh

`sudo chmod a+x install.sh`

### Chạy lệnh cài đặt Webmin và Virtual:

   `sudo ./install.sh`

### B5: Để khởi động webmin dùng lệnh:

   `# service webmin start`
   
####   Để bật Webmin khi khởi động hệ thống, hãy sử dụng lệnh sau:

   `# chkconfig webmin on`
 
#### Hoặc:

`systemctl webmin.service`

#### B6: Để có thể sử dụng webmin ta cần có 1 trình duyệt

##### Ở đây tôi cài Chrome.Để tải gói cài đặt ta sử dụng lệnh

`wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm`

#### Sau đó dùng lệnh sau để cài đặt:

`yum install ./google-chrome-stable_current_x86_64.rpm`




   
