---
description: 营销网站可能涉及在第三方网站上以图像或其他富媒体文件（从Web服务器提供）形式投放广告。
solution: Analytics
title: 衡量广告印象
topic: Data workbench
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 衡量广告印象{#measuring-advertisement-impression}

营销网站可能涉及在第三方网站上以图像或其他富媒体文件（从Web服务器提供）形式投放广告。

在这种情况下，您可能希望衡量广告在浏览器上的印象以及随后对您网站上广告的目标URL的点进（如果出现）。

对于以图像形式的广告，附加到查询字符串的 [!DNL Log=1] 结果是图像请求，从而由于分析目的而捕获广告 [!DNL Sensor] 印象。

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_ic= | 表示印象营销活动的价值 | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | 表示印象营销活动资产的值 | v_ica=&quot;72890ab&quot; |
| v_icr= | 表示印象营销活动引荐的值 | v_icr=&quot;http://money.cnn.com/markets/ |

除了附加到图像请求之外 [!DNL Log=1] ，还应将标识符添加到从广告到网站中目标页面的URL中，以跟踪导致点击的广告，并跟踪点击返回到该广告的特定营销活动。

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
   <td colname="col2"> 指示点进营销活动的值 </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> 指示点进营销活动资产的值 </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> 指示点进营销活动引用的值 </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>市场／市场/ </p> </td> 
  </tr> 
 </tbody> 
</table>

