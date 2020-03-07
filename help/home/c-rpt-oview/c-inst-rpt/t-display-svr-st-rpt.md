---
description: Data Workbench中的“详细状态”界面可用于对作为Data Workbench Server客户端的Data Workbench Server和Report Server计算机的错误或其他问题进行疑难解答。
solution: Analytics
title: 显示报告服务器状态
topic: Data workbench
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 显示报告服务器状态{#displaying-report-server-status}

Data Workbench中的“详细状态”界面可用于对作为Data Workbench Server客户端的Data Workbench Server和Report Server计算机的错误或其他问题进行疑难解答。

要在界面中查看“报表”的状 [!DNL Master Server Detailed Status] 态，必须将报表状态服务器添加到Data Workbench Server文 [!DNL Servers] 件中的矢量中的报 [!DNL Communications.cfg] 表。 以下过程介绍如何将报告状态服务器添加到文 [!DNL Communications.cfg] 件：

For more information about [!DNL Detailed Status] interfaces, see the Administrative Interfaces chapter of the *Data Workbench User Guide*.

**添加[!DNL Report Status Server]**

1. 导航到Data Workbench Server(InsightServer64.exe)安装目录中的“组件”文件夹。

   示例：[!DNL C:\Adobe\Server\Components]
1. 在文 [!DNL Communications.cfg] 本编辑器（如记事本）中打开。
1. 找到该 [!DNL Servers] 矢量，并将报告状态服务器添加到此矢量，如下面的文件片段中高亮显示。

   ```
    . . .
   Servers = vector: 17 items
       0 = FileServer: 
         Local Path = string: Audit\\
         URI = string: /Audit
       1 = FileServer: 
         Local Path = string: Bin\\
         URI = string: /Bin
       2 = FileServer: 
         Local Path = string: Components\\
         URI = string: /Components
     . . .
       16 = ReportStatusServer: 
         URI = string: /ReportStatus.vsp
   ```

1. 更新矢量的项目计数( [!DNL Servers] 即，将项目值增加1)，该值在上一步的文件片段中高亮显示。
1. 保存文件。
