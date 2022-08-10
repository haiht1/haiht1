###### Webmin
# Cai Webmin

# Buoc 1: Truy cập: 

**https://www.webmin.com/rpm** 

# Buoc 2: Tren linux nhap lenh duoi de tao file:
`vi /etc/yum.repos.d/webmin.repo`
Nhap noi dung nhu sau:

'[Webmin]'
`name=Webmin Distribution Neutral`
`#baseurl=https://download.webmin.com/download/yum`
`mirrorlist=https://download.webmin.com/download/yum/mirrorlist`
`enabled=1`
`gpgkey=https://download.webmin.com/jcameron-key.asc`
`gpgcheck=1`

# Luu va thoat bang lenh: **:x!**

# Buoc 3: Cai key GPG bang lenh duoi:

`wget https://download.webmin.com/jcameron-key.asc`
`rpm --import jcameron-key.asc`

# Buoc4: Nhap lenh sau de cai webmin
   `yum install perl`
   `yum install webmin`
