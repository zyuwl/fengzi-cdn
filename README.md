# cdnfly-kaixin
仅支持CENTOS7

web目录为云端验证文件，请自行搭建

wget https://raw.githubusercontent.com/zyuwl/fengzi-cdn/main/web/web.tar.gz

tar -zxvf web.tar.gz

0.0.0.0改成(自己搭建的验证服务器IP)

vi /etc/hosts

0.0.0.0  auth.cdnfly.cn monitor.cdnfly.cn

主控登录地址为: http://主控IP/
管理员账号和密码： admin/cdnfly
普通用户账号和密码： ceshi/ceshi


v5.1.13主控

curl -fsSL https://raw.githubusercontent.com/zyuwl/fengzi-cdn/main/master.sh -o master.sh && chmod +x master.sh && ./master.sh --es-dir /home/es


宝塔安装法:

curl -fsSL https://raw.githubusercontent.com/zyuwl/fengzi-cdn/main/master.sh -o master.sh && chmod +x master.sh && ./master.sh --es-dir /home/es --no-mysql --mysql-ip 127.0.0.1 --mysql-db 数据库名 --mysql-user 数据库用户名 --mysql-pass 数据库密码 --mysql-port 3306  --with-bt




v5.1.16被控

curl -fsSL https://raw.githubusercontent.com/zyuwl/fengzi-cdn/main/agent.sh -o agent.sh  && chmod +x agent.sh && ./agent.sh --master-ver v5.1.13 --master-ip  --es-ip  --es-pwd 



