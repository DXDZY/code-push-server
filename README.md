# 热更新服务器配置
使用[code-push-server](https://github.com/lisong/code-push-server)替换微软[react-native-code-push]([react-native-code-push](https://link.jianshu.com/?t=https%3A%2F%2Fgithub.com%2FMicrosoft%2Freact-native-code-push)
)
1. 安装code-push-server
`npm install code-push-server -g`
2. 安装mysql
* 如果没安装先下载安装[mysql](https://pan.baidu.com/s/1OI8XmHLCr0j4WC20YZbiYw)`密码: 9ya6`
* 启动`mysql`>`系统`>`偏好设置`
* 配置环境变量，按照这个[配置方法](https://jingyan.baidu.com/article/a378c960b8f828b328283033.html)即可
* 配置好后，在终端输入`mysql`，如果提示
`Access denied for user 'root'@'localhost' (using password: NO)`
* `mysql -u root -p`之后会让你输入安装`mysql`时输入的密码，密码输入后即可输入`mysql`进入，输入`exit`退出
3. 初始化mysql数据库
* mysql配置好后在终端输入
`code-push-server-db init --dbhost localhost --dbuser root --dbpassword 密码`
如果提示错误
`Client does not support authentication protocol requested by server`
```
mysql -u root -p
USE mysql;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '密码';
FLUSH PRIVILEGES;
```
4. 从[code-push-server](https://github.com/lisong/code-push-server)下载服务
5. 配置config文件
![config/config.js](https://upload-images.jianshu.io/upload_images/7999439-aaee2dd1e1a5dd0c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![config/config.js](https://upload-images.jianshu.io/upload_images/7999439-26988a1cfcb1fa42.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
6. 启动服务
`npm start`
7. 登陆
```
//默认用户名密码为：admin|123456
code-push login http://127.0.0.1:3000
```
8. 获取token后，即可登陆。
9. 登出
```
code-push logout
```
***
参考文档：
[配置环境变量](https://jingyan.baidu.com/article/a378c960b8f828b328283033.html)
[code-push-server](https://github.com/lisong/code-push-server)
***

