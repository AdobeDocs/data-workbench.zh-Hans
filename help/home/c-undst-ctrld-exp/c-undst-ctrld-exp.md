---
description: 对照实验是一种测试，用于比较从实验样本组获得的结果和从标准对照组获得的结果。
solution: Analytics
title: Data Workbench对照实验
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Data Workbench对照实验{#data-workbench-controlled-experiments}

对照实验是一种测试，用于比较从实验样本组获得的结果和从标准对照组获得的结果。

通过网站，您可以实施、测量和分析对照实验及其结果，因为它们与网站的不同方面相关。 这样，您就可以在花费大量时间或资金全面实施建议的更改之前，测试有关网站性能改进的假设。

>[!NOTE]
>
>网站实验只能在使用唯一访客识别方法( [!DNL Sensor] 设置永久cookie方法。 在J2EE服务器（JBoss、Tomcat、WebLogic和WebSphere）上运行的传感器不支持对照实验。 有关更多信息，请参阅以下部分。

使用Site，您可以实施A/B、A/B/A和多变量对照实验，以收集足够的测试数据，从而提供具有统计学意义的准确数据来详细评估您的假设，而不会影响当前网站的性能。
