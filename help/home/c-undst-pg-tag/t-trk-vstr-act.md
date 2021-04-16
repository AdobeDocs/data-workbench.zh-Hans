---
description: 使用Flash构建的网站需要对捕获在富媒体内容中执行的访客操作给予特别关注。
title: 跟踪 Flash 富媒体内容中的访客活动
uuid: fe2e75eb-0897-4f63-b582-b4f1fdce02a1
exl-id: f51c7034-a7fd-4575-80e1-18fc6513ca2b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 7%

---

# 跟踪 Flash 富媒体内容中的访客活动{#tracking-visitor-activity-within-flash-rich-media-content}

使用Flash构建的网站需要对捕获在富媒体内容中执行的访客操作给予特别关注。

使用[!DNL Flash]ActionScript，您可以对现有[!DNL Flash]影片进行简单更改，以便跟踪与影片的所有访客交互，如按钮单击或鼠标移动。

为了便于[!DNL Flash]电影中的访客活动跟踪，请执行以下步骤：

1. 将以下ActionScript代码添加到影片。 此代码表示一个函数，该函数可由要跟踪的[!DNL Flash]电影中的事件调用。

   ```
   // FLASH TAG CODE BEGIN 
   var FLASHTAGURI = "[PATH_TO_WEB_SERVER]/flashtag.txt"; 
   function tag(PAGENAME,VARIABLES) { 
   loadVariablesNum(FLASHTAGURI+”?”+"PAGENAME="+PAGENAME+"&"+VARIABLES,0); 
   } 
   // FLASH TAG CODE END
   ```

1. 创建一个名为[!DNL flashtag.txt]的空文件，并将该文件放置到Web服务器上。
1. 在步骤1中的函数中，将\[[!DNL PATH_TO_WEB_SERVER]\]占位符替换为[!DNL flashtag.txt]文件位置的完全限定或相对路径。 例如：

   ```
   var FLASHTAGURI = http://www.mysite.com/flashtag/flashtag.txt”;
   ```

1. 将以下ActionScript代码添加到要跟踪的所有事件。 此代码表示用于捕获有关事件的数据的函数调用：

   ```
   on(release) {tag("[PUT_PAGE_NAME_HERE]","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   此示例说明了on(release)事件的使用；但是，tag()函数可能通过您可能希望跟踪的任何事件引用，如on(press)、on(rollove)、on(rollout)或on(keypress)事件。

   应将\[[!DNL PUT_PAGE_NAME_HERE]\]占位符替换为一个字符串，该字符串表示要跟踪的页面或事件的名称。 可以手动或通过变量引用修改\[[!DNL PUT_PAGE_NAME_HERE]\]变量，以表示[!DNL Flash]应用程序中页面或事件的唯一名称。 替换\[[!DNL PUT_PAGE_NAME_HERE]\]占位符的值可能由简单名称组成，也可能被构造为表示与完整URI类似的层次结构。 例如：

   ```
   on(release) {tag(“/about_us/index.swf","[PUT_ADDITIONAL_VAR_HERE]");}
   ```

   Adobe建议您在代码部署之前，为页面名称和事件名称编译一个书面规范，以便于协调业务要求和开发任务，并减少额外开发周期的可能性。

1. 如果需要，可以收集附加变量并与[!DNL Flash]电影中的页面或事件关联。 要这样做，请将\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]占位符替换为一组由&amp;符分隔的name=value对。 例如：

   ```
   on(release) {tag(“/about_us/index.swf"," var1=value1&var2=value2");}
   ```

   可以手动或通过变量引用来修改变量，以指示要收集并与页面或事件关联的其他属性。 如果没有要收集的其他适用变量，请删除\[[!DNL PUT_ADDITIONAL_VAR_HERE]\]。

   您在[!DNL Flash]富媒体内容中的访客跟踪设置现已完成。 调用事件时，将调用标记[!DNL (PAGENAME,VARIABLES)]函数，从而对以下文件发出HTTP请求。 除了可能按[!DNL Flash]电影中的定义触发的其他函数外，还将调用此函数：

   ```
   http://www.mysite.com/flashtag/flashtag.txt?PAGENAME=/about_us/index.swf&var1=value1&var2=value2
   ```

由[!DNL Flash]标记ActionScript函数产生的HTTP请求导致收集与[!DNL Flash]电影中每个事件相关的以下信息。 表(W3C名称cs-uri-查询)中的最后一行表示为函数调用中指定的其他变量收集的信息。

<table id="table_A7ED9D38F36B4405947B2F48EA94D3C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> W3C名称 </th> 
   <th colname="col2" class="entry"> 收集的数据 </th> 
   <th colname="col3" class="entry"> 说明 </th> 
   <th colname="col4" class="entry"> 示例 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> x-trackingid </td> 
   <td colname="col2"> 跟踪标识符(唯一访客) </td> 
   <td colname="col3"> 在访客的初始请求中，<span class="wintitle">传感器</span>从用户浏览器中放置的Cookie读取的标识符 </td> 
   <td colname="col4"> v1st=3C94007B4E01F9C2 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>日期 </p> <p>时间 </p> </td> 
   <td colname="col2"> 时间戳 </td> 
   <td colname="col3"> 服务器处理请求的时间(精度为100ns;准确性取决于服务器环境和NTP) </td> 
   <td colname="col4"> 2002-11-21 17:21:45.123 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc(content-type) </td> 
   <td colname="col2"> 内容类型 </td> 
   <td colname="col3"> 从服务器返回的对象类型 </td> 
   <td colname="col4"> 文本/html </td> 
  </tr> 
  <tr> 
   <td colname="col1"> sc-status </td> 
   <td colname="col2"> HTTP响应状态代码 </td> 
   <td colname="col3"> 由服务器生成的记录HTTP服务器响应状态的数字代码 </td> 
   <td colname="col4"> 200 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-stem </td> 
   <td colname="col2"> URI Stem </td> 
   <td colname="col3"> 客户端请求的URI的干部 </td> 
   <td colname="col4"> /flashtag/flashtag.txt </td> 
  </tr> 
  <tr> 
   <td colname="col1"> c-ip </td> 
   <td colname="col2"> 客户端IP </td> 
   <td colname="col3"> 请求客户端的IP地址 </td> 
   <td colname="col4"> 127.0.0.1 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s-dns </td> 
   <td colname="col2"> 服务器域名 </td> 
   <td colname="col3"> 处理请求的Web服务器的域名 </td> 
   <td colname="col4"> www.mysite.com </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(referrer) </td> 
   <td colname="col2"> 反向链接 URL </td> 
   <td colname="col3"> 客户端发送的HTTP推荐人字段的内容 </td> 
   <td colname="col4"></td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(user-agent) </td> 
   <td colname="col2"> 用户代理 </td> 
   <td colname="col3"> 用于向HTTP服务器发出请求的设备 </td> 
   <td colname="col4"> Mozilla/4.0+(compatible;+MSIE+6.0;+Windows+NT+5.1) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs(cookie) </td> 
   <td colname="col2"> 域中的客户端Cookie </td> 
   <td colname="col3"> 网站所有用户Cookie的内容 </td> 
   <td colname="col4"> <p>KL_TC1 1038058778312 </p> <p>KL972x1038058778312282052 </p> <p>KL_PVKL972 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> cs-uri-query </td> 
   <td colname="col2"> 查询字符串 </td> 
   <td colname="col3"> 客户端请求的URI的查询字符串部分（如果有） </td> 
   <td colname="col4"> PAGENAME=/about_us/index.swf&amp;var1=value1&amp;var2=value2 </td> 
  </tr> 
 </tbody> 
</table>
