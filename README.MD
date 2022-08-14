# Webmin

## Cài Virtualmin

### Nhập lệnh để update

`sudo apt update`

#### Để có thể thực thi lệnh wget. Nếu chưa có cần cài công cụ này.Nhập lệnh sau để cài

`sudo apt install wget`

### Nhập lệnh bên dưới để tải Script Vitualmin

`sudo wget wget http://software.virtualmin.com/gpl/scripts/install.sh`

#### Lệnh đăt hostname cho Vituralmin:

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




   
