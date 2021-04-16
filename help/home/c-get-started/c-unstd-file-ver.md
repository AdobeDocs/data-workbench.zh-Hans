---
description: Worktop可轻松确定每个特定工作区的存储位置，无论它位于Data Workbench服务器、本地计算机还是两者。
title: 文件版本控制
uuid: 5e7430f3-1425-41d2-828b-bc8f5786bf3b
exl-id: 82a70d51-a95c-4ddd-8d3c-cd0364940693
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 26%

---

# 文件版本控制{#file-versioning}

Worktop可轻松确定每个特定工作区的存储位置，无论它位于Data Workbench服务器、本地计算机还是两者。

## 识别文件版本{#section-d555c96b016344f19b356c12213dd2a9}

**服务器**

服务器工作区存储在连接的Data Workbench服务器上，可供有权访问此用户档案和选项卡的所有用户使用。 服务器工作区显示为单个缩略图。

![](assets/wsp_thumb_server.png)

默认情况下，服务器工作区存储在所连接的Data Workbench服务器上Workspaces文件夹中的相应子文件夹中。

**本地**

本地工作区是本地版本的服务器工作区。本地工作区显示为两个重叠的缩略图。最初上面的缩略图周围有一圈光晕，这表示最近在本地对服务器工作区进行了更改。此光晕会随时间而消散。

![](assets/wsp_thumb_local.png)

默认情况下，本地工作区存储在Data Workbench（或Insight）安装目录的[!DNL User\working profile name\Workspaces\tab]名称文件夹中。

>[!NOTE]
>
>当您有服务器工作区的本地版本时，必须先还原到服务器版本，然后才能下载服务器工作区的更新版本。 要恢复到服务器版本而不进行本地更改，请右键单击本地工作区的缩略图，然后单击&#x200B;**[!UICONTROL Revert to server version]**。

**用户**

用户工作区是在本地计算机上创建且仅存在于本地计算机上的工作区。用户工作区显示为单个缩略图，其后是空白工作区的虚线轮廓，表示所连接的Data Workbench服务器上没有源工作区。

![](assets/wsp_thumb_user.png)

默认情况下，用户工作区存储在Insight安装目录的User\*工作用户档案名称*\Workspaces\*tab name*文件夹中。
