---
description: Data Workbench提供了安装工作站（客户端）应用程序的设置向导。
title: 工作站设置向导
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# 工作站设置向导{#workstation-setup-wizard}

Data Workbench提供了安装工作站（客户端）应用程序的设置向导。

## 使用安装向导安装工作站 {#section-58da9bb6196c46eab3b54146913fdcb8}

启动安装向导可执行文件并逐步完成安装工作站客户端项目的每个步骤。 安装工作站后，您可以连接到服务器和用户档案。

1. 多次-单击工作站安装程序可执行文件。
1. 单击 **是** ，以允许项目在Windows上安装。
1. 为设置 **向导选择** “语言”。

   此时将打开向导：

   ![](assets/6_4_workstation_wizard.png)

1. 单击 **欢迎使用** Data Workbench设置 **向导对话框中的下一步** 。

1. 选择以安装新 **安装** ，或升 **级或修复现有安装** 。

   **“新安装** ”将覆盖以前安装的任何文件。

   **升级** ，可将工作站更新至最新版本，或者允许您修复现有安装。 如果有较高版本的客 **户端可用，Data Workbench将比较已安装的Insight.exe** 文件并运行工作站设置向导。

1. 选择安装位置：

   **典型** ，安装到默认文件夹和位置。

   * 项目文件默认保存为：

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * 默认情况下，数据文件(用户档案、证书、跟踪日志和用户文件)保存为：

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >最初将安 ***装一个不带服务器详细信息的通用Insight*** .cfg文件。 建议您使用新安装的 ***Insight.cfg文件并自定义它*** ，而不是从以前的安装中移动文件。 由于工作站的安装路径已更改，因此建议添加字体、删除 *User Folder*，并删除*TraceFileComponent *。

1. （可选）选择 **“自定义** ”以选择语言包以及项目和数据文件的位置。
1. 在“开始” **菜单中选择快捷键的位置**。

   ![](assets/6_4_workstation_wizard_folder.png)

   单 **击“不创建开始菜单”文件夹** ，以便不在Windows开始菜单上安装快捷键。

1. 单击&#x200B;**下一步。** 此时将显示所选文件位置路径和语言的摘要。 单击 **Install.**

1. 找到数 **据工作台证书**。

   如果安装向导在安装过程中找不到Data Workbench证书，它将打开一个对话框以浏览到证书的位置(默认位于客户端 **Certificates文件夹中的** .pem **文件)，或单击** Skip **** 以在安装后查找证书。

   找到 **证书后** ，单击“安装”。

1. 安装向导完成并安装Data Workbench后，单击“完 **成** ”以完成安装。

   >[!NOTE]
   >
   >工作站设置向导的默认日志位置， **[!DNL 网址为C:\Users\<userName>\AppData\Local\Temp。]**

   选中“启 **动应用程序** ”复选框，以在设置后打开工作台。

1. **配置到文件中** ，与服务器的 **[!DNL Insight.cfg]** 连接。

   安装工作站后，将打开增强的工作站配置体验工作区，其中包含有关在 [Insight.cfg文件中输入服务器连接信息的其他信息](/help/home/c-get-started/c-insght-config-param.md)** ，以及从下拉菜单中选择用户档案的选项。 您还可以将连接状态视图到服务器。

   ![](assets/6_4_workstation_install_conf_conn.png)

## 安装文件夹 {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

Data Workbench文件夹结构有两个安装位置：

* **项目文件** Insight **.exe和支持客户端文件(** Insight.ini ****)现在默认位于

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Appdata文 **件夹** 。

   **Insight.cfg**、用户档案、证书、跟踪日志和用户文件现在默认位于

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   您可以在文件中设置 **Appdata** 文件夹的 `Insight.ini` 路径：

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## 卸载工作站 {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Data Workbench现在包含一个可卸载工作站的可执行文件(默认位置 **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**&#x200B;为)。

启动并按照步骤从硬盘中删除Data Workbench Workstation文件。

>[!NOTE]
>
>您可以使用“ **开始菜单”中的“卸载数据工作台”(** Uninstall Data Workbench **)快捷键，或从“菜单”(** >)启动unins000.exe可执行文件 **[!UICONTROL Control Panel]****[!UICONTROL Program and Features]**。
