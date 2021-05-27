---
description: 参考页面标记执行调用会插入到您要为其收集测量数据的网页中。
title: 添加参考页面标记执行调用
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
exl-id: a4f9ab2b-50e8-4e0b-9c87-80dffb697316
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 3%

---

# 添加参考页面标记执行调用{#adding-reference-page-tag-execution-calls}

参考页面标记执行调用会插入到您要为其收集测量数据的网页中。

它应包含在HTML文档的正文中，并可以放置在全局包含页脚（如果适用）中。 您的团队可以修改[!DNL Reference Page Tag Execution Call]，以收集在与Adobe咨询服务团队召开的要求收集会议期间可能确定的其他信息。

要通过使用[!DNL Reference Page Tag]方便数据收集，请完成以下步骤：

1. 将以下代码复制到HTML文档正文中：

   ```
   <!--//BEGIN REFERENCE PAGE TAG--> 
   <script language="javascript"> 
   var vlc = "0" //Capture Link Click  1=TRUE, 0=FALSE 
   var v = {}; 
   </script> 
   
   <!--//MODIFIY PATH TO ZIG.JS--> 
   <script language="javascript" src="/path/to/zig.js" type="text/javascript"></script> 
   <!--//END REFERENCE PAGE TAG--> 
   
   <noscript> 
   <img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
   </noscript> 
   <!-- END REFERENCE PAGE TAG-->
   ```

1. 修改[!DNL zig.js]和[!DNL zag.gif]文件位置的路径。 例如：

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

请确保在您的Web服务器上设置了相应的HTTP Cache-Control标头，以确保浏览器不会缓存[!DNL zig.js]和[!DNL zag.gif]文件。 您可以使用两种方法之一来设置HTTP Cache-Control标头信息。 第一种方法是通过Web服务器设置HTTP标头。 第二种方法是使用脚本为每个特定页面或嵌入式对象设置HTTP标头。 使用脚本方法时，网页必须是使用JSP或ASP等编程语言创建的。 然后，将对页面进行脚本化，以便其发送相应的标头信息。 此方法有两个明显的缺点：1)必须对所有页面进行编码以发送标头，2)页面不能是静态HTML，这对Web服务器性能有一定影响。

在Microsoft IIS上运行的网站可通过Microsoft管理控制台添加相应的HTTP标头。 从Netscape iPlanet Web Server提供的网站可通过编辑站点配置目录中的[!DNL obj.conf]文件来实现此目的。 Apache Web Server使网站管理员能够使用随附的mod_headers模块自定义HTTP标头，其中AOLServer可通过使用Tcl模块进行自定义。 在实施HTTP Cache-Control标头之前，您应该参阅特定于您的Web服务器平台的文档。

通常，HTTP标头的结构应如下所示：

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```
