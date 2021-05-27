---
description: Data Workbench中的“详细状态”界面可用于对作为Data Workbench服务器客户端的Data Workbench服务器和报表服务器计算机出现错误或其他问题进行故障诊断。
title: 显示报表服务器状态
uuid: 5260266d-5bd1-4905-9619-f67f6e1bc54c
exl-id: 3a717a81-7c5d-432d-b214-4ae0455b19b5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---

# 显示报表服务器状态{#displaying-report-server-status}

Data Workbench中的“详细状态”界面可用于对作为Data Workbench服务器客户端的Data Workbench服务器和报表服务器计算机出现错误或其他问题进行故障诊断。

要在[!DNL Master Server Detailed Status]界面中查看报表的状态，必须将报表状态服务器添加到Data Workbench Server的[!DNL Communications.cfg]文件的[!DNL Servers]矢量中。 以下过程描述如何将报表状态服务器添加到[!DNL Communications.cfg]文件：

有关[!DNL Detailed Status]界面的详细信息，请参阅《Data Workbench用户指南》*的“管理界面”一章。*

**添加[!DNL Report Status Server]**

1. 导航到Data Workbench Server(InsightServer64.exe)安装目录中的Components文件夹。

   示例：[!DNL C:\Adobe\Server\Components]
1. 在文本编辑器（如记事本）中打开[!DNL Communications.cfg]。
1. 找到[!DNL Servers]矢量，并将报表状态服务器添加到此矢量，如以下文件片段中突出显示的那样。

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

1. 更新[!DNL Servers]矢量的项目计数（即，将项目值递增1），如上一步中在文件片段中突出显示的那样。
1. 保存文件。
