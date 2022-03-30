---
description: 部署实验后，您应该验证该实验是否正常工作。
solution: Analytics
title: 验证试验
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 验证试验{#validating-the-experiment}

部署实验后，您应该验证该实验是否正常工作。

如 [修改ExpCookieURL参数（可选）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)，在 [!DNL Sensor] 配置文件可用于将您自己放置在特定的实验组中。

默认虚拟页面为 [!DNL /setcookie.htm]，但必须使用ExpCookieURL参数中设置的值。

## 请求测试页 {#section-8aed3b48d47f4e6c8869c0216f8781b1}

要为您的网站测试特定实验组，必须将您的浏览器配置为接受Cookie，并且您必须尚未拥有此网站的Cookie。

每次要测试新组时，请确保清除网站的Cookie。

要将您自己放入特定实验的特定组中，请使用以下形式的查询字符串来请求测试页面：

[!DNL https://] *&lt; [!DNL sitename/?Experiment Name=Group Name]>*

例如：

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

将虚拟URL请求发送到服务器时， [!DNL Sensor] 将您标识为指定实验中指定组的成员，然后将您重定向到网站的根。 您现在可以导航到网站上的相应位置，以验证是否为该实验和组显示了正确的内容。

如果要在浏览器中键入以下内容，则浏览器将显示网站的主页，并将您放入New_Homepage实验的index2组中：

[!DNL https://www.omniture.com/setcookie.htm?New_Homepage=index2]

当index2组中的访客请求主页时，“请求演示”图形链接在页面上的较高位置显示，如下图所示：

![](assets/TestPage.png)
