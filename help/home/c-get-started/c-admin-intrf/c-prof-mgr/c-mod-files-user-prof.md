---
description: 您可以使用“配置文件管理器”下载要修改的文件。
solution: Analytics
title: 修改用户配置文件中的本地文件
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modify local files in the user profile{#modify-local-files-in-the-user-profile}

您可以使用“配置文件管理器”下载要修改的文件。

您可能要下载一个文件，以使用该文件的原始版本覆盖您现有的本地文件，或者打开、查看并修改无法从工作区菜单访问的文件。

**下载文件**

1. In the [!DNL Profile Manager], open the necessary folders and subfolders to locate the file that you want to download.
1. Right-click the check mark next to the name of the file and click **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configuration ( [!DNL .cfg]), dimension ( [!DNL .dim]), and metric ( [!DNL .metric]) files can be edited directly in a profile folder and saved to the server without making them local and separately saving them to the server. Simply right-click the check mark next to the name of the file and click **[!UICONTROL Open]** > **in workstation**.

After the file has been downloaded to the local computer, a check mark appears in the [!DNL User] column, which indicates that a local copy of the file resides in the User\*profile name* folder on your computer. 请注意，复选标记的颜色与&#x200B;*配置文件名称*&#x200B;列中的复选标记相同。这表示本地文件与&#x200B;*配置文件名称*&#x200B;文件夹中的文件具有相同的修改日期和时间。

**修改文件**

1. Right-click the check mark next to the file name in the [!DNL User] column.
1. 单击以下菜单选项之一，具体选择取决于您希望如何编辑文件：

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** if you are editing a [!DNL .vw] file or [!DNL .cfg] file in a workspace.

   * **打开** > **in vw。 编辑器**。

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** if you wan open a text file or need to add new parameters to a [!DNL .cfg] file.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** if you want to open the folder which the file is on the computer

1. 根据需要编辑文件，然后保存该文件。

In the [!DNL Profile Manager], note that the check mark in the [!DNL User] column for the file you edited has changed color. 这表示本地文件现在不同于&#x200B;*配置文件名称*&#x200B;文件夹中的版本。如有必要，可以将文件的修改版本发布到配置文件，以供使用此配置文件的其他用户使用。
