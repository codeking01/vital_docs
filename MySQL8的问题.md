## 1.通过mysql的msi自动安装时候（日志里），出现无法启动服务

报错如下

> Retry 1: Attempting to connect to Mysql@localhost:3306 with user root with no password...
> Unknown error: 发生一个或多个错误。

解决：

1. 打开服务找到mysql服务
   
   右击属性，找到登陆选项，将登录身份改成本地系统账户，并且允许服务和桌面交互

## 2.安装好无法启动服务

> 1.找到mysql服务的bin文件，然后将它配置到环境变量中去
> 
> 2.也可能是因为没有启动服务，用管理员身份打开cmd，然后输入 
> 
> net start MySQL80

## 3.输入密码报错，无法进入mysql交互

> 这个原因应该是mysql8新特性的原因，它存在加密
> 
> 解决方案：重置密码
> 
> cmd输入：mysqladmin -u root password 123456
> 
> - 如果你想给root账号授权，你可以在命令行输入mysql -u root -p，然后输入正确的密码，进入mysql控制台。然后输入grant all privileges on *.* to ‘root’@‘localhost’ with grant option;来给root账号赋予所有权限。
