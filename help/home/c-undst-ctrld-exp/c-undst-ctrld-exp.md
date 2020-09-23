---
description: 受控实验是一种测试，它允许您将从实验样本组获得的结果与从标准对照组获得的结果进行比较。
solution: Analytics,Analytics
title: Data Workbench控制实验
topic: Data workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---


# Data Workbench Controlled Experiments{#data-workbench-controlled-experiments}

受控实验是一种测试，它允许您将从实验样本组获得的结果与从标准对照组获得的结果进行比较。

站点使您能够实施、测量和分析与网站不同方面相关的受控实验及其结果。 这样，您就可以在花费大量时间或金钱来全面实施建议的更改之前，测试有关网站性能改进的假设验证。

>[!NOTE]
>
>只有在数据集中才能分析站点实验，其中唯一使用的访客识别方法是集 [!DNL Sensor] 合的永久cookie方法。 在J2EE服务器（JBoss、Tomcat、WebLogic和WebSphere）上运行的传感器不支持受控试验。 有关详细信息，请参阅下一节。

使用“站点”，您可以实施A/B、A/B/A和多变量控制实验，以收集足够的测试数据，从而提供统计上准确的数据，用于详细评估您的假设验证，而不会影响当前网站的性能。
