---
description: 卸载Insight Server、转换或中继器的说明。
title: 卸载软件
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# 卸载软件{#uninstalling-your-software}

卸载Insight Server、转换或中继器的说明。

## 卸载Insight ServerAdobe{#section-7d7befe672854df79bb6c28ec02f6670}

1. 取消注册[!DNL Insight Server] Windows服务。

   1. 打开命令提示符，然后导航到[!DNL Insight Server]安装文件夹中的bin子目录。

      示例：[!DNL C:\Adobe\Server\bin]

   1. 在命令提示符下，执行以下命令，以在Microsoft Windows下停止并取消注册服务：

      ```
      InsightServer64.exe /unregserver
      ```

1. 删除[!DNL Insight Server]安装目录。

## 正在卸载转换{#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. 使用以下步骤来更新您使用[!DNL Transform]的每个配置文件的[!DNL profile.cfg]文件。

   1. 打开 [!DNL Profile Manager].
   1. 右键单击[!DNL profile.cfg]旁边的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。 [!DNL User]列中将显示此文件的复选标记。

   1. 右键单击新创建的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Insight]**。 出现[!DNL profile.cfg]窗口。

   1. 在[!DNL profile.cfg]窗口中，从目录矢量中删除[!DNL Transform]配置文件条目。

   1. 右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

   1. 在[!DNL Profile Manager]中，右键单击[!DNL User]列中[!DNL profile.cfg]的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*。

1. 从[!DNL Insight Server]安装目录的[!DNL Profiles]文件夹中删除[!DNL Transform]文件夹。

## 卸载中继器{#section-2f94141d956749d88f549dbea26e5272}

1. 取消注册[!DNL Repeater] Windows服务。

   1. 打开命令提示符，然后导航到[!DNL Repeater]安装文件夹中的bin子目录。

      示例：[!DNL D:\Adobe\Repeater\bin]

   1. 在命令提示符下，执行以下命令，以在Microsoft Windows下停止并取消注册服务：

      ```
      InsightServer64.exe /unregserver
      ```

1. 删除[!DNL Repeater]安装目录。
