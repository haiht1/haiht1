###### Webmin

# Cài Webmin

# B1: Truy cập: 

**https://www.webmin.com/rpm** 

### Để có thể thực thi lệnh wget cần cài công cụ này.Nhập lệnh sau để cài

`yum install wget`

# B2: Tren linux nhập lệnh dưới để tạo file:

`vi /etc/yum.repos.d/webmin.repo`

# Nhập nội dung sau :

`[Webmin]`

`name=Webmin Distribution Neutral`

`#baseurl=https://download.webmin.com/download/yum`

`mirrorlist=https://download.webmin.com/download/yum/mirrorlist`

`enabled=1`

`gpgkey=https://download.webmin.com/jcameron-key.asc`

`gpgcheck=1`

# Lưu va thoát bằng lệnh: **:x!**

# B3: Cài key GPG băng lệnh dưới:

`wget https://download.webmin.com/jcameron-key.asc`

`rpm --import jcameron-key.asc`

# B4: Nhập lệnh sau để cài webmin
   `yum install perl`
   
   `yum install webmin`
