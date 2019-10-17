# 更多...

下面每一个方案，都经过实践证明行之有效，希望能够对你有帮助

## 域名绑定

绑定域名的前置条件是：已经完成域名解析（登录域名控制台，增加一个A记录指向服务器公网IP）  

完成域名解析后，从服务器安全和后续维护考量，需要完成**域名绑定**：

OpenCart 域名绑定操作步骤：

1. 使用 SFTP 工具登录云服务器
2. 修改 [虚拟机主机配置文件](/zh/stack-components.html#apache)，将其中的域名相关的值
   ```text
   #### OpenCart(LAMP) bind domain #### 

     <VirtualHost *:80>
     ServerName  www.mydomain.com # 修改成您的实际域名
     DocumentRoot "/data/wwwroot/prestashop"
     ...
     
   #### OpenCart(LNMP) bind domain #### 

     server {
      listen 80;
      server_name prestashop.example.com; # 修改成您的实际域名
     ...

   ```
3. 保存配置文件，[重启服务](/zh/admin-services.html#apache)

## OpenCart 维护模式

登录 OpenCart 后台，打开：【Shop Parameters】>【General】>【Maintenance】，设置维护模式
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-mantmode-websoft9.png)


## OpenCart 更换域名

如果 OpenCart 需要更换域名，具体操作如下：

1. 完成域名解析和域名绑定
2. 将 OpenCart 设置为维护模式
3. 打开 OpenCart 的配置文件（[路径参考](/zh/stack-components.html#prestashop)），修改其中与域名有关的内容
4. 登录 OpenCart 后台，打开：【Shop Parameters】>【Traffic&SEO】，修改它
  ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-seturl-websoft9.png)

## OpenCart 导入数据

登录 OpenCart 后台，打开：【Advanced Parameters】>【Import】，导入所需的数据
![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-importdb-websoft9.png)


## OpenCart Modules

Modules 是 OpenCart 功能扩展，Modules 可以即插即用

1. 登录 OpenCart 后台，
2. 依次打开：【Modules】>【Module Catalog】，找到所需的插件，点击【Install】开始安装
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-installmd-websoft9.png)
3. 依次打开：【Modules】>【Module Manager】，找到所需的插件，点击【Upgrade】即可在线升级
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrademodules-websoft9.png)

## OpenCart 连接 Marketplace

除了系统提供 Modules 之外，更多的 Modules 都是通过 Marketplace 发布，因此需要将你的 OpenCart 连接到 Marketplace，便可以在线使用上面的资源。

具体操作步骤参考：[连接 Marketplace](/zh/stack-installation.html#连接-prestashop-marketplace)



## OpenCart 语言包

OpenCart的多语言支持非常的成熟，系统在后台内置一套多语言体系，只需要选择对应的语言，在线导入到您的 OpenCart 系统即可。

### 导入语言

1. 登录OpenCart后台，依次打开：【国际】>【本地化】，进入设置界面
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-setlanguage-websoft9.png)
2. 选择一个语言包，点击本项之右下角【上传】图标，完成在线导入
3. 选择【语言】选项卡，我们就可以看到成功导入的语言包
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-alllanguage-websoft9.png) 

> 每次导入一个新的语言包，系统会自动为此语言生成一个伪静态规则。如果您的某个语言的伪静态设置出现问题导致了 Redirect（重定向），可以删除这个语言，然后重新导入一次即可。

### 删除语言

1. 登录OpenCart后台，依次打开：【国际】>【本地化】>【语言】，编辑您需要的语言
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-dellanguage001-websoft9.png)
2. 将语言的状态修改为“否”，然后保存
3. 回到【语言】选项开，找到已经打叉的语言，删除之即可
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-dellanguage002-websoft9.png)

## OpenCart API (Web Service)

OpenCart enables merchants to give third-party tools access to their shop's database through a CRUD API, otherwise called a web service.

参考官方文档：https://doc.prestashop.com/display/PS16/Using+the+OpenCart+Web+Service