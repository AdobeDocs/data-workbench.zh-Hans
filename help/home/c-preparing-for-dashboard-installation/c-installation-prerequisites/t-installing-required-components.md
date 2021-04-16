---
description: 安装所需Microsoft组件的步骤。
title: 安装必需组件
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# 安装必需组件{#installing-required-components}

安装所需Microsoft组件的步骤。

1. 安装Microsoft .NET Framework v4.0。

   >[!NOTE]
   >
   >只有在安装和配置IIS Web角色后，才能安装它。

1. 请按照向导操作，并选择提示完成安装的默认值。
1. 安装后，请验证IIS中的&#x200B;**[!UICONTROL Application Pools]**&#x200B;列表中是否添加了ASP.NET v.4.0应用程序池。
1. 安装Microsoft SQL Server数据库。

   使用任何版本的SQL Server 2008或2008 R2（支持Express）和管理工具(Adobe建议使用SQL Server 2008 R2 SP1 - Express Edition)。 1.对于没有提前运行的现有SQL Server实例的通用安装，请在&#x200B;**[!UICONTROL Instance Configuration]**&#x200B;屏幕上选择&#x200B;**[!UICONTROL Default Instance]**&#x200B;选项。
1. 对于其余配置选项，请按照向导操作，并在提示完成安装时选择默认值。
1. 安装Microsoft Web Deploy v2.0。

   对于大多数安装，**[!UICONTROL Typical]**&#x200B;安装可以。 但是，如果您计划执行远程部署，则需要完全安装（选择&#x200B;**[!UICONTROL Complete]**）。

   正确安装所有先决条件后，即可准备好Data Workbench Server与仪表板通信。
