---
description: 有关日志处理数据集包含文件中定义的特定于 Web 设置的信息，这些文件与用于 Site 的 Adobe 配置文件一起提供。
solution: Analytics
title: 用于日志处理的特定于 Web 的设置
topic: Data workbench
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 用于日志处理的特定于 Web 的设置{#web-specific-settings-for-log-processing}

有关日志处理数据集包含文件中定义的特定于 Web 设置的信息，这些文件与用于 Site 的 Adobe 配置文件一起提供。

The filtering defined by these settings occurs after the log entries leave the decoders and the transformations are applied but before evaluation by the [!DNL Log Entry Condition].

* [HTTP 状态过滤](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [机器人过滤](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## HTTP 状态过滤 {#section-ac66acdcb6aa467d81c3721199e540fd}

您可以配置 [!DNL Site] 的实施，以从数据集中删除 sc-status 代码为 400 或以上的日志条目。成功请求的状态代码小于 400。Your default implementation includes a [!DNL Log Processing Dataset Include] file in which HTTP status filtering is configured.

**编辑 HTTP 状态过滤的配置设置**

1. 在数据集 [!DNL Profile Manager] 配置文件中打开文件，然后打开 [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] 文件。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. 根据需要查看或编辑该文件参数的值。可参考以下示例。

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   有关该条件的 [!DNL Range] 信息，请参 [阅条件](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)。

1. Save the [!DNL HTTP Status Filter.cfg] file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

## 机器人过滤 {#section-7f43681dfbc64b969619cb88f97d5ad5}

您可以配置 [!DNL Site] 的实施，以使用对照文件从数据集中删除由已知机器人、测试脚本和内部用户 IP 地址生成的日志条目。您的默认实现包括一 [!DNL Log Processing Dataset Include] 个配置了自动过滤的文件。

**编辑机器人过滤的配置设置**

1. 在数据集 [!DNL Profile Manager] 配置文件中打开文件，然后打开 [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] 文件。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. 参考以下示例和信息，查看或编辑该文件的参数：

   ![](assets/cfg_WebParameters_RobotFilter.png)

   该文件包含由以下三个参数定义的 [!DNL NotRobotCondition]：

   * **Case Insensitive Robot Filtering（不区分大小写机器人过滤）：** true 或 false。如果为 true，则在机器人过滤时不考虑字母的大小写情况。
   * **Robot Lookup File, Baseline（机器人对照文件，基线）：**&#x200B;文本文件的路径和文件名，该文本文件包含已知为机器人并且将被过滤出数据集的浏览器用户代理的列表。Adobe 提供基线机器人对照文件。如果未指定路径，则 Data Workbench Server 会在 Data Workbench Server 安装目录内的 Lookups 目录中查找此文件。
   * **Robot Lookup File, Extended（机器人对照文件，扩展）：**&#x200B;包含浏览器用户代理或 IP 地址（这些代理和地址定义特定于实施的机器人）列表的可选文本文件的路径和文件名。此列表可包含应从数据集中筛选出来的内部监视机器人、测试脚本和内部用户的 IP 地址。如果未指定路径，则 Data Workbench Server 会在 Data Workbench Server 安装目录内的 Lookups 目录中查找此文件。
   如果某个日志条目的浏览器用户代理在两个对照文件中都没有列出，则该日志条目被视为由“真实”访客生成，而不会从数据集中过滤出来。

   >[!NOTE]
   >
   >机器人查找文件中的匹配使用子字符串与c-ip和cs(user-agent)日志字段进行比较。 如果搜索字符串以“$”开头，则它必须匹配所测试字符串的开头；如果搜索字符串以“$”结尾，则它必须匹配所测试字符串的结尾。如果搜索字符串的开头和结尾都是“$”，则字符串必须完全匹配才能筛选出日志条目。例如，若要测试 C 类块中的所有 IP 地址，则需要使用“$231.78.123.”之类的字符串来强制匹配字符串的开头。这将匹配从 231.78.123.0 至 231.78.123.255 的地址。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

   >[!NOTE]
   >
   >如果用于构建数据集的基础日志条目不发生更改（即使用于构建和更新数据集及其维度的转换发生更改）至关重要，则应对Robot Lookup File（自动查找文件）、Baseline（基线）和Robot Lookup File（扩展）进行版本控制。 为这些文件指定一个版本号，可确保对默认机器人对照文件的更新不会因在这些文件中添加或删除条目而意外更改以前构建的报表数据集。

