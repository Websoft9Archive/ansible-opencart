# 故障处理

此处收集使用 OpenCart 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### OpenCart 重定向错误？

多语言下，重定向错误比较常见。例如：打开您的OpenCart商店中文版会出现重定向

处理办法：
1. 分析网站根目录下的 `.htaccess` 文件，看看有没有死循环规则
2. 进入后台先删除中文，然后再重新导入中文。重新导入的时候，OpenCart会自动生成伪静态规则，覆盖您网站根目录的 `.htaccess` 文件

####  域名配置后，会出现“页面布局混乱或图片无法显示”？

如果先通过 IP 安装，再绑定域名，就会出现这个问题，请分别打开 OpenCart 的[配置文件](/zh/stack-components.html#opencart)，将其中的IP地址改成域名。

#### 安装插件，显示403权限不足，错误"you dont have permession to access /admin/index.php"

修改文件：/etc/httpd/conf.d/mod\_evasive.conf 中  DOSPageCount 2 改为 DOSPageCount 12

#### 修改了数据库密码 OpenCart 不能访问？

若已完成 OpenCart 安装向导，再通过 phpMyAdmin 修改数据库密码，OpenCart 就会连不上数据库  

需要修改 [OpenCart 配置文件](/zh/stack-components.html#opencart) 对应的数据库 password 参数即可。

#### Apache httpd 服务无法启动？

请通过分析日志文件定位原因： */var/log/httpd*

#### 代码500错误？

通过日志文件找到出问题的代码，下面是一个范例：

```
[Sun Jan 26 07:13:47.606086 2020] [:error] [pid 20341] [client 35.229.42.198:47877] PHP Fatal error:  Uncaught Error: Class 'FacebookCommonUtils' not found in /data/wwwroot/default/storage/modification/catalog/controller/common/header.php:6\nStack trace:\n#0 /data/wwwroot/default/storage/modification/system/engine/action.php(79): ControllerCommonHeader->index(Array)\n#1 /data/wwwroot/default/storage/modification/system/engine/loader.php(48): Action->execute(Object(Registry), Array)\n#2 /data/wwwroot/default/storage/modification/catalog/controller/common/home.php(24): Loader->controller('common/header')\n#3 /data/wwwroot/default/storage/modification/system/engine/action.php(79): ControllerCommonHome->index()\n#4 /data/wwwroot/default/opencart/catalog/controller/startup/router.php(25): Action->execute(Object(Registry))\n#5 /data/wwwroot/default/storage/modification/system/engine/action.php(79): ControllerStartupRouter->index()\n#6 /data/wwwroot/default/storage/modification/system/engine/router.php(108): Action->execute(Object(Registry))\n#7 /data/wwwroot/default/storage/modification/system/engine/router.php(97): Router- in /data/wwwroot/default/storage/modification/catalog/controller/common/header.php on line 6

```

如果是扩展（插件）问题，建议重新下载插件然后通过SFTP上传到Opencart文件夹，再测试问题是否解除

#### 数据库服务无法启动

数据库服务无法启动最常见的问题包括：磁盘空间不足，内存不足，配置文件错误。  
建议先通过命令进行排查  

```shell
# 查看磁盘空间
df -lh

# 查看内存使用
free -lh
```

