---
description: “服务器文件管理器”显示Data Workbench Server安装目录中的所有目录，包括配置和查找文件。
solution: Analytics
title: 创建服务器文件管理器
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 创建服务器文件管理器{#create-a-server-files-manager}

“服务器文件管理器”显示Data Workbench Server安装目录中的所有目录，包括配置和查找文件。

You may want to access a portion of the [!DNL Server Files Manager] without having to navigate its entire directory structure or display only a few of the subdirectories to address a particular need. For example, you might want to create a separate [!DNL Server Files Manager] that displays only the Access Control and Users subdirectories, enabling you to manage your users and their access.

Each manager that you create must have a [!DNL .vw] file. You can use the [!DNL Server Files.vw] file as a template.

有关的详细信息， [!DNL Server Files Manager]请参 [阅服务器文件管理器](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)。

**创建服务器文件管理器**

1. 在中， [!DNL Profile Manager]单击目 **[!UICONTROL Menu]** 录，然后单击目 **[!UICONTROL Admin]** 录。 The [!DNL Server Files.vw] file is located here.
1. In the *profile name* column, right-click the check mark for the [!DNL Server Files.vw] file and click **[!UICONTROL Make Local]**. A check mark for the file appears in the [!DNL User] column.
1. Right-click the check mark for the [!DNL Server Files.vw] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. The [!DNL Server Files.vw] file opens.
1. 要删除目录，请右键单击该目录的上边框， [!DNL Server Files Manager] 然后单击 **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*。
1. 要添加目录，请右键单击目录的上边框 [!DNL Server Files Manager]，单击 **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**。

   Type the directory’s URI in the URI field, and click **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >您可以在URI字段中指定多个目录。 例如，如果您键入[!DNL Profiles\Marketing\]，则服务器文件管理器将包含Marketing子目录，但Profiles目录中没有其他子目录。

1. 右键单击顶部边框，然 [!DNL Server Files Manager] 后单击 **[!UICONTROL Save]**。
1. To create a new manager, change the file name in the [!DNL File Name] field, then click **[!UICONTROL Save]**. To overwrite the existing manager, click **[!UICONTROL Save]**.
1. （可选）要使更改对工作配置文件的所有用户可用，请右键单击列中文件 [!DNL .vw] 的复选标 [!DNL User] 记。

   然后，单击 **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

