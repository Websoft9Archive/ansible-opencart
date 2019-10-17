# 故障处理

此处收集使用 OpenCart 过程中最常见的故障，供您参考

> 大部分故障与云平台密切相关，如果你可以确认故障的原因是云平台造成的，请参考[云平台文档](https://support.websoft9.com/docs/faq/zh/tech-instance.html)

#### OpenCart 重定向错误？

多语言下，重定向错误比较常见。例如：打开您的OpenCart商店中文版会出现重定向

处理办法：
1. 分析网站根目录下的 `.htaccess` 文件，看看有没有死循环规则
2. 进入后台先删除中文，然后再重新导入中文。重新导入的时候，OpenCart会自动生成伪静态规则，覆盖您网站根目录的 `.htaccess` 文件


#### 修改了数据库密码 OpenCart 不能访问？

若已完成 OpenCart 安装向导，再通过 phpMyAdmin 修改数据库密码，OpenCart 就会连不上数据库

需要修改 [OpenCart 配置文件](/zh/stack-components.html#prestashop) 对应的数据库 password 参数即可。

#### Apache httpd 服务无法启动？

请通过分析日志文件定位原因： */var/log/httpd*

#### 网站重定向错误？



#### 数据库服务无法启动

数据库服务无法启动最常见的问题包括：磁盘空间不足，内存不足，配置文件错误。  
建议先通过命令进行排查  

```shell
# 查看磁盘空间
df -lh

# 查看内存使用
free -lh
```

