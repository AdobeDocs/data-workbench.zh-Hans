---
description: 当Web服务器因故障而脱机时，该解决方案很简单，需要具有相应权限的用户打开Log Processing Mode.cfg文件并将传感器的ID（在我们的示例中，为WEB2）添加到“Offline Sources”部分。
title: 解决问题
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
exl-id: 4a05dc06-360b-4c15-a881-81d350e95372
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# 解决问题{#solving-the-problem}

当Web服务器因故障而脱机时，该解决方案很简单，需要具有相应权限的用户打开Log Processing Mode.cfg文件并将传感器的ID（在我们的示例中，为WEB2）添加到“Offline Sources”部分。

文件的此部分告诉[!DNL data workbench server]它不应再期望来自此源的任何数据，因为实际上它是脱机的。

>[!NOTE]
>
>此更改不需要由Adobe顾问执行。 任何具有打开[!DNL Log Processing Mode.cfg]文件的适当权限的人都可以进行此更改。

如果WEB2开始再次发送数据，[!DNL data workbench server]将源重新联机，并调整“截止时间”以反映它上次从其感知的所有源接收数据的时间。 换句话说，传入系统的新数据优先于[!DNL Log Processing Mode.cfg file]中写入的内容。

如果WEB2再次脱机，则“开始”时间将再次停止，并且您需要再次编辑[!DNL Log Processing Mode.cfg]文件，即使它可能已将WEB2列为脱机源。 这是符合“开始时间：系统上次拥有所有已知源的数据时。

添加更多Web服务器(WEB4、WEB5、WEB6)后，它们开始向[!DNL data workbench server]发送数据时，您无需执行任何操作，让[!DNL data workbench server]识别新源。 如上所述，系统只是意识到它应期望这些新来源的数据。
