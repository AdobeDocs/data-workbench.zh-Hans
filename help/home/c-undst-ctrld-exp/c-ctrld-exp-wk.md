---
description: 在实验中，除了控制组，您还可以定义任意数量的测试组。
solution: Insight,Analytics
title: 受控实验如何工作？
topic: Data workbench
uuid: 9549e2ab-dca9-4fb1-9729-65072f951900
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 受控实验如何工作？{#how-do-controlled-experiments-work}

在实验中，除了控制组，您还可以定义任意数量的测试组。

当实验运行时，访问您网站的所有访客在访问实验中涉及的任何页面时，即作为测试组或控制组的一部分成为实验的一部分。 访客会按实验配置中定义的比例随机分配到实验组。

使用安装在Web群集中 [!DNL Sensor] 的每个内容服务器上的软件实现受控实验。 当内容服务器收到请求时，会随 [!DNL Sensor] 机选择测试组的访客，并将其页面请求重定向到实验内容。 当选 [!DNL Sensor] 择访客查看测试内容时，地址栏会继续列出最初请求的URI，但访客会路由到测试URI。 由于此过程在服务器应用程序内部进行，因此用户不知道他们何时被测试，这是进行无偏试验的重要考虑因素。

[!DNL Sensor] 将测试URI（而非向用户显示的原始URI）传递到日志文件以用于分析。

可以轻松地分析实验结果，以确定 [!DNL Insight] 您所测试的实验假设是否正确。

>[!NOTE]
>
>Adobe强烈建议，应根据组织中负责配置和维护分析数据集的人员的反馈来协调和执行受控实验。

