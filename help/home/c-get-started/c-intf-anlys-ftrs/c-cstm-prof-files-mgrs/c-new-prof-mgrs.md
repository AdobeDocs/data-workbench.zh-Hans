---
description: “配置文件管理器”显示与工作配置文件相关的所有目录。
title: 创建配置文件管理器
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 25%

---

# 创建配置文件管理器{#create-a-profile-manager}

“配置文件管理器”显示与工作配置文件相关的所有目录。

您可能需要访问[!DNL Profile Manager]的子目录，而无需导航其整个目录结构。 例如，通过工作区窗口菜单[!DNL Manage]菜单上提供的[!DNL Metrics]和[!DNL Workspaces]菜单选项，可分别打开“配置文件管理器量度”和“工作区”文件夹。

有关[!DNL Profile Manager]的详细信息，请参阅[配置文件管理器](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)。

默认情况下，您可以访问以下管理器：

* **[!DNL Metrics Manager]:** 显示“配置文件管理器”的“量度”文件夹的内容。您可以打开、编辑、删除或复制每个配置文件中定义的量度。
* **[!DNL Reports Manager]:** 显示“配置文件管理器”的“报告”文件夹的内容。您可以打开、编辑、删除或复制报表工作区或 [!DNL report.cfg] 文件。

* **[!DNL Workspaces Manager]:** 显示“配置文件管理器”的“工作区”文件夹的内容。所有用于配置 [!DNL Worktop] 选项卡的文件都位于此处。请参阅[自定义Worktop选项卡](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)。

Data Workbench允许您创建其他配置文件管理器，以显示[!DNL Profile Manager]中的一个子目录。 您创建的每个管理器都必须有一个[!DNL .vw]文件，该文件指定其显示内容的[!DNL Profile Manager]目录以及该窗口的属性。 您可以将任何提供的管理器的[!DNL .vw]文件用作模板。

**创建配置文件管理器**

1. 在[!DNL Profile Manager]中，单击&#x200B;**[!UICONTROL Menu]**&#x200B;目录以查看其内容。
1. 在 Menu 目录内，单击 **[!UICONTROL Admin]** 目录，然后单击 **[!UICONTROL Profile]** 目录。现有管理器的[!DNL .vw]文件位于此处。
1. 在&#x200B;*配置文件名称*&#x200B;列中，右键单击其中一个[!DNL .vw]文件（例如[!DNL Workspaces.vw]）的复选标记，然后单击&#x200B;**[!UICONTROL Make Local]**。

   [!DNL User]列中将显示该文件的复选标记。

1. 右键单击[!DNL User]列中[!DNL .vw]文件的复选标记，然后单击&#x200B;**[!UICONTROL Open]** > **[!UICONTROL in Notepad]**。
1. 在[!DNL Profile Path]字段中，键入要为其创建新管理器的[!DNL Profile Manager]目录。 请确保目录名称后面包含斜线 (/)。

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

1. 在记事本中，单击&#x200B;**[!UICONTROL File]** > **[!UICONTROL Save As]**&#x200B;将编辑后的文件保存到&#x200B;*Data Workbench安装文件夹*\User\*工作配置文件名称*\Menu\Admin\Profile Management。

   请务必更改[!DNL .vw]文件的名称，以反映该文件所对应的[!DNL Profile Manager]目录。

1. （可选）若要使更改对工作配置文件的所有用户可用，请右键单击[!DNL User]列中[!DNL .vw]文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > **[!UICONTROL working profile name]**>。
