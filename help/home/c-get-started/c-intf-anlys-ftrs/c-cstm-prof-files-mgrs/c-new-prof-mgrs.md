---
description: “配置文件管理器”显示与工作配置文件相关的所有目录。
title: 创建配置文件管理器
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 25%

---

# 创建配置文件管理器{#create-a-profile-manager}

{{eol}}

“配置文件管理器”显示与工作配置文件相关的所有目录。

您可能想要访问 [!DNL Profile Manager] 无需导航其整个目录结构。 例如， [!DNL Metrics] 和 [!DNL Workspaces] 菜单选项 [!DNL Manage] “工作区”窗口菜单的菜单，可分别打开“配置文件管理器量度”和“工作区”文件夹。

有关 [!DNL Profile Manager]，请参阅 [配置文件管理器](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

默认情况下，您可以访问以下管理器：

* **[!DNL Metrics Manager]:** 显示“配置文件管理器”的“量度”文件夹的内容。 您可以打开、编辑、删除或复制每个配置文件中定义的量度。
* **[!DNL Reports Manager]:** 显示“配置文件管理器”的“报告”文件夹的内容。 您可以打开、编辑、删除或复制报表工作区或 [!DNL report.cfg] 文件。

* **[!DNL Workspaces Manager]:** 显示“配置文件管理器”的“工作区”文件夹的内容。 所有用于配置 [!DNL Worktop] 选项卡的文件都位于此处。请参阅 [自定义工作台选项卡](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench允许您创建其他配置文件管理器，以显示 [!DNL Profile Manager]. 您创建的每个管理器都必须具有 [!DNL .vw] 指定 [!DNL Profile Manager] 显示其内容的目录以及该窗口的属性。 您可以使用 [!DNL .vw] 作为模板为任何提供的管理器提供文件。

**创建配置文件管理器**

1. 在 [!DNL Profile Manager]，请单击 **[!UICONTROL Menu]** 目录查看其内容。
1. 在 Menu 目录内，单击 **[!UICONTROL Admin]** 目录，然后单击 **[!UICONTROL Profile]** 目录。的 [!DNL .vw] 现有管理器的文件位于此处。
1. 在 *配置文件名称* 列中，右键单击 [!DNL .vw] 文件(例如， [!DNL Workspaces.vw])，然后单击 **[!UICONTROL Make Local]**.

   文件的复选标记将显示在 [!DNL User] 列。

1. 右键单击 [!DNL .vw] 文件 [!DNL User] 列，单击 **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. 在 [!DNL Profile Path] 字段，键入 [!DNL Profile Manager] 要为其创建新管理器的目录。 请确保目录名称后面包含斜线 (/)。

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

1. 在记事本中，单击 **[!UICONTROL File]** > **[!UICONTROL Save As]** 将已编辑的文件保存到 *Data Workbench安装文件夹*\User\*工作配置文件名称*\Menu\Admin\Profile Management。

   请务必更改 [!DNL .vw] 文件来反映 [!DNL Profile Manager] 对应的。

1. （可选）若要使更改对工作配置文件的所有用户可用，请右键单击 [!DNL .vw] 文件 [!DNL User] 列，单击 **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**> 。
