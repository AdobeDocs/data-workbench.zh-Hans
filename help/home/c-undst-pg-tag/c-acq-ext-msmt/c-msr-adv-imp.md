---
description: 营销您的网站可能涉及在第三方网站上以图像或其他富媒体文件（从您的Web服务器提供）形式投放广告。
title: 衡量广告展示次数
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# 衡量广告展示次数{#measuring-advertisement-impression}

{{eol}}

营销您的网站可能涉及在第三方网站上以图像或其他富媒体文件（从您的Web服务器提供）形式投放广告。

在这种情况下，您可能希望同时测量广告在浏览器上的展示次数，以及随后对您网站上广告的目标URL的点进（如果发生）。

对于以图像形式显示的广告，附加 [!DNL Log=1] 到查询字符串会导致图像请求，从而导致广告展示被捕获 [!DNL Sensor] 以便进行分析。

```
<!—REFERENCE IMPRESSION TAG->
<IMG SRC="https://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=https://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_ic= | 表示展示型营销活动的值 | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | 表示展示型营销活动资产的值 | v_ica=&quot;72890ab&quot; |
| v_icr= | 表示展示促销活动反向链接的值 | v_icr=&quot;https://money.cnn.com/markets/ |

除了附加 [!DNL Log=1] 在图像请求中，应将标识符添加到从广告到您网站目标页面的URL中，以跟踪导致点进的广告，并跟踪该广告的点进回到特定营销活动。

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=https://money.cnn.com/markets/”>
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
   <td colname="col2"> 表示点进促销活动的值 </td>
   <td colname="col3"> v_c="CAMPAIGN1" </td>
  </tr>
  <tr>
   <td colname="col1"> v_ca= </td>
   <td colname="col2"> 表示点进促销活动资产的值 </td>
   <td colname="col3"> v_ca="72890ab" </td>
  </tr>
  <tr>
   <td colname="col1"> v_cr= </td>
   <td colname="col2"> 表示点进促销活动反向链接的值 </td>
   <td colname="col3"> <p> <span class="filepath"> v_cr="https://money.cnn.com/</span> </p> <p>市场/ </p> </td>
  </tr>
 </tbody>
</table>
