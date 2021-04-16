---
description: 在营销您的网站时，可能会涉及在第三方网站上以图像或其他富媒体文件（从您的Web服务器提供）形式投放广告。
title: 衡量广告展示次数
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# 衡量广告展示次数{#measuring-advertisement-impression}

在营销您的网站时，可能会涉及在第三方网站上以图像或其他富媒体文件（从您的Web服务器提供）形式投放广告。

在这种情况下，您可能希望衡量广告在浏览器上的印象，以及随后点击（如果出现）到您网站上广告的目标URL。

对于以图像形式的广告，将[!DNL Log=1]附加到查询字符串导致图像请求，从而由[!DNL Sensor]为分析目的捕获广告印象。

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_ic= | 表示印象活动的价值 | v_ic=&quot;活动1&quot; |
| v_ica= | 表示印象活动资产的值 | v_ica=&quot;72890ab&quot; |
| v_icr= | 表示印象活动推荐人的价值 | v_icr=&quot;http://money.cnn.com/markets/ |

除了将[!DNL Log=1]附加到图像请求之外，还应将标识符添加到从广告到您网站中目标页面的URL，以跟踪导致点进的广告，并将点进跟踪返回到该广告的特定活动。

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 收集的数据 </th> 
   <th colname="col2" class="entry"> 说明 </th> 
   <th colname="col3" class="entry"> 示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> 指示点进活动的值 </td> 
   <td colname="col3"> v_c="活动1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> 表示点进活动资产的值 </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> 表示点进活动推荐人的值 </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>市场/ </p> </td> 
  </tr> 
 </tbody> 
</table>
