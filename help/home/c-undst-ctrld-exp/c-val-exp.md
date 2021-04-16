---
description: 部署实验后，应验证实验是否正常工作。
solution: Analytics,Analytics
title: 验证实验
uuid: 59769f5b-4175-479e-ad7d-7226e9c666af
exl-id: 6dfd01ca-288d-40fd-aad4-75a588902ebd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 2%

---

# 验证实验{#validating-the-experiment}

部署实验后，应验证实验是否正常工作。

如[修改ExpCookieURL参数（可选）](../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expckurl-prm.md#concept-215bf86bab4e4ec0b0cc803ec48a8fcf)中所述，在[!DNL Sensor]配置文件的ExpCookieURL参数中指定的页面可用于将自己放置在特定实验组中。

默认虚拟页为[!DNL /setcookie.htm]，但必须使用在ExpCookieURL参数中设置的值。

## 请求测试页{#section-8aed3b48d47f4e6c8869c0216f8781b1}

要测试网站的特定实验组，必须将您的浏览器配置为接受cookie，且您必须尚未拥有此网站的cookie。

每次要测试新组时，请确保清除网站的Cookie。

要将您自己放入特定实验的特定组中，请以下形式使用查询字符串请求测试页：

[!DNL http://] *&lt;>>*[!DNL sitename/?Experiment Name=Group Name]

例如：

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

当虚拟URL请求发送到服务器时，[!DNL Sensor]会将您标识为指定实验中指定组的成员，然后将您重定向到网站的根。 您现在可以导航到网站上的相应位置，以验证该实验和组是否显示了正确的内容。

如果您要在浏览器中键入以下内容，浏览器将显示网站的主页，并将您放入New_Homepage实验中的index2组：

[!DNL http://www.omniture.com/setcookie.htm?New_Homepage=index2]

当index2组中的访客请求主页时，页面上的“请求演示”图形链接会显示得更高，如下图所示：

![](assets/TestPage.png)
