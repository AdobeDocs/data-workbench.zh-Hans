---
description: 在IIS中部署功能板的步骤。
title: 部署功能板
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# 部署功能板{#deploying-the-dashboard}

在IIS中部署功能板的步骤。

1. 创建安装文件夹以安装功能板，如[!DNL c:\inetpub\wwwroot\dashboard]。
1. 在IIS中创建功能板的应用程序池。
1. 打开IIS管理器控制台。
1. 转到 **[!UICONTROL Application Pools]** 。
1. 在右侧的&#x200B;**[!UICONTROL Actions]**&#x200B;菜单中选择**[!UICONTROL Add Application Pool…]**。
1. 在&#x200B;**[!UICONTROL Add Application Pool]**&#x200B;窗体中，使用功能板作为名称，然后选择.NET Framework v.4.0.xxxxxx作为您的.NET Framework版本。
1. 将其他字段保留为默认字段，然后单击&#x200B;**[!UICONTROL OK]**&#x200B;以创建应用程序池。
1. 部署功能板应用程序。
1. 打开IIS管理器控制台。
1. 展开&#x200B;**[!UICONTROL Default Web Site]**，您应会看到在c:\inetpub\wwwroot\dashboard by default中创建的文件夹。
1. 右键单击文件夹并选择&#x200B;**[!UICONTROL Convert to Application]**。
1. 选择在步骤2中创建的**[!UICONTROL Application Pool]**（例如，“功能板”）。
1. 在&#x200B;**[!UICONTROL Sites]**&#x200B;下，右键单击要部署的网站（例如，“默认网站”）。
1. 选择 **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. 浏览并选择由Adobe提供的功能板部署文件。
1. 单击&#x200B;**[!UICONTROL Next]**&#x200B;两次以继续进入“Enter Application Information（输入应用程序信息）”屏幕。
1. 在此屏幕中，您可以选择自定义功能板部署。
1. 对于&#x200B;**[!UICONTROL Application Path]**，输入先前选择的文件夹名称。
1. 在&#x200B;**[!UICONTROL Disable Automatic Database Upgrade]**&#x200B;下，输入`False`，因为这是新安装。
1. 根据需要自定义连接字符串。 例如：

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. 单击&#x200B;**[!UICONTROL Next]**,IIS将开始安装应用程序。
1. 安装完成后，安装日志中应不显示任何错误。
