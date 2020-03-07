---
description: 配置数据集时，可以定义变量（也称为参数）来表示有意义的值。
solution: Analytics
title: 在数据集包含文件中定义参数
topic: Data workbench
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 在数据集包含文件中定义参数{#defining-parameters-in-dataset-include-files}

配置数据集时，可以定义变量（也称为参数）来表示有意义的值。

To assign a value to a parameter (that is, to define the parameter), you add the parameter&#39;s name and value to the Parameters vector in a log processing or [!DNL Transformation Dataset Include] file. 定义参数之后，您就可以在数据集配置文件的配置文件中引用这些参数。定义和引用此类参数称为参数替代。配置数据集时使用参数替代可以为参数定义创建一个集中位置。当您需要对引用了多次或在多个文件中引用的参数进行更新时，只需更改一次即可。

>[!NOTE]
>
>在本指南中，术语参数用于引用配置文件中任何设置的名称（如日志条目条件、重新处理或转换）。 但在本节中，参数特指数据集包含文件中“参数”矢量的成员，而不是配置文件中设置的名称。

在定义参数时，您应该考虑以下几点：

* 一个参数只需定义一次。因此，无法在多个数据集包含文件中定义同一个变量。
* 您定义的任何参数对于日志处理阶段或转换阶段都是本地的，但在该阶段的多个数据集配置文件中是全局通用的。For example, if you define a parameter in a [!DNL Transformation Dataset Include] file, the parameter is defined for the entire transformation phase, and you can reference it in the [!DNL Transformation.cfg] file and all other [!DNL Transformation Dataset Include] files for the inherited profiles. The parameter would not be defined for log processing; therefore, any references to the parameter in the [!DNL Log Processing.cfg] file or a [!DNL Log Processing Dataset Include] file would generate a processing error.

**定义参数**

您可以在和文件中定义字符串、数字和矢 [!DNL Log Processing] 量参 [!DNL Transformation Include] 数。

1. 在或文件的Data Workbench窗 [!DNL Log Processing] 口中， [!DNL Transformation Dataset Include] 右键单击 **[!UICONTROL Parameters]**，然后单击 **[!UICONTROL Add new]** > **[!UICONTROL Parameter]**。

1. 选 **[!UICONTROL String Parameter]**&#x200B;择、 **[!UICONTROL Numeric Parameter]**&#x200B;或 **[!UICONTROL Vector Parameter]**，并完成“名称”和“值”参数，如以下各节所述。

1. To save the dataset include file in which you have defined the parameter, right-click **[!UICONTROL (modified)]** at the top of the window and click **[!UICONTROL Save]**.

1. To make the locally made changes take effect, in the [!DNL Profile Manager], right-click the check mark for the file in the [!DNL User] column, then click **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, where profile name is the name of the dataset profile or the inherited profile to which the dataset include file belongs.

>[!NOTE]
>
>请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

**引用参数**

* When you reference a defined parameter in another dataset configuration file, you must type its name as [!DNL $(parameter name)].

以下各节描述了您可以定义的参数类型。

* [字符串参数和数值参数](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [矢量参数](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)

