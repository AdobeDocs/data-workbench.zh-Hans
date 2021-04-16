---
description: 要使报表服务器的某些功能正常工作，您必须在安装之前提供并配置硬件或软件。
title: 开始之前
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 4%

---

# 开始之前{#before-you-begin}

要使报表服务器的某些功能正常工作，您必须在安装之前提供并配置硬件或软件。

## 基本报表服务器要求{#section-e891eaee79fe4fa98e658426dc3b2777}

输出的报表可以是.PNG图像或.XLS电子表格形式，也可以是电子邮件形式。 硬件要求与[Data Workbench客户端](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)相同。

报表服务器存在以下要求：

* 访问文件系统以输出数据（网络共享或本地驱动器）。
* 访问已配置的SMTP服务器。
* 安装在[!DNL Report]服务器上的Microsoft Excel 2010 64位或更高版本。 有关其他信息，请参阅[ Office服务器端自动化注意事项](http://support.microsoft.com/kb/257757)。

## 其他要求{#section-f53d4388656a4dfc90aefe29dfabef89}

* **安装适当的图形适配器。** 要正确呈现报告，安装服务器的 [!DNL Report] 计算机必须安装相应的图形适配器。

* **安装Microsoft Excel以将报表生成为Excel文件。** 要以Microsoft Excel文件（或）的形 [!DNL .xls] 式生 [!DNL .xlsx]成和分发报表，安装报表服务器的计算机必须安装并注册相应版本的64位Microsoft Excel。如果Excel尚未注册，并且报表服务器首次尝试访问它，则Excel将显示一个注册对话框。 如果您不确定是否已注册副本，请手动开始Excel，如果出现注册对话框，请完成注册过程。

   >[!NOTE]
   >
   >将报表生成为Excel文件时，将打开Excel的新实例。 有关此过程的详细信息，请参阅 [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757)。

* **提供对SMTP服务器的访问权限，以通过电子邮件分发报告。** 如果要以电子邮件形式分发报表，则报表服务器必须能够连接到SMTP服务器，并且必须打开指向电子邮件转发服务的相应端口。
