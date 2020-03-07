---
description: 引用页面标记执行调用将插入到要为其收集测量数据的网页中。
solution: Analytics
title: 添加引用页面标记执行调用
topic: Data workbench
uuid: 8c682649-d1b1-40a6-a2b2-4ff5a92b732f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 添加引用页面标记执行调用{#adding-reference-page-tag-execution-calls}

引用页面标记执行调用将插入到要为其收集测量数据的网页中。

它应包含在HTML文档的正文中，并可以放在全局包含页脚中（如果适用）。 您的 [!DNL Reference Page Tag Execution Call] 团队可以修改该组件，以收集可能在要求收集与Adobe咨询服务团队的会议期间确定的其他信息。

为便于通过使用数据收集，请 [!DNL Reference Page Tag]完成以下步骤：

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

1. 修改指向和文件位置的 [!DNL zig.js] 路 [!DNL zag.gif] 径。 例如：

   ```
   //www.mysite.com/scripts/zig.js 
   //www.mysite.com/images/zag.gif 
   ```

请确保在您的Web服务器上设置了相应的HTTP Cache-Control头，以确保浏览器不对 [!DNL zig.js]和 [!DNL zag.gif] 文件进行缓存。 可以使用两种方法之一设置HTTP Cache-Control头信息。 第一种方法是通过Web服务器设置HTTP头。 第二种方法是使用脚本为每个特定页面或嵌入对象设置HTTP头。 使用脚本方法时，网页必须使用JSP或ASP等编程语言创建。 然后，将对页面进行脚本编写，以便其发送相应的标题信息。 此方法有两个明显的缺点：1)必须对所有页面进行编码才能发送标题，2)页面不能是静态HTML，这对Web服务器性能有一定影响。

在Microsoft IIS上运行的网站可以通过Microsoft管理控制台添加相应的HTTP头。 通过Netscape iPlanet Web Server提供的网站可以通过编辑站点配置目 [!DNL obj.conf] 录中的文件来实现此目的。 Apache Web Server使网站管理员能够使用随附的mod_headers模块自定义HTTP头，其中AOLServer通过使用Tcl模块可自定义。 在实施HTTP Cache-Control头之前，您应参阅特定于Web服务器平台的文档。

通常，HTTP头的结构应如下：

```
Cache-Control: no-cache 
Pragma: no-cache 
Expires: -1
```

