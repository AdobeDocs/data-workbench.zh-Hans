---
description: 在实验中，除了控制组之外，您还可以定义任意数量的测试组。
solution: Analytics
title: 控制试验的工作原理是什么？
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
exl-id: 1d3af6a2-078e-4eb8-848e-685f531a60c5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---

# 控制试验的工作原理是什么？{#how-do-controlled-experiments-work}

{{eol}}

在实验中，除了控制组之外，您还可以定义任意数量的测试组。

当实验运行时，所有访问您网站的访客一旦访问实验中涉及的任何页面，即会成为实验的一部分（无论是作为测试组的一部分还是控制组的一部分）。 访客会以实验配置期间定义的比例随机分配给您的实验组。

使用 [!DNL Sensor] 软件。 当内容服务器收到请求时， [!DNL Sensor] 随机选择测试组的访客并将其页面请求重定向到实验内容。 When [!DNL Sensor] 选择访客以查看测试内容，地址栏会继续列出最初请求的URI，但访客将被路由到测试URI。 由于此过程在服务器应用程序内部进行，因此用户在测试时并不知情，这是进行无偏倚实验的重要考虑因素。

[!DNL Sensor] 将测试URI（而非向用户显示的原始URI）传递到日志文件以供分析使用。

实验结果可以很方便地用 [!DNL Insight] 来确定你所测试的实验假设是否正确。

>[!NOTE]
>
>Adobe强烈建议对照实验进行协调和执行，以便使用组织中负责配置和维护分析数据集的人员的输入。
