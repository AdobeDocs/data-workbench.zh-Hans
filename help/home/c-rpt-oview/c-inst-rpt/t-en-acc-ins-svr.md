---
description: 要连接到Data Workbench Server，报表服务器必须具有访问该服务器的权限。
solution: Analytics
title: 启用对Data Workbench Server的访问
topic: Data workbench
uuid: e112ac2a-34fe-40a2-9324-262f5cb1f681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 启用对Data Workbench Server的访问{#enabling-access-to-the-data-workbench-server}

要连接到Data Workbench Server，报表服务器必须具有访问该服务器的权限。

通过将Report Server的通用名称（在Report Server的数字证书上分配）添加到服务器的访问控制文件，可以授予对Data Workbench Server的访问权限。

>[!NOTE]
>
>在群集环境中工作时，应将Report Server配置为访问主Data Workbench Server以避免同步问题。 In data workbench you can view information about processing servers in your cluster using the [!DNL Related Servers] menu item in the [!DNL Servers Manager]. For more information about the [!DNL Servers Manager], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

以下过程介绍如何将Report Server手动添加到Data Workbench Server上的访问控制文件。 要以这种方式更新访问控制文件，您必须在安装Data Workbench Server的计算机上具有文件系统访问权限。

您还可以使用Data Workbench中的文件更新服务器的 [!DNL Server Files Manager] 访问控制文件。 为此，您的Data Workbench客户端必须对服务器具有管理权限。

For more information about the [!DNL Server Files Manager], see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

**配置对Data Workbench Server的访问权限**

1. 导览至Data Workbench Server(InsightServer64.exe)安装目录中的“访问控制”文件夹。

   示例：[!DNL C:\Adobe\Server\Access Control]

1. 在文 [!DNL Access Control.cfg] 本编辑器（如记事本）中打开。
1. 找到该 [!DNL Report Server AccessGroup] 组并 [!DNL Report Server’s] 向该组添加公用名称，如以下文件片段中突出显示。 (键入公用名称，其显示方式与数字证 [!DNL Report Server’s] 书完全相同。)

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
