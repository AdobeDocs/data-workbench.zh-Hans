---
description: 在配置实验之前，应创建要在实验中使用的替代内容。
solution: Analytics,Analytics
title: 创建测试内容
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# 创建测试内容{#creating-the-test-content}

在配置实验之前，应创建要在实验中使用的替代内容。

对照组将发送到原始URI，而测试组将发送到新的替代URI。

要避免混淆，请勿重用测试组文件名。 例如，如果您使用名为[!DNL test2.asp]的测试组文件运行实验，则不要在下一个实验中使用[!DNL test2.asp]作为测试文件的名称。

对于将“请求演示”图形链接移到主页上会影响访客转换的假设验证，我们会在新位置创建包含“请求演示”图形链接的替代主页。 以下部分介绍您随后如何指定将对照组URI [!DNL index.asp]替换为特定百分比访客的测试组URI [!DNL index2.asp]。
