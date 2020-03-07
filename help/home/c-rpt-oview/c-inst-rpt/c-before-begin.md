---
description: 要使报表服务器的某些功能正常工作，您必须在安装之前提供并配置硬件或软件。
solution: Analytics
title: 开始之前
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# 开始之前{#before-you-begin}

要使报表服务器的某些功能正常工作，您必须在安装之前提供并配置硬件或软件。

## 基本报告服务器要求 {#section-e891eaee79fe4fa98e658426dc3b2777}

输出的报告可以是。PNG图像或放入文件系统的。XLS电子表格的形式，也可以是电子邮件形式。 硬件要求与Data Workbench客户端 [相同](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)。

Report Server存在以下要求：

* 访问文件系统以输出数据（网络共享或本地驱动器）。
* 访问已配置的SMTP服务器。
* 服务器上安装的Microsoft Excel 2010 64位或更高 [!DNL Report] 版本。 有关 [其他信息，请参阅Office服务器端自动化注意事项](http://support.microsoft.com/kb/257757) 。

## 其他要求 {#section-f53d4388656a4dfc90aefe29dfabef89}

* **安装适当的图形适配器。** 要正确呈现报告，安装 [!DNL Report] Server的计算机必须安装相应的图形适配器。

* **安装Microsoft Excel以将报表生成为Excel文件。** 要以Microsoft Excel文件( [!DNL .xls] 或 [!DNL .xlsx])的形式生成和分发报表，安装Report Server的计算机必须安装并注册相应版本的64位Microsoft Excel。 如果Excel尚未注册，且报表服务器首次尝试访问它，则Excel将显示一个注册对话框。 如果不确定是否已注册副本，请手动启动Excel，如果出现注册对话框，请完成注册过程。

   >[!NOTE]
   >
   >将报表生成为Excel文件时，您将打开Excel的新实例。 有关此过程的详细信息，请参阅 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。

* **提供对SMTP服务器的访问权限，以通过电子邮件分发报告。** 如果要以电子邮件形式分发报告，报告服务器必须能够连接到SMTP服务器，并且必须打开指向电子邮件转发服务的相应端口。

