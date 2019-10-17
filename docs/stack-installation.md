# Initial Installation

If you have completed the OpenCart deployment on Cloud Platform, the following steps is for you to start use it quikly

## Preparation

1. Get the **Internet IP** on your Cloud Platform
2. Check you **[Inbound of Security Group Rule](https://support.websoft9.com/docs/faq/tech-instance.html)** of Cloud Console to ensure the TCP:80 is allowed
3. Make a domain resolution on your DNS Console if you want to use domain for OpenCart

## OpenCart Installation Wizard

1. Using local Chrome or Firefox to visit the URL *https://domain* or *https://Internet IP*, start to install    
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps01.png)
2. Agree license, Click "Next"
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps02.png)
3. Set your store information and administration account, Click "Next"
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps03.png)
4. Database connection configuration, you can use the MySQL in this Server([Don's know password?](/stack-accounts.html#mysql)), and you can use other database services
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps04.png)
5. Your installation is finished! 
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps05.png)
6. Please delete */data/wwwroot/prestashop/install* folder.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-delinstallftp-websoft9.png)
7. Click "Manage your store" to enter your administration account, Click "Login IN"
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps07.png)
8. This is your administration console
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps08.png)
9. Use *http://IP*  to go to your index page.
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/ps09.png)

> Refer to [OpenCart Docs](https://www.prestashop.com/en/resources/documentations) to get more details

## Connect OpenCart Marketplace

Completed installation of OpenCart, suggest you make your OpenCart system connect OpenCart's Marketplace. Once you have connected it, you can use many resourses on Marketplace.

1. Log in OpenCart Console as administrator
2. Open 【Modules】>【Module Manager】, click【Connect to Addons marketplace】
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-connectmk-websoft9.png)  
3. Register an account if you don't have it
   ![](https://libs.websoft9.com/Websoft9/DocsPicture/zh/prestashop/prestashop-registeraccount-websoft9.png)  
4. Connect to Marketplace using your Marketplace's account
   ![](http://libs.websoft9.com/Websoft9/DocsPicture/en/prestashop/prestashop-marketplace-websoft9.png)

## Q&A

#### I can't visit the start page of OpenCart?

Your TCP:80 of Security Group Rules is not allowed so there no response from Chrome or Firefox

#### Which database does this OpenCart package use?

MySQL

#### Can I use Cloud database for OpenCart?

Yes