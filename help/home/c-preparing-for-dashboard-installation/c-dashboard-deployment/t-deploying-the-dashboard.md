---
description: 在IIS中部署仪表板的步骤。
solution: Analytics
title: 部署控制板
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 部署控制板{#deploying-the-dashboard}

在IIS中部署仪表板的步骤。

1. 创建安装文件夹以安装功能板，如 [!DNL c:\inetpub\wwwroot\dashboard]。
1. 在IIS中创建功能板的应用程序池。
1. 打开IIS Manager控制台。
1. 转到 **[!UICONTROL Application Pools]** 。
1. 在右侧的菜单中选[!UICONTROL Add Application Pool…]**[!UICONTROL Actions]** 择****。
1. 在表 **[!UICONTROL Add Application Pool]** 单中，使用功能板作为名称，并选择。NET Framework v.4.0.xxxxxx作为。NET Framework版本。
1. 将其他字段保留为默认字段，然 **[!UICONTROL OK]** 后单击以创建应用程序池。
1. 部署仪表板应用程序。
1. 打开IIS Manager控制台。
1. 展开 **[!UICONTROL Default Web Site]**&#x200B;文件夹，您应当看到您在c:\inetpub\wwwroot\dashboard by default中创建的文件夹。
1. 右键单击文件夹并选择 **[!UICONTROL Convert to Application]**。
1. 选择在步骤2中创建的**[!UICONTROL Application Pool]**（例如，“功能板”）。
1. 在 **[!UICONTROL Sites]**&#x200B;下，右键单击要部署的网站（例如，“默认网站”）。
1. 选择 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. 浏览至Adobe提供的仪表板部署文件并选择该文件。
1. 单击 **[!UICONTROL Next]** 两次以继续进入“输入应用程序信息”屏幕。
1. 从此屏幕中，您可以选择自定义功能板部署。
1. 对于 **[!UICONTROL Application Path]**，输入之前选择的文件夹名称。
1. 在下 **[!UICONTROL Disable Automatic Database Upgrade]**&#x200B;面，输 `False`入，因为这是新安装。
1. 根据需要自定义您的连接字符串。 例如：

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. 单击 **[!UICONTROL Next]** 后，IIS将开始安装该应用程序。
1. 安装完成后，安装日志中不会显示任何错误。
