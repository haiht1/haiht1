# Webmin

## Cài Webmin

### B1: Truy cập: 

**https://www.webmin.com/rpm** 

#### Để có thể thực thi lệnh wget cần cài công cụ này.Nhập lệnh sau để cài

`yum install wget`

### B2: Trên linux nhập lệnh dưới để tạo file:

`vi /etc/yum.repos.d/webmin.repo`

#### Nhập nội dung sau :

`[Webmin]`

`name=Webmin Distribution Neutral`

`#baseurl=https://download.webmin.com/download/yum`

`mirrorlist=https://download.webmin.com/download/yum/mirrorlist`

`enabled=1`

`gpgkey=https://download.webmin.com/jcameron-key.asc`

`gpgcheck=1`

#### Lưu và thoát bằng lệnh: **:x!**

### B3: Cài key GPG bằng lệnh dưới:

`wget https://download.webmin.com/jcameron-key.asc`

`rpm --import jcameron-key.asc`

### B4: Nhập lệnh sau để cài webmin
   `yum install perl`
   
   `yum install webmin`

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




   
