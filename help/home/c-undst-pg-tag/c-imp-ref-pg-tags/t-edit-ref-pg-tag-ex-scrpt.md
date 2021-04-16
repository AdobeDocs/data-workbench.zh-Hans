---
description: 引用页面标签由驻留在Web服务器上的页面标签执行脚本组成，当调用时，该脚本会为站点访客请求的页面收集所有客户端数据。
title: 编辑参考页面标记执行脚本
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
exl-id: bc922b59-716e-4e92-84b5-59a52620df03
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 6%

---

# 编辑参考页面标记执行脚本{#editing-the-reference-page-tag-execution-script}

引用页面标签由驻留在Web服务器上的页面标签执行脚本组成，当调用时，该脚本会为站点访客请求的页面收集所有客户端数据。

您可以修改[!DNL Reference Page Tag Execution Script]以收集在与Adobe咨询服务团队召开会议时可能需要识别的其他信息。 [!DNL Reference Page Tag Execution Script]相对较小，可避免在网页中添加大量下载内容。

在名为[!DNL zig.js]的文件中为您提供了以下[!DNL Reference Page Tag Execution Script]代码：

```
//REFERENCE PAGE TAG 
// CONSTANTS 
var ct = "<img src="; 
var cd = "[PATH_TO_WEB_SERVER]"; //this should contain the domain of 
                               //the web site that will host the 
                                //page tag 
 
var cu = "[PATH_TO_WEB_PAGE_TAG_CODE]/zag.gif?Log=1";  
                                 //this should contain the full path to 
                                 //the zag.gif file (excluding domain) 
                                 //and include the query string of log=1 
var ce = ">"; 
var c = {}; 
c["sw"] = screen.width; 
c["sh"] = screen.height; 
c["cd"] = screen.colorDepth; 
var co = ""; 
 
for ( cKey in c ) { 
co = co+"&"+cKey+"="+escape(c[cKey]); 
} 
document.write(ct,cd,cu,co,ce); 
 
var d = {}; 
d["dt"] = document.title; 
d["dr"] = document.referrer; 
d["cb"] = new Date().getTime(); 
var vo = ""; 
 
if (typeof v != "undefined") { 
for ( vKey in v ) { 
vo = vo+"&"+vKey+"="+escape(v[vKey]); 
} 
} 
for ( dKey in d ) { 
vo = vo+"&"+dKey+"="+escape(d[dKey]); 
} 
document.write(ct,cd,cu,vo,ce); 
//END REFERENCE PAGE TAG 
```

要通过使用[!DNL Reference Page Tag]便于数据收集，请完成以下步骤：

1. 创建名为[!DNL zag.gif]的1个像素× 1个像素图像文件，或将其放置到Web服务器上的目录中。
1. 修改cd变量以引用引用[!DNL zag.gif]文件的网站或Adobe托管服务域的相应域。 通过执行[!DNL zig.js]文件函数创建对文件的引用。 例如：

   ```
   //www.mysite.com
   ```

1. 修改cu变量以引用[!DNL zag.gif]文件位置的适当路径。 例如

   ```
   /scripts
   ```

1. 确保为[!DNL zag.gif]和[!DNL zig.js]文件建立了适当的缓存控制标头。
