# 更新升级

网站技术日新月异，**更新升级**是维护工作之一，长时间不升级的程序，就如长时间不维护的建筑物一样，会加速老化、功能逐渐缺失直至无法使用。  

这里注意更新与升级这两词的差异（[延伸阅读](https://support.websoft9.com/docs/faq/zh/tech-upgrade.html#更新-vs-升级)），例如：  

- 操作系统打个补丁常称之为**更新**，Ubuntu16.04 变更为 Ubuntu18.04，称之为**升级**
- MySQL5.6.25-->MySQL5.6.30 常称之为**更新**，MySQL5.6->MySQL5.7 称之为**升级**

OpenCart 完整的更新升级包括：系统级更新（操作系统和运行环境）和 OpenCart 程序升级两种类型

## 系统级更新

运行一条更新命令，即可完成系统级更新：

``` shell
#For Centos&Redhat
yum update -y

#For Ubuntu&Debian
apt update && apt upgrade -y
```
> 本部署包已预配置一个用于自动更新的计划任务。如果希望去掉自动更新，请删除对应的Cron


## OpenCart 升级

OpenCart 自动备份是通过一个名称为“1-Click Upgrade”的插件实现的，具体步骤如下：

1. 登录 OpenCart 后台，打开【Modules Catalog】，搜索“upgrade”，安装备份插件
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrade001-websoft9.png)
2. 安装完成后，点击“配置”，进入模块设置界面
3. 根据设置建议，将系统置为维护模式（maintenance mode）
4. 点击【Upgrade OpenCart now】按钮，开始升级
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrade002-websoft9.png)
5. 升级过程中首先会下载最新的安装包，受制于网络因素，这个过程可能会比较慢。
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrade003-websoft9.png)
6. 升级过程的例外情况
   - 如果下载新版本这个步骤无法完成，需要多次尝试
   - 若出现 “you don't have permission...ajax-upgradetab.php” 的错误提示，升级失败，暂无解决办法

> 与升级有关的更多方案，请参考官方文档：[OpenCart Backup](https://doc.prestashop.com/display/PS16/Manual+update)

## OpenCart Module 升级

OpenCart 提供了在线插件升级能力

1. 登录 OpenCart 后台，打开【Modules Catalog】
2. 找到需要升级的插件，点击【Upgrade】即可在线升级
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrademodules-websoft9.png)