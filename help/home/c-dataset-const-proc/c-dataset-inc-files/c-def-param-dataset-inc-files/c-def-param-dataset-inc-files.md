---
description: 配置数据集时，可以定义变量（也称为参数）来表示有意义的值。
title: 在数据集包含文件中定义参数
uuid: 1eb7d48c-a107-4b32-abca-55d30586813f
exl-id: 80bb77e1-a157-4e16-9519-6d0e2ce17fe1
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 51%

---

# 在数据集包含文件中定义参数{#defining-parameters-in-dataset-include-files}

配置数据集时，可以定义变量（也称为参数）来表示有意义的值。

要为参数赋值（即定义参数），请在日志处理或[!DNL Transformation Dataset Include]文件中将参数的名称和值添加到Parameters矢量。 定义参数之后，您就可以在数据集配置文件的配置文件中引用这些参数。定义和引用此类参数称为参数替代。配置数据集时使用参数替代可以为参数定义创建一个集中位置。当您需要对引用了多次或在多个文件中引用的参数进行更新时，只需更改一次即可。

>[!NOTE]
>
>在本指南中，术语参数用于引用配置文件中任何设置的名称（如日志条目条件、重新处理或转换）。 但在本节中，参数特指数据集包含文件中“参数”矢量的成员，而不是配置文件中设置的名称。

在定义参数时，您应该考虑以下几点：

* 一个参数只需定义一次。因此，无法在多个数据集包含文件中定义同一个变量。
* 您定义的任何参数对于日志处理阶段或转换阶段都是本地的，但在该阶段的多个数据集配置文件中是全局通用的。例如，如果在[!DNL Transformation Dataset Include]文件中定义参数，则该参数将在整个转换阶段定义，并且可以在[!DNL Transformation.cfg]文件和继承配置文件的所有其他[!DNL Transformation Dataset Include]文件中引用该参数。 不会为日志处理定义参数；因此，对[!DNL Log Processing.cfg]文件或[!DNL Log Processing Dataset Include]文件中参数的任何引用都将生成处理错误。

**定义参数**

您可以在[!DNL Log Processing]和[!DNL Transformation Include]文件中定义字符串参数、数值参数和矢量参数。

1. 在[!DNL Log Processing]或[!DNL Transformation Dataset Include]文件的Data Workbench窗口中，右键单击&#x200B;**[!UICONTROL Parameters]**，然后单击&#x200B;**[!UICONTROL Add new]** > **[!UICONTROL Parameter]**。

1. 选择&#x200B;**[!UICONTROL String Parameter]**、**[!UICONTROL Numeric Parameter]**&#x200B;或&#x200B;**[!UICONTROL Vector Parameter]**，然后按照以下部分所述完成Name（名称）和Value（值）参数。

1. 要保存已定义参数的数据集包含文件，请右键单击窗口顶部的&#x200B;**[!UICONTROL (modified)]** ，然后单击&#x200B;**[!UICONTROL Save]**。

1. 若要使本地所做的更改生效，请在[!DNL Profile Manager]列中右键单击[!DNL User]列中该文件的复选标记，然后单击&#x200B;**[!UICONTROL Save to]** > ***[!UICONTROL profile name]**>*，其中“配置文件名称”是数据集包含文件所属的数据集配置文件或继承配置文件的名称。

>[!NOTE]
>
>请勿将已修改的配置文件保存到 Adobe 提供的任何内部配置文件中，因为当您安装这些配置文件的更新时，系统会覆盖您所做的更改。

**引用参数**

* 在另一个数据集配置文件中引用定义的参数时，必须键入其名称[!DNL $(parameter name)]。

以下各节描述了您可以定义的参数类型。

* [字符串参数和数值参数](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-string-num-param.md#concept-14f391ce107c4a3dad827ec7967f1080)
* [矢量参数](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-vector-param.md#concept-adb42a5474e245a9996d0aa8d5d522d0)
