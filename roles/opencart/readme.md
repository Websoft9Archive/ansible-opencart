# Opencart

## 说明
此项目是用Ansible编写的Opencart自动安装程序.

## 安装基础环境

### 基础环境要求

官方对基础环境的最低要求建议如下：
~~~
Web Server (Apache suggested)
PHP (at least 5.4)
Curl enabled
Database (MySQLi suggested)
~~~

基于官方的要求，本程序仅适用于Websoft9的基础环境，包括：

* LAMP
* LNMP（暂时不支持）

本程序在php7.0,mysql5.6下测试运行正常

### 适用于的操作系统

* CentOS7.X
* Ubuntu（暂时不支持）

### 服务器配置要求

* 建议最低配置1核1G


## 源码包

目前提供Opencart官方原版（含中文语言包）、成都光大网络版两个版本，通过修改下载链接进行区分


### 版本
1. Opencart官方版当前源码包版本为：V3.0.3.1，下载地址：https://www.opencart.com/index.php?route=cms/download ，
2. Opencart光大网络版是包含了中英文的本地版本，有大量的修，当前版本是V3.0，基于官方原版3.0.2.1基础上匠心二次开发而来。下载地址：https://www.opencart.cn/download

### 其他说明
Opencart官方安装包和光大网络的源码解压后的路径是：opencart/upload，因此Ansible下载到服务器之后还需要将源码移动到opencart目录下面


## 用户体验改进

### 数据库随机root密码
1. 数据库root账号的随机密码存放在txt文件中（暂未实现）
2. 

### 免数据库配置

暂未实现


### 默认安装中文语言包方案
1. 手工打包中文语言包，名称为opencart,其中包含admin,catalog,install三个包，上传到OSS
2. Ansible程序给roles设置一个语言变量。使用方法：language: cn 即额外再预装一个中文语言包 
3. Ansible程序修改intall目录下的opencart.sql文件，插入语言表的第二行简体中文项（见下）
~~~
INSERT INTO `oc_language` (`language_id`, `name`, `code`, `locale`, `image`, `directory`, `sort_order`, `status`) VALUES
(1, 'English', 'en-gb', 'en-US,en_US.UTF-8,en_US,en-gb,english', 'gb.png', 'english', 1, 1),
(2, ' 简体中文', 'zh-cn', 'zh_CN.UTF-8,zh_CN,zh-cn,china', 'cn.png', 'zh-CN', 1, 1);
~~~

---

## 日志
### 2019-01-16
