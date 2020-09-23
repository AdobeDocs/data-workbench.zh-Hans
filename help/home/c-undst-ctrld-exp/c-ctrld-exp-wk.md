---
description: 在实验中，除了定义对照组，您还可以定义任意数量的测试组。
solution: Analytics,Analytics
title: 对照实验的工作原理是什么？
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 3%

---


# 对照实验的工作原理是什么？{#how-do-controlled-experiments-work}

在实验中，除了定义对照组，您还可以定义任意数量的测试组。

当实验运行时，您网站上的所有访客在访问实验中涉及的任何页面后，即作为测试组或对照组的一部分成为实验的一部分。 访客会按实验配置中定义的比例随机分配给您的实验组。

控制实验是使用安装在 [!DNL Sensor] Web群集中每个内容服务器上的软件来实现的。 当内容服务器收到请求时， [!DNL Sensor] 会随机选择测试组的访客，并将其页面请求重定向到实验内容。 当选 [!DNL Sensor] 择访客来视图测试内容时，地址栏继续列表最初请求的URI，但访客路由到测试URI。 由于此过程在服务器应用程序中内部进行，因此用户不知道他们何时被测试，这是进行无偏的试验的重要考虑因素。

[!DNL Sensor] 将测试URI（而非向用户显示的原始URI）传递给日志文件以用于分析。

可以轻松地分析实验结果，以 [!DNL Insight] 确定您正在测试的实验假设验证是否正确。

>[!NOTE]
>
>Adobe强烈建议使用组织中负责配置和维护分析数据集的人员的输入来协调和执行受控实验。

