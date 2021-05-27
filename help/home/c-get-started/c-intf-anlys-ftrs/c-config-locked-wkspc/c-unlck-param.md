---
description: 用户 Insight.cfg 文件中的 Unlock（解锁）参数指定用户是否有权对锁定的工作区临时解锁以进行编辑。
title: 设置解锁参数
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 73%

---

# 设置解锁参数{#set-the-unlock-parameter}

用户 Insight.cfg 文件中的 Unlock（解锁）参数指定用户是否有权对锁定的工作区临时解锁以进行编辑。

如果用户的[!DNL Insight.cfg]文件中已存在Unlock（解锁）参数，则可以使用Data Workbench编辑该参数。 如果用户的 [!DNL Insight.cfg] 文件中不存在该参数，则必须使用文本编辑器（例如记事本）将其添加到该文件中。

**[!DNL Unlock]在 Insight.cfg 文件中设置现有 （解锁）参数**

1. 在工作区中，右键单击&#x200B;**[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**。 将打开[!DNL Insight.cfg]文件。
1. 对于 Unlock（解锁）参数，键入 true 或 false。True 表示允许用户暂时对任何锁定的工作区解锁，而 false 则不允许。
1. 要保存配置更改，请右键单击窗口顶部的&#x200B;**[!UICONTROL Insight.cfg (modified)]** ，然后单击&#x200B;**[!UICONTROL Save as Insight.cfg]**。

**将 Unlock（解锁）参数添加到 Insight.cfg 文件**

1. 导航到您的Data Workbench安装目录，然后使用文本编辑器（如记事本）打开[!DNL Insight.cfg]文件。
1. 将 Unlock（解锁）参数添加到文件末尾，如下例所示：

[!DNL Unlock = bool: false]

1. 设置值为 true 或 false。True 表示允许用户暂时对任何锁定的工作区解锁，而 false 则不允许。
1. 保存并关闭该文件。
