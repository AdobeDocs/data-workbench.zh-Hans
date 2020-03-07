---
description: 当Web服务器因故障而离线时，该解决方案很简单，它要求具有相应权限的Data Workbench用户打开Log Processing Mode.cfg文件，并将传感器的ID（在我们的示例中，WEB2）添加到“Offline Sources”部分。
solution: Insight
title: 解决问题
uuid: 19d47b06-be12-4adf-9eac-b16cf7131834
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 解决问题{#solving-the-problem}

当Web服务器因故障而离线时，该解决方案很简单，它要求具有相应权限的Data Workbench用户打开Log Processing Mode.cfg文件，并将传感器的ID（在我们的示例中，WEB2）添加到“Offline Sources”部分。

该文件的此部分告诉 [!DNL data workbench server] 它不应再期望来自此源的任何数据，因为它实际上处于脱机状态。

>[!NOTE]
>
>此更改无需由Adobe顾问执行。 具有打开文件的适当权限的任 [!DNL Log Processing Mode.cfg] 何人都可以进行此更改。

如果WEB2开始再次发送数据，则 [!DNL data workbench server] 将源恢复在线，并调整截止时间以反映其上次从其感知的所有源接收数据的时间。 换句话说，进入系统的新数据优先于在中写入的内容 [!DNL Log Processing Mode.cfg file]。

如果WEB2再次脱机，则“截止时间”将再次停止，并且您需要再次编辑该文件，即使它可能已将WEB2列为脱机源。 [!DNL Log Processing Mode.cfg] 这是符合“截止时间”(As Of)定义的产品设计的伪像：系统上次拥有所有已知来源的数据时。

添加更多Web服务器(WEB4、WEB5、WEB6)后，它们开始向发送数据 [!DNL data workbench server]，您无需执行任何操作即可识别 [!DNL data workbench server] 新源。 如上所述，系统只是意识到它应期望这些新来源的数据。
