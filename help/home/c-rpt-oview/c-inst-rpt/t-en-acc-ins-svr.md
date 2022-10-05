---
description: 要连接到Data Workbench Server，报表服务器必须具有访问该服务器的权限。
title: 启用对 Data Workbench 服务器的访问
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
exl-id: bf409413-470e-4e05-9bd2-b5b511bbe4a5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 6%

---

# 启用对 Data Workbench 服务器的访问{#enabling-access-to-the-data-workbench-server}

{{eol}}

要连接到Data Workbench Server，报表服务器必须具有访问该服务器的权限。

您可以授予对Data Workbench Server的访问权限，方法是将报表服务器的通用名称（在报表服务器的数字证书上分配）添加到服务器的访问控制文件。

>[!NOTE]
>
>在群集环境中工作时，应将报表服务器配置为访问主控的Data Workbench Server，以避免出现同步问题。 在Data Workbench中，您可以使用 [!DNL Related Servers] 菜单项 [!DNL Servers Manager]. 有关 [!DNL Servers Manager]，请参阅 *Data Workbench用户指南*.

以下过程介绍如何将报表服务器手动添加到Data Workbench Server上的访问控制文件。 要以这种方式更新访问控制文件，您必须在安装Data Workbench Server的计算机上具有文件系统访问权限。

您还可以使用 [!DNL Server Files Manager] 在data workbench中。 要实现此目的，您的Data Workbench客户端必须对服务器具有管理权限。

有关 [!DNL Server Files Manager]，请参阅 *Data Workbench用户指南*.

**配置对Data Workbench Server的访问**

1. 导航到Data Workbench Server(InsightServer64.exe)安装目录中的Access Control文件夹。

   示例：[!DNL C:\Adobe\Server\Access Control]

1. 打开 [!DNL Access Control.cfg] 在文本编辑器（如记事本）中。
1. 找到 [!DNL Report Server AccessGroup] 添加 [!DNL Report Server’s] 此组的通用名称，在以下文件片段中突出显示。 (完全键入显示的通用名称 [!DNL Report Server’s] 数字证书。)

   ```
   . . .
     5 = AccessGroup: 
       Members = vector: 1 items
         0 = string: CN: ReportCommonName
       Name = string: Report Server
       Read-Only Access = vector: 5 items
         0 = string: /Profiles/$
         1 = string: /Status/
         3 = string: /Software/
         4 = string: /Addresses/
         5 = string: /Users/$
       Read-Write Access = vector: 3 items
         0 = string: /Profiles/
         1 = string: /Users/%CN%/
         2 = string: /ReportStatus.vsp
      . . .
   ```

1. 保存文件。
