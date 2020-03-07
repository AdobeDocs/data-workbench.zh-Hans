---
description: “配置文件管理器”显示与工作配置文件相关的所有目录。
solution: Analytics
title: 创建Profile Manager
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 创建Profile Manager{#create-a-profile-manager}

“配置文件管理器”显示与工作配置文件相关的所有目录。

You may want to access a subdirectory of the [!DNL Profile Manager] without having to navigate its entire directory structure. For example, the [!DNL Metrics] and [!DNL Workspaces] menu options available on the [!DNL Manage] menu of the workspace window menu enable you to open the Profile Manager Metrics and Workspaces folders, respectively.

有关的详细信息，请 [!DNL Profile Manager]参阅 [配置文件管理器](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)。

默认情况下，您可以访问以下管理器：

* **[!DNL Metrics Manager]:**显示Profile Manager的Metrics文件夹的内容。 您可以打开、编辑、删除或复制每个配置文件中定义的量度。
* **[!DNL Reports Manager]:**显示Profile Manager的Reports文件夹的内容。 您可以打开、编辑、删除或复制报表工作区或[!DNL report.cfg]文件。

* **[!DNL Workspaces Manager]:**显示Profile Manager的Workspaces文件夹的内容。 所有用于配置[!DNL Worktop]选项卡的文件都位于此处。See[Customizing Worktop Tabs](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench enables you to create additional profile managers that display one subdirectory from the [!DNL Profile Manager]. Each manager that you create must have a [!DNL .vw] file that specifies the [!DNL Profile Manager] directory whose contents it shows and the properties of that window. You can use the [!DNL .vw] file for any of the provided managers as a template.

**创建配置文件管理器**

1. In the [!DNL Profile Manager], click the **[!UICONTROL Menu]** directory to view its contents.
1. 在 Menu 目录内，单击 **[!UICONTROL Admin]** 目录，然后单击 **[!UICONTROL Profile]** 目录。The [!DNL .vw] files for the existing managers are located here.
1. In the *profile name* column, right-click the check mark for the one of the [!DNL .vw] files (for example, [!DNL Workspaces.vw]), then click **[!UICONTROL Make Local]**.

   A check mark for the file appears in the [!DNL User] column.

1. Right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. In the [!DNL Profile Path] field, type the [!DNL Profile Manager] directory for which you want to create a new manager. 请确保目录名称后面包含斜线 (/)。

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. In Notepad, click **[!UICONTROL File]** > **[!UICONTROL Save As]** to save the edited file to the *Data Workbench installation folder*\User\*working profile name*\Menu\Admin\Profile Management.

   Be sure to change the name of the [!DNL .vw] file to reflect the directory in the [!DNL Profile Manager] to which it corresponds.

1. (Optional) To make the changes available to all users of the working profile, right-click the check mark for the [!DNL .vw] file in the [!DNL User] column and click **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

