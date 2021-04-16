---
description: 有关工作表表达式和使用单元格引用的概念性信息。
title: 工作表表达式
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 92%

---

# 工作表表达式{#worksheet-expressions}

有关工作表表达式和使用单元格引用的概念性信息。

以下工作表提供对某个银行网站的联机申请表上提供的申请向导页面进行查看的访客详细信息。

![](assets/client-wkst.png)

* A 列显示所评估的访客的类别列表：访客、推荐访客和推荐人 A 推荐的访客。
* B 列显示每个类别中查看了立即申请页面的访客数。
* C 列显示同时查看了立即申请和申请向导页面的访客数。
* D 列包含三个类别中立即申请页面查看者同时也查看了申请向导页面的百分比。

工作表显示大约有 55% 的推荐人 A 推荐的访客同时查看了立即申请页面和申请向导页面。

下表为上面示例中的工作表提供了示例公式：

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 工作表单元格 </th> 
   <th colname="col2" class="entry"> 公式 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>查看立即申请页面的访客数 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>查看立即申请页面的推荐访客数 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>查看立即申请页面的推荐人 A 推荐的访客数 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath">Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>查看立即申请页面和申请向导页面的访客数 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitors[Page="/applynow/default.asp" </span> </p> <p> AND <span class="filepath">Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>查看立即申请页面和申请向导页面的推荐访客数 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_访客s[Page="/applynow/default.asp"  </span> </p> <p> AND <span class="filepath">Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>查看立即申请页面和申请向导页面的推荐人 A 推荐的访客数 </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Referred_Visitors[Page="/applynow/default.asp"</span> </p> <p> AND <span class="filepath">Page="/applynow/appwizard.asp"</span> </p> <p> AND <span class="filepath">Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>查看立即申请页面和申请向导页面的访客数百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>查看立即申请页面和申请向导页面的推荐访客数百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>查看立即申请页面和申请向导页面的推荐人 A 推荐的访客数百分比 </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

与其他可视化一样，当您在工作区中的另一个可视化中进行选择时工作表会自动更新。有关进行选择的详细信息，请参阅[在可视化中进行选择](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746)。

以下 Web 数据示例在每天的会话数可视化中选择了若干天的会话数据。工作表显示在所选择的时间段内，大约有 69% 的推荐人 A 推荐的访客同时查看了立即申请页面和申请向导页面。如果没有此选择（如上文中的示例所示），那么大约有 55% 的推荐人 A 推荐的访客同时查看了立即申请页面和申请向导页面。

![](assets/client-exp.png)

## 使用单元格引用  {#section-0004e315c9c94d359b1a8a39794ba555}

不管是在工作表自身的表达式中还是在其他表达式中，都可以将任何字符串替换为单元格引用。

* **简单单元格引用：**&#x200B;单元格 A2 包含 Visitors 一词，该单元格用作标题。单元格B2包含[!DNL eval(A1)]，其计算结果为[!DNL =Visitors]。

* **过滤单元格引用：**&#x200B;单元格 A5 包含昨天的日期。单元格B5包含[!DNL访客[ Day=A5 ]]，计算结果为昨天的访客数。

* **级联单元格引用：**&#x200B;单元格 A5 包含今天的日期，单元格 A6 包含 08:00 到 08:59 一个小时的时间段。单元格B6包含[!DNL访客[小时=A5+&quot; &quot;+A6 ]]，其计算结果是当前在上午8:00到上午9:00之间的访客数。
