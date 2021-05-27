---
description: 在配置实验之前，应创建要在实验中使用的替代内容。
solution: Analytics,Analytics
title: 创建测试内容
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# 创建测试内容{#creating-the-test-content}

在配置实验之前，应创建要在实验中使用的替代内容。

控制组将被发送到原始URI，而测试组将被发送到新的备用URI。

为避免混淆，请不要重复使用测试组文件名。 例如，如果使用名为[!DNL test2.asp]的测试组文件运行实验，请不要将[!DNL test2.asp]用作下一个实验中测试文件的名称。

假设在主页上移动“请求演示”图形链接会影响访客转化，我们会创建替代主页，该主页的新位置包含“请求演示”图形链接。 以下部分介绍您随后如何为特定百分比的访客指定控制组URI [!DNL index.asp]替换为测试组URI [!DNL index2.asp]。
