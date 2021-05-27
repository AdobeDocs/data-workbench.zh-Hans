---
description: 当Web服务器因故障而离线时，该解决方案很简单，它要求具有相应权限的Data Workbench用户打开Log Processing Mode.cfg文件，并将传感器ID（在我们的示例中为WEB2）添加到“离线源”部分。
title: 解决问题
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 解决问题{#solving-the-problem}

当Web服务器因故障而离线时，该解决方案很简单，它要求具有相应权限的Data Workbench用户打开Log Processing Mode.cfg文件，并将传感器ID（在我们的示例中为WEB2）添加到“离线源”部分。

文件的此部分告知[!DNL data workbench server]，它不应再期望此源提供任何数据，因为实际上，它是离线的。

>[!NOTE]
>
>无需由Adobe顾问执行此更改。 任何有权打开[!DNL Log Processing Mode.cfg]文件的人都可以进行此更改。

如果WEB2再次开始发送数据，[!DNL data workbench server]将源重新联机并调整截止时间以反映其上次从其感知的所有源接收数据的时间。 换言之，传入系统的新数据优先于[!DNL Log Processing Mode.cfg file]中写入的内容。

如果WEB2再次离线，则“截止时间”将再次停止，您将需要再次编辑[!DNL Log Processing Mode.cfg]文件，即使它可能已将WEB2列为离线源。 这是产品设计中符合“截止时间”(As Of Time)定义的人为产物：系统上次包含所有已知源的数据时。

添加更多Web服务器(WEB4、WEB5、WEB6)，然后它们开始向[!DNL data workbench server]发送数据时，您无需执行任何操作，即可让[!DNL data workbench server]识别新源。 如上所述，系统只是意识到它应期待来自这些新来源的数据。
