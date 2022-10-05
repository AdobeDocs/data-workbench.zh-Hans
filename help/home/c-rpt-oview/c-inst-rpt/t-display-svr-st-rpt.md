---
description: Data Workbench中的“详细状态”界面可用于对作为Data Workbench服务器客户端的Data Workbench服务器和报表服务器计算机出现错误或其他问题进行故障诊断。
title: 显示报表服务器状态
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# 显示报表服务器状态{#displaying-report-server-status}

{{eol}}

Data Workbench中的“详细状态”界面可用于对作为Data Workbench服务器客户端的Data Workbench服务器和报表服务器计算机出现错误或其他问题进行故障诊断。

在 [!DNL Master Server Detailed Status] 界面中，您必须向 [!DNL Servers] data workbench服务器中的矢量 [!DNL Communications.cfg] 文件。 以下过程介绍如何将报表状态服务器添加到 [!DNL Communications.cfg] 文件：

有关 [!DNL Detailed Status] 界面，请参阅 *Data Workbench用户指南*.

**添加[!DNL Report Status Server]**

1. 导航到Data Workbench Server(InsightServer64.exe)安装目录中的Components文件夹。

   示例：[!DNL C:\Adobe\Server\Components]
1. 打开 [!DNL Communications.cfg] 在文本编辑器（如记事本）中。
1. 找到 [!DNL Servers] 矢量并将报表状态服务器添加到此矢量，如下文件片段中突出显示。

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

1. 更新 [!DNL Servers] 矢量（即，将项目值递增1），在上一步骤的文件片段中突出显示。
1. 保存文件。
