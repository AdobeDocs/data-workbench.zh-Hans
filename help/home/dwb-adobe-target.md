---
description: 将Data Workbench与Adobe Target集成。 导出数据段并自动填充导出文件。
title: Data Workbench 与 Adobe Target 集成
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Data Workbench 与 Adobe Target 集成

借助用于导出Adobe段和自动填充导出文件的Data Workbench功能，更轻松地将Data Workbench与Adobe Target集成。

AdobeData Workbench提供与Adobe Target的闭环集成，用于共享数据和生成报告。 在Data Workbench中，您可以使用所有可用数据分析人群，以找到有意义的细分，包括通过电话、商店等渠道进行离线转换。

例如，访客在您的网站上查找鞋，但不会进行转换。 相反，访客会下载优惠券，下次购买时可享受20%的折扣，然后在您的商店购买一件衬衫。 使用Data Workbench，您可以收集该数据，然后将该用户档案数据推回目标，以显示访客离线购买了一件衬衫。 然后，您可以目标一个为访客提供领带的活动，当通常目标可能尝试将鞋重新销售给该访客时。

## 使用Adobe Target设置Data Workbench

1. 右键单击[!UICONTROL Detail Table]窗口中的标题。

   ![](assets/insight-to-tnt.png)

1. 选择&#x200B;**[!UICONTROL New Target Export]**，然后在菜单的&#x200B;**[!UICONTROL Save As]**&#x200B;命令下输入新导出文件的名称。

1. 单击 **[!UICONTROL Save Export File]**。

   将打开一个导出模板窗口。

   所有Adobe Target信息将自动填充。 它根据您在区段导出中放置的内容构建参数列表。 完成后，Data Workbench会将数据发送到Adobe Target服务器。

   **注意：** 模板文件应由配置 [!UICONTROL Profile Architect]。需要输入[!UICONTROL Client Name]、[!UICONTROL Domain Postfix]、[!UICONTROL Mbox Host]和[!UICONTROL Mbox Name]。 如果您有多个站点，则填写多个模板并将其保存到服务器。 用户档案管理器中的模板位于`Context\FileNew\Detail Table\Export\Copy`中。

   ![](assets/insight-to-tnt1.png)

1. 指定[!UICONTROL mboxPC]查询参数。

   如果Data Workbench属性的名称不是[!UICONTROL mboxPC]，则必须编辑相应的查询参数，并将其重命名为&#x200B;_mboxPC_。

   ![](assets/insight-to-tnt2.png)

   将导出文件保存到服务器时，将开始导出。 完成后，[!UICONTROL TnTSend.exe]应用程序将启动并开始向目标帐户发送数据。

## 配置Data Workbench以实现目标

在Adobe Target中完成以下任务:

Data Workbench正在将用户用户档案传递到Adobe Target。 要配置导出到目标，您需要设置并启用其API，并为导出配置文件(`export.cfg`)提供&#x200B;**[!UICONTROL clientname]**&#x200B;和&#x200B;**[!UICONTROL domain postfix]**&#x200B;参数。

名为&#x200B;**[!UICONTROL Oneshot]**&#x200B;的新布尔选项已添加到区段导出文件。 此选项包含在随新用户档案分发的模板文件中。 如果[!UICONTROL Oneshot]设置为&#x200B;_true_，则在导出完成后，`.export`文件将重命名为`.export.done-TIMESTAMP`，以确保不会多次导出区段。 这在导出到Adobe Target时很重要。

**注意：** 从Data Workbench到Adobe Target的呼叫计为呼叫， [!UICONTROL mbox] 每次发送的用户档案需要一次呼叫。因此，如果两个解决方案之间需要多次呼叫，则成本会增加。

配置不完整时，将在日志中生成以下错误消息：

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## 配置Adobe Target以实现Data Workbench

在Adobe Target中，客户发送用户档案数据不需要特殊配置。 用户的用户档案信息通常在常规的[!UICONTROL mbox]请求中传递，服务器会将用户档案参数作为标准功能提供给目标活动设置，而无需任何附加设置。

Adobe Target内置了Data Workbench集成，可以从“超级用户客户端详细信息”页面启用。 启用此选项将显示从Adobe Target内的Data Workbench共享的区段，以使其可用于定位。

## 在ExportIntegration.exe中设置HTTP日志报告

使用[!UICONTROL ExportIntegration.exe]导出Adobe Target集成文件时，将长报告减少到[!UICONTROL HTTP.log]。

新的[!UICONTROL httpLoggingEI.cfg]配置文件（位于`server\Admin\Export\httpLoggingEI.cfg`）可让您在使用[!UICONTROL ExportIntegration.exe]导出数据时减少对[!UICONTROL HTTP.log]文件的详细记录。 这允许您停止详细请求/响应日志记录。

已在[!UICONTROL TnTSend.log]文件中捕获详细日志。

_Truesets详_ 细记录，Falses停 __ 止详细记录到 [!UICONTROL HTTP.log] 文件。

在“False”设置中，只有警告消息将发送到[!UICONTROL HTTP.log]文件（未发送信息内容）。
