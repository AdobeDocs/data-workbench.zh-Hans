---
description: 将Data Workbench与Adobe Target集成。 导出数据区段并自动填充导出文件。
title: Data Workbench 与 Adobe Target 集成
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench 与 Adobe Target 集成

使用Data Workbench功能导出数据区段并自动填充导出文件，可更轻松地将AdobeData Workbench与Adobe Target集成。

AdobeData Workbench提供与Adobe Target的闭环集成，用于共享数据和生成报告。 在Data Workbench中，您可以使用所有可用数据分析群体中有意义的区段，包括通过电话、商店等渠道进行离线转化。

例如，访客在您的网站上查找鞋，但未进行转化。 相反，访客下载的优惠券可在下次购买时优惠20%，然后在您的商店购买衬衫。 使用Data Workbench，您可以收集该数据，然后将该配置文件数据推回Target，以显示访客在线购买了衬衫。 然后，您可以定位向该访客提供领带的营销活动，通常Target可能会尝试向该访客重新营销鞋。

## 使用Adobe Target设置Data Workbench

1. 在[!UICONTROL Detail Table]窗口中右键单击标题。

   ![](assets/insight-to-tnt.png)

1. 选择&#x200B;**[!UICONTROL New Target Export]** ，然后在菜单的&#x200B;**[!UICONTROL Save As]**&#x200B;命令下输入新导出文件的名称。

1. 单击 **[!UICONTROL Save Export File]**。

   将打开导出模板窗口。

   所有Adobe Target信息都会自动填充。 它会根据您在区段导出中放置的内容构建参数列表。 完成后，Data Workbench会将数据发送到Adobe Target服务器。

   **注意：** 模板文件应由 [!UICONTROL Profile Architect]配置。需要输入[!UICONTROL Client Name]、[!UICONTROL Domain Postfix]、[!UICONTROL Mbox Host]和[!UICONTROL Mbox Name]。 如果您有多个网站，则填写多个模板并将其保存到服务器。 “配置文件管理器”中的模板位于`Context\FileNew\Detail Table\Export\Copy`中。

   ![](assets/insight-to-tnt1.png)

1. 指定[!UICONTROL mboxPC]查询参数。

   如果Data Workbench属性的名称不是[!UICONTROL mboxPC]，则必须编辑相应的查询参数并将其重命名为&#x200B;_mboxPC_。

   ![](assets/insight-to-tnt2.png)

   将导出文件保存到服务器后，将开始导出。 完成后，[!UICONTROL TnTSend.exe]应用程序将启动并开始向Target帐户发送数据。

## 为Target配置Data Workbench

在Adobe Target中完成以下任务：

Data Workbench正在将用户配置文件传递到Adobe Target。 要配置导出到Target，您需要设置并启用其API，并为导出配置文件(`export.cfg`)提供&#x200B;**[!UICONTROL clientname]**&#x200B;和&#x200B;**[!UICONTROL domain postfix]**&#x200B;参数。

为区段导出文件添加了名为&#x200B;**[!UICONTROL Oneshot]**&#x200B;的新布尔选项。 此选项包含在随新用户档案分发的模板文件中。 如果将[!UICONTROL Oneshot]设置为&#x200B;_true_，则在导出完成后，会将`.export`文件重命名为`.export.done-TIMESTAMP`，以确保区段永远不会被多次导出。 这在导出到Adobe Target时很重要。

**注意：** 从Data Workbench到Adobe Target的调用计为一次调 [!UICONTROL mbox] 用，每个发送的用户档案都需要一次调用。因此，如果两个解决方案之间需要多次调用，则成本会增加。

配置不完整会在日志中生成以下错误消息：

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## 配置Adobe Target以Data Workbench

在Adobe Target中，客户发送用户档案数据不需要任何特殊配置。 用户的配置文件信息通常在常规的[!UICONTROL mbox]请求中传递，服务器将使配置文件参数作为标准功能提供给目标营销活动设置，而无需进行任何其他设置。

Adobe Target内置了Data Workbench集成，可从超级用户客户端详细信息页面启用该集成。 启用此选项将显示从Adobe Target内的Data Workbench共享的区段，以使其可用于定位。

## 在ExportIntegration.exe中设置HTTP日志报告

使用[!UICONTROL ExportIntegration.exe]导出Adobe Target集成文件时，请缩短对[!UICONTROL HTTP.log]的报告时间。

新的[!UICONTROL httpLoggingEI.cfg]配置文件（位于`server\Admin\Export\httpLoggingEI.cfg`）允许您在使用[!UICONTROL ExportIntegration.exe]导出数据时减少对[!UICONTROL HTTP.log]文件执行详细日志记录。 这允许您停止详细请求/响应日志记录。

已在[!UICONTROL TnTSend.log]文件中捕获详细日志记录。

__ Truesets详细记录，和Falses停 __ 止对文件进行详细记 [!UICONTROL HTTP.log] 录。

在False设置中，只向[!UICONTROL HTTP.log]文件发送警告消息（未发送信息内容）。
