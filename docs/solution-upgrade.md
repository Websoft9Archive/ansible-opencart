# Update & Upgrade

Updates and upgrades are one of the maintenance tasks for sytem. Programs that are not upgraded for a long time, like buildings that are not maintained for a long time, will accelerate aging and gradually lose functionality until they are unavailable.

You should know the differences between the terms **Update** and **Upgrade**([Extended reading](https://support.websoft9.com/docs/faq/tech-upgrade.html#update-vs-upgrade))
- Operating system patching is **Update**, Ubuntu16.04 to Ubuntu18.04 is **Upgrade**
- MySQL5.6.25 to MySQL5.6.30 is **Update**, MySQL5.6 to MySQL5.7 is **Upgrade**

For OpenCart maintenance, focus on the following two Update & Upgrade jobs

- Sytem update(Operating System and Running Environment) 
- OpenCart upgrade 

## System Update

Run an update command to complete the system update:

``` shell
#For Centos&Redhat
yum update -y

#For Ubuntu&Debian
apt update && apt upgrade -y
```
> This deployment package is preconfigured with a scheduled task for automatic updates. If you want to remove the automatic update, please delete the corresponding Cron

## OpenCart Upgrade

OpenCart provide two methond for Upgrade: OpenCart backend online upgrade and Composer command upgrade  

Below is the step for upgrade online:

## OpenCart Upgrade

Installing the module 【1-Click Upgrade】for OpenCart upgrading online

1. Log in OpenCart console, open【Modules Catalog】, search the module【upgrade】 and install it
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrade001-websoft9.png)
2. Set it when you have completed the installation of this module
3. Set your OpenCart to [maintenance mode](/solution-more.md#prestashop-maintenance-mode)
4. Click【Upgrade OpenCart now】 to start upgrading
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/prestashop-checkupgrade-websoft9.png)
5. The latest installation package will be downloaded first during the upgrade. Due to network factors, this process may be slow.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrade003-websoft9.png)
6. Exceptions to the upgrade process
   - If you can't complete this step to download a new version, you need to try multiple times.
   - May get the error “you don't have permission...ajax-upgradetab.php”

> More upgrade details please refer to: [OpenCart Backup](http://doc.prestashop.com/display/PS16/Manual+update)

## OpenCart Module Upgrade

OpenCart can upgrade the Module online

1. Log in OpenCart as administrator, open【Modules Catalog】
2. Find the module you need to upgrade, click the 【Upgrade】 button
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-upgrademodules-websoft9.png)