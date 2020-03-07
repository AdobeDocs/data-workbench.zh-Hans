---
description: 关于特定于 Web 的设置信息，这些设置在与 Adobe Site 配置文件一起提交的转换数据集包含文件中定义。
solution: Analytics
title: 用于转换的特定于 Web 的设置
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# 用于转换的特定于 Web 的设置{#web-specific-settings-for-transformation}

关于特定于 Web 的设置信息，这些设置在与 Adobe Site 配置文件一起提交的转换数据集包含文件中定义。

由这些设置定义的条件、维度和参数在数据集构建的转换阶段创建。

* [页面查看条件](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [URI 维度](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [反向链接维度](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [会话参数](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## 页面查看条件 {#section-cc2807a12a88492f8b64a43234a1f835}

The [!DNL Page View Condition] is a condition operation that determines whether a particular log entry (that is, a page request) should be included in the data gathered about a visitor&#39;s page view history. When the log entry satisfies the [!DNL Page View Condition], it becomes an element of the Page View countable dimension. If a log entry does not satisfy the [!DNL Page View Condition], its data fields still are accessible by other dimensions. In addition to the Page View dimension, the following dimensions can be affected by the results of the [!DNL Page View Condition]:

* **[!DNL URI]和[!DNL Page]:**这些维度直接受到影响[!DNL Page View Condition]。 If the given page does not pass the[!DNL Page View Condition,]it is not be included in the URI or Page dimensions.

* **[!DNL Visitor Page Views]和[!DNL Session Page Views]:**“访客页面查看次数”和“会话页面查看次数”维是访客在给定会话中或在给定会话中查看的页面数量的计数。 Pages filtered out by the[!DNL Page View Condition]are not part of this count.

* **会话编号：** 它 [!DNL Page View Condition] 对“会话编号”维有间接影响。 The Session Number dimension is created prior to the [!DNL Page View Condition]; therefore, when considering [!DNL Session Number] in relation to the [!DNL Page Views], it is possible to have sessions with no page views.

您的默认实现 [!DNL Site] 包括一 [!DNL Transformation Dataset Include] 个文件，其中定义了页面视图可计数维和相关 [!DNL Page View Condition] 维度。

有关可计数维的信息，请参阅 [扩展维](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**编辑“页面查看条件”的配置设置**

1. 在数据集 [!DNL Profile Manager] 配置文件中打开文件，然后打开 [!DNL Dataset\Transformation\Traffic\Page View.cfg] 文件。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. Review or edit the values of the parameters of the [!DNL Page View Condition] as needed. 可参考以下示例。在此文件中， [!DNL Page View Condition] 由转换定 [!DNL Copy] 义。 请注意，此文件还包含“页面浏览量”可计数维度的定义。

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >有关可计数维的信息，请参阅 [扩展维](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。 有关转换的信 [!DNL Copy] 息，请参阅 [数据转换](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md)。

1. Save the file by right-clicking **[!UICONTROL (modified)]** at the top of the window, then click **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

## URI 维度 {#section-348f7e9099d049d197a7cdcbc8a6c234}

如果您要使用 [!DNL Site]，则需要定义 URI 维度，该维度的元素是所查看的网站页面的 URI 主干。Your default implementation includes a [!DNL Transformation Dataset Include] file in which the URI simple dimension is defined.

有关简单维的信息，请参阅 [扩展维](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**编辑 URI 维度的配置设置**

1. 在数据集 [!DNL Profile Manager] 配置文件中打开文件，然后打开 [!DNL Dataset\Transformation\Traffic\URI.cfg] 文件。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. 根据需要查看或编辑该文件参数的值。可参考以下示例和信息。

![](assets/cfg_WebParameters_URI.png)

URI 维度的配置设置包含以下两个参数：

* **区分大小写：** True 或 false。如果为 true，则在识别唯一页面时会考虑字母的大小写情况。默认值为 true。
* **最大元素数量：** URI 维度元素（即 URI）的最大数量。默认值为 32768。

   >[!NOTE]
   >
   >更改此值可能会导致严重的性能问题。 在未咨询 Adobe 的情况下，请勿更改此值。

* Save the [!DNL URI.cfg] file by right-clicking **[!UICONTROL (modified)]** at the top of the window, then click **[!UICONTROL Save]**.

* To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

## “反向链接”维度{#section-8a97ec34d18b4814b5f95495ac4f8638}

如果您要使用 [!DNL Site]，则需要定义“反向链接”维度，该维度的元素由所有会话中第一个日志条目反向链接的次级域组成。Your default implementation includes a [!DNL Transformation Dataset Include] file in which the Referrer simple dimension is defined.

有关简单维的信息，请参阅 [扩展维](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md)。

**编辑“反向链接”维度的配置设置**

1. 在数据集 [!DNL Profile Manager] 配置文件中打开文件，然后打开 [!DNL Dataset\Transformation\Traffic\Referrer.cfg] 文件。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these configuration settings exist may differ from the location described.

1. 根据需要查看或编辑该文件参数的值。可参考以下示例和信息。

   ![](assets/cfg_WebParameters_Referrer.png)

   “反向链接”维度的配置设置包括 Maximum Elements（最大元素数量）参数，该参数指定“反向链接”维度元素（即反向链接）的最大数量。默认值为 32768。

   >[!NOTE]
   >
   >In the example above, the [!DNL Maximum Elements] parameter is set to 0. 此参数设为 0 时，Data Workbench Server 将使用其内部默认值 32768。

1. Save the [!DNL Referrer.cfg] file by right-clicking **[!UICONTROL (modified)]** at the top of the window, then click **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

## 会话参数 {#section-0a209b0c504041a5801f7f71a963c8b1}

如果您要使用 [!DNL Site]，则可以指定一些参数来定义网站上访客会话的边界。These parameters are valid only when defined in a [!DNL Transformation Dataset Include] file within your [!DNL Site] implementation.

The following parameters are unique in that they can be members of [!DNL Transformation Dataset Include] file&#39;s [!DNL Parameters] vector, or they can be listed as individual parameters in the [!DNL Transformation.cfg]file. A parameter can be defined exactly once, so these parameters are defined either in the [!DNL Transformation.cfg]file or in the [!DNL Parameters] vector of the dataset include file - not in both files.
**最大会话时长和会话超时**

Maximum Session Duration（最大会话时长）和 Session Timeout（会话超时）是用于定义访客会话长度的字符串参数。这些参数与 Internal Domains（内部域）参数结合使用来确定会话长度。

最大会话时长指定在启动新会话之前的最长会话长度。这可防止具有自动内容刷新功能的网页创建任意长度的会话。如果某个单击的反向链接设为 Internal Domains（内部域）参数中的条目之一，则此超时将用于定义会话结束。无论会话包含多少次单击，任何会话都不会长于指定的最大会话时长。建议的值为 48 小时。

会话超时指定在给定访客的日志条目之间需要经过的时间量，用于确定一个会话的结尾和新会话的开头（即用于定义用户会话的典型超时）。此参数的建议值是 30 分钟。如果某个单击的反向链接未设为 Internal Domains（内部域）参数中的反向链接之一，则此超时将用于定义会话。如果某个日志条目的 cs(referrer-domain) 位于内部域列表中，则“最大会话时长”将确定当前日志条目是现有会话的一部分还是新会话的开头。

假定某位访客在浏览网站期间被叫走，而且他离开计算机的这段时间长于“会话超时”。该访客返回后，从之前暂停的位置继续浏览。由于访客从未离开网站或关闭浏览器，因此他下一次单击的 cs(referrer-domain) 与内部域相同，并且只要未达到“最大会话时长”设置，他的原始会话就保持活动状态。如果网站的域列为内部域，并且未达到最大超时，则访客的交互会显示为一个会话，而不是两个不同的会话。但是，如果访客返回计算机后，他的下一次单击具有外部（或空白）反向链接，则会开始一个新会话。

>[!NOTE]
>
>The [!DNL Sessionize] transformation&#39;s [!DNL Timeout Condition] also plays a role in determining the length of a visitor&#39;s session. If Session Timeout and Maximum Session Duration do not apply, the [!DNL Timeout Condition] is checked to determine whether a log entry should be considered the start of a new session. For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**编辑 Maximum Session Duration（最大会话时长）和 Session Timeout（会话超时）参数**

If you are working with [!DNL Site], your default implementation likely includes a [!DNL Transformation Dataset Include] file in which the names and recommended values of these parameters are specified.

1. 在数据 [!DNL Profile Manager] 集配置文件中打开并转到 [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg]。

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which these parameters are defined may differ from the location described.

1. 根据需要编辑参数的值。请确保指定所需的单位（分钟、小时等）。

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Save the [!DNL Session Parameters.cfg] file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

**[!DNL Internal Domains]**

[!DNL Internal Domains]（内部域）是一个矢量参数，它列出了应视为特定网站一部分的域级别主机（内部反向链接）。这些主机会从反向链接维度（外部反向链接信息的列表）中删除。如果 cs(referrer-domain) 匹配内部域集中列出的任何字符串，则会忽略“会话超时”，并且将使用“最大会话时长”确定会话长度。

当访客在一个公司的多个域（这些域以超过会话超时的方式关联在一起）之间转换时，Internal Domains（内部域）参数还可用于防止启动新会话。例如，假定公司的部分网站分为两个域：一个域进行记录 ([!DNL xyz.com])，另一个域不进行记录 ([!DNL xyz-unlogged.com])。如果这些网站的集成方式便于流量在两个域之间无缝移动，则每次访客从 [!DNL xyz-unlogged.com] 域转回 [!DNL xyz.com] 域时，便无需生成另一个会话。只要未达到“最大会话时长”设置，将 [!DNL xyz-unlogged.com] 列为内部域就能防止会话因为流量跨两个域而被拆分为多个会话。

**添加内部域**

If you are working with [!DNL Site], your default implementation includes a [!DNL Transformation Dataset Include] file for defining the Internal Domains parameter. 在此文件中，对该参数进行了命名，您只需输入想要包含的内部域并保存更新后的文件即可。

1. 打开数 [!DNL Profile Manager] 据集配置文件内的，然后转到 [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >If you have customized your implementation of [!DNL Site], the file in which the Internal Domains parameter is defined may differ from the location described.

1. 右键单击“ **[!UICONTROL Value]** 内部域”矢量参数，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Value]**。

1. 根据需要编辑值。

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Save the [!DNL Internal Domains.cfg] file by right-clicking **[!UICONTROL (modified)]** at the top of the window and clicking **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

   >[!NOTE]
   >
   >请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

