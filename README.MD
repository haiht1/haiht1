#    LAB LINUX 


## I.Đổi port trên SSH 22 -> 2022

| Dùng lệnh Vim để mở file chứa cài đặt ssh | `sudo vim /etc/ssh/sshd_config` |
|-------------------------------------------|---------------------------------|
| Đổi port 22-> 2022 | Sau đó lưu lại |


## II.Chuyển đổi xác thực SSH bằng Key thay cho mật khẩu

| Dùng lệnh dưới để tạo key rsa | `sudo ssh-keygen -t rsa` |
|-------------------------------|--------------------------|
| Hệ thống sẽ hỏi nơi Lưu key | Điền đường dẫn hoặc Nhấn enter để lưu theo mặc định |
| Hệ thống sẽ yêu cầu nhập Passphase | Nhấn enter để rỗng |
| Sau đó hệ thống sẽ sinh ra 2 key trên hệ thống: | Private Key và Public Key |
| Trên máy mình 2 key đó sẽ nằm trong mục /root/ .ssh/id_rsa | Nhớ lưu lại 2 key này để sử dụng |
| Private Key chứa trong file ~/.ssh/id_rsa | Public Key chứa trong file ~/.ssh/id_rsa.pub |
| Mở file config của SSH Service ra | /etc/ssh/sshd_config và điều chỉnh thành |
| `PubkeyAuthentication | `yes` |
| `AuthorizedKeysFile | .ssh/authorized_keys`|
| Lưu Private key trên máy user theo đường dẫn | /home/abc/.ssh/authorized_keys(Linux) C:\Users\abc\.ssh\authorized_keys trên (windows) |



# III.Chỉ cho ip tòa nhà Núi thành truy cập ssh: 

 |Lệnh set IP: | `sudo iptables -I INPUT -p tcp -s 118.69.62.113 -m tcp --dport 22 -j ACCEPT`| 
 |-------------|-----------------------------------------------------------------------------|
 
## IV.Để đổi hostname
 
| Sử dụng lệnh vi mở tập tin | `vim /etc/hosts` |
|----------------------------|------------------|
| Sau đó đổi hostname mới mà bạn muốn | Sau đó lưu và thoát |

## V.Cài Webmin & Virtualmin

###  1.Nhập lệnh để update

`sudo apt update`

###   1.2.Để có thể thực thi lệnh wget. Nếu chưa có cần cài công cụ này.Nhập lệnh sau để cài

`sudo apt install wget`

###  2.Nhập lệnh bên dưới để tải Script Vitualmin

`sudo wget wget http://software.virtualmin.com/gpl/scripts/install.sh`

###  2.2Lệnh đặt hostname cho Vituralmin:

`sudo hostnamectl set-hostname haiht.tk`

###  3.Gán quyền thực thi cho tệp install.sh

`sudo chmod a+x install.sh`

###  4.Chạy lệnh cài đặt Webmin và Virtual:

   `sudo ./install.sh`
   
###  4.1.Hệ thống sẽ hỏi bạn nhập y 2 lần 

###  5.Đợi hệ thống tải và cài đặt các package hoàn tất.


## Cấu hình Vituralmin



###  1.Trên máy user, để vào được giao diện webmin: mở trình duyệt nhập đường dẫn:

`192.168.75.131:10000`

###  2.Sẽ xuất hiện giao diện đăng nhập Webmin

###  3.Dùng user và password(mặc định là tài khoản và password user root để đăng nhập

###  4.Sau đó bắt đầu cấu hình cho Virtualmin

###  5.Click Next
 
###   5.1.Preload Libraries :( tải trước thư viện) chọn có nếu RAM trên 2GB

###      Run email domain look up : máy chủ tra cứu tên  miền
 
###   5.2.Scan Viruss với ClAV : bật quét virus 


## Mục 3 :

### MySQL :chạy dữ liệu MySQL

### Postpre SQL : chạy với dữ liệu Postpre SQL

## Mục 4 : 

### Set password MySQL: đặt mật khẩu cho My SQL

## Mục 6 : 

### Set password MySQL: đặt mật khẩu cho My SQL

## Mục 5 : 

### Config My SQL size : điều chỉnh SQL để tăng hiệu xuất (Tùy thuộc theo RAM)

## Mục 7 : 

## Primary Nameserver: Cấu hình DNS chọn Skip check để thiết lập sau

## Mục 8 : 

## Password Storage  chọn loại lưu trữ mật khẩu dạng text hoặc được mã hóa

## Mục 9 :

## Setup Default Virtual Server : ùy chọn tạo mới máy chủ ảo mặc định,tick chọn no sau đó sẽ tự tạo máy chủ sau

## Mục 10: 

## Recheck and refresh configuration : hệ thống sẽ kiểm tra lại các thông tin và các cài đặt và làm reset lại 

# Tạo 1 Virtualmin Server:

## Chọn Create Server để tạo mới Virtual Server

## Điền thông tin và điều chỉnh các mục sau:

## Domain name: nhập vào tên miền đã được trỏ IP về VPS Ubuntu

## Administration passwords:  hập mật khẩu đã tạo với MySQL

## Administration username: họn Custom username và nhập vào tên miền 

## Sau đó chọn Create Server để tạo mới Virtual Server

# Cài Wordpress

## Download mã nguồn wordpress tại trang:

`https://wordpress.org/`

## Sau khi download source cài đặt WordPress về máy, các bạn hãy upload lên theo đường dẫn như ảnh, rồi giải nén và paste hết vào thư mục /Public_html

## Truy cập trên trình duyệt bằng IP VPS để bắt đầu cài Wordpress










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

