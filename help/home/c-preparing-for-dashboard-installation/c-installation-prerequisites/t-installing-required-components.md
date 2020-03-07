---
description: 安装所需Microsoft组件的步骤。
solution: Analytics
title: 安装所需组件
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装所需组件{#installing-required-components}

安装所需Microsoft组件的步骤。

1. 安装Microsoft .NET Framework v4.0。

   >[!NOTE]
   >
   >只有在安装和配置IIS Web角色后，才能安装它。

1. 按照向导操作，并选择默认值，提示您完成安装的位置。
1. 安装后，请验证ASP.NET v.4.0应用程序池是否已添加到IIS **[!UICONTROL Application Pools]** 的列表中。
1. 安装Microsoft SQL Server数据库。

   将任何版本的SQL Server 2008或2008 R2（支持Express）与管理工具一起使用（Adobe建议使用SQL Server 2008 R2 SP1 - Express Edition）。 1.对于没有提前运行的现有SQL Server实例的通用安装，请在屏幕上选 **[!UICONTROL Default Instance]** 择该选 **[!UICONTROL Instance Configuration]** 项。
1. 对于其余的配置选项，请按照向导操作，并在提示您完成安装时选择默认值。
1. 安装Microsoft Web Deploy v2.0。

   对于大多数安装， **[!UICONTROL Typical]** 安装是正常的。 但是，如果您计划执行远程部署，则需要完全安装(选择 **[!UICONTROL Complete]**)。

   正确安装所有先决条件后，您就可以准备Data Workbench Server以与控制板通信。
