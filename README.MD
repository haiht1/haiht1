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
| `PubkeyAuthentication` | `yes` |
| `AuthorizedKeysFile` | .ssh/authorized_keys`|
| Lưu Private key trên máy user theo đường dẫn | /home/abc/.ssh/authorized_keys(Linux) C:\Users\abc\.ssh\authorized_keys trên (windows) |



# III.Chỉ cho ip tòa nhà Núi thành truy cập ssh: 

 |Lệnh set IP: | `sudo iptables -I INPUT -p tcp -s 118.69.62.113 -m tcp --dport 22 -j ACCEPT`| 
 |-------------|-----------------------------------------------------------------------------|
 
## IV.Để đổi hostname
 
| Sử dụng lệnh vi mở tập tin | `vim /etc/hosts` |
|----------------------------|------------------|
| Sau đó đổi hostname mới mà bạn muốn | Sau đó lưu và thoát |

## V.Cài Webmin & Virtualmin

| Nhập lệnh để update | `sudo apt update` |
|---------------------|-------------------|
| Để có thể thực thi lệnh wget.Nhập lệnh sau để cài |`sudo apt install wget` |
| Lệnh để tải Script Vitualmin | `sudo wget wget http://software.virtualmin.com/gpl/scripts/install.sh` |
|Lệnh đặt hostname cho Vituralmin | `sudo hostnamectl set-hostname haiht.tk` |
|Gán quyền thực thi cho tệp install.sh | `sudo chmod a+x install.sh` 
| Cài đặt Webmin và Virtual | `sudo ./install.sh` |
| Hệ thống sẽ hỏi bạn | Nhập y 2 lần |

## Cấu hình Vituralmin

| Mở trình duyệt nhập đường dẫn | `192.168.75.131:10000` |
|-------------------------------|------------------------|
| Sẽ xuất hiện giao diện đăng nhập Webmin | Nhập user và password(user và pwd user root) |
| Sau đó bắt đầu cấu hình cho Virtualmin | Click Next | 
| Preload Libraries :( tải trước thư viện)| chọn có nếu RAM trên 2GB |
| Run email domain look up : máy chủ tra cứu tên  miền |tùy theo |
|Scan Viruss với ClAV : bật quét virus | nên chon không |
| MySQL :chạy dữ liệu MySQL | chọn có |
| Postpre SQL : chạy với dữ liệu Postpre SQL | chọn không |
| Set password MySQL | đặt mật khẩu cho My SQL |
| Config My SQL size | điều chỉnh size SQL để tăng hiệu xuất (Tùy thuộc theo RAM) |
| Primary Nameserver |Cấu hình DNS chọn Skip check để thiết lập sau |
| Password Storage  chọn loại lưu trữ mật khẩu dạng text hoặc được mã hóa | chọn 1 trong 2 |
| Setup Default Virtual Server : Tùy chọn tạo mới máy chủ ảo mặc định| chọn no sau đó sẽ tự tạo máy chủ sau |
| Recheck and refresh configuration | hệ thống sẽ kiểm tra lại các thông tin và các cài đặt và làm reset lại |

# Tạo 1 Virtualmin Server:

| Chọn Create Server để tạo mới Virtual Server|   |
|---------------------------------------------|---|
| Domain name | nhập vào tên miền đã được trỏ IP về VPS |
| Administration passwords | Nhập mật khẩu đã tạo với MySQL |
| Administration username | Chọn Custom username và nhập vào tên miền |
| Chọn Create Server | để tạo mới Virtual Server |

# Cài Wordpress

| Download mã nguồn wordpress tại trang | https://wordpress.org |
|---------------------------------------|-----------------------|
| Sau khi download source cài đặt WordPress & giải nén, paste hết vào thư mục | /Public_html |
| Truy cập trên trình duyệt bằng IP VPS | để bắt đầu cài Wordpress |

# Cấu hình firewall với UFW để giới hạn các cổng được phép kết nối

| Lệnh  để xem trạng thái UFW | `sudo ufw status` |
|-----------------------------|-------------------|
| Sử dụng lệnh sau để kích hoạt UFW | `sudo ufw enable` |
| Mở cổng | `sudo ufw allow 80/tcp` |
| Đóng cổng ||`sudo ufw deny 80/tcp` |
| Cho phép IP truy cập đến cổng nhất định | `sudo ufw allow from 192.168.0.1 to any port 22` |
| Từ chối IP truy cập đến cổng nhất định | `sudo ufw deny from 192.168.0.1 to any port 22` |
| Hiện các rule đã set up theo danh sách | `sudo ufw status numbered`|
| Xóa 1 rule |`sudo ufw delete 7` |
| Mở cổng theo phạm vi | `sudo ufw allow 35000:35999/tcp` |
| Đóng cổng theo phạm vi |`sudo ufw deny 35000:35999/tcp` |
| Cho phép IP truy cập | `sudo ufw allow from 103.15.48.131` |
| Từ chối IP truy cập | `sudo ufw deny from 103.15.48.131` |
| Nếu cần mở IPv6 trên UFW | `sudo vim /etc/default/ufw` |
| Đổi IPV6=no -> | IPV6=yes |

# Thay đổi múi giờ 

| Nhập lệnh để xem định dạng thời hiện tại trên hệ thống | `sudo timedatectl` |
|--------------------------------------------------------|--------------------|
| Để xem danh sách múi giờ | `sudo timedatectl list-timezones` |
| Thay đổi timezone | `sudo timedatectl set-timezone Asia/Ho_Chi_Minh` |

# Các lỗi đã xảy ra trong quá trình cài đặt

### 1. Lỗi đăng nhập bằng SSH  

img src="(https://imgur.com/rLEw1VV)"

**Giải pháp phân quyền lại các đường dẫn và các tập tin chứa key**

### 2. Lỗi thiếu cập nhật hoặc lỗi hệ thống thiếu các package cần thiết

img src="(https://imgur.com/F5gf4vb)"

**Giải pháp upadate lại hệt thống hoặc cài lại hệ điều hành nếu không khắc phục được qua update**
