# 该项目应用于企业DNS管理系统、支持AIDNS、智能解析功能

## 支持记录类型: A、MX、 PTR、 NS、 SOA、 TXT、CNAME等

## 安装步骤(仅针对centos/redhat发行版,其他版本自行测试)

1. 安装LnmOS初始化环境<br>
curl -o - 'https://raw.githubusercontent.com/fxtxkktv/fxtxkktv.github.io/master/files/Install_LnmOS_env.sh'|bash <br>

2. 获取主程序<br>
git clone https://github.com/fxtxkktv/lnmDNS.git <br>
进入程序目录 <br>
cd lnmFTP <br>
创建程序独立运行Python环境 <br>
/opt/Py27lnmos/bin/virtualenv -p /opt/Py27lnmos/bin/python venv <br>
进入virtualenv环境 <br>
source venv/bin/activate <br>
DNS服务: [安装lnmOS定制RPM包,可在主页资源包获取](https://github.com/fxtxkktv/fxtxkktv.github.io/tree/master/files/RPM组件包/) <br>
yum install -i bind bind-sdb <br>
安装Python程序扩展包 <br>
pip install -r readme/requirements.txt <br>

3. 创建数据库并恢复数据模版 <br>
[创建数据库]: # mysql -u root -p -e "create database lnmdns" <br>
[恢复数据模版]: # mysql -u root -p ftpdb < readme/db_schema.sql <br>
[配置数据库连接及其他]: # vim config/config.ini <br>

4. 正式运行程序 <br>
[程序调试]：python main.py <br>
[后台运行]: startweb.sh restart <br>
[前段访问]：http://IP地址:端口号 默认用户名：admin 密码: admin<br>

如有问题可直接反馈或邮件master@lnmos.com <br>

## 项目截图
### 系统管理
![其余界面](https://github.com/fxtxkktv/lnmDNS/blob/master/readme/systeminfo.jpg)
### DNS服务
![其余界面](https://github.com/fxtxkktv/lnmDNS/blob/master/readme/dns_domain.jpg)
### 智能DNS
![其余界面](https://github.com/fxtxkktv/lnmDNS/blob/master/readme/dns_aidns.jpg)
### 帮助页面
![其余界面](https://github.com/fxtxkktv/lnmDNS/blob/master/readme/help.jpg)
### 支持捐赠
![其余界面](https://github.com/fxtxkktv/lnmDNS/blob/master/readme/pay.jpg)
