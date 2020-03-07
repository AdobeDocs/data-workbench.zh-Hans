---
description: 引用页面标记由驻留在Web服务器上的页面标记执行脚本组成，当调用该脚本时，会为站点访客请求的页面收集所有客户端数据。
solution: Analytics
title: 编辑参考页标记执行脚本
topic: Data workbench
uuid: 0db00b89-e420-423d-9b88-8b724baa828f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 编辑参考页标记执行脚本{#editing-the-reference-page-tag-execution-script}

引用页面标记由驻留在Web服务器上的页面标记执行脚本组成，当调用该脚本时，会为站点访客请求的页面收集所有客户端数据。

您可以修改以收 [!DNL Reference Page Tag Execution Script] 集在要求收集与Adobe咨询服务团队的会议期间可能识别的其他信息。 它的 [!DNL Reference Page Tag Execution Script] 尺寸相对较小，可避免为网页添加大量下载内容。

以下代 [!DNL Reference Page Tag Execution Script][!DNL zig.js]码位于名为的文件中：

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

为便于通过使用数据收集，请 [!DNL Reference Page Tag]完成以下步骤：

1. 创建或放置名为“1 x 1像素”的图像文件，并将其放 [!DNL zag.gif] 置到Web服务器上现有的目录中。
1. 修改cd变量以引用您的网站或从中引用文件的Adobe托管服务 [!DNL zag.gif] 域的相应域。 通过执行文件函数创建对文件 [!DNL zig.js] 的引用。 例如：

   ```
   //www.mysite.com
   ```

1. 修改cu变量，以引用文件位置的相应路 [!DNL zag.gif] 径。 例如

   ```
   /scripts
   ```

1. 确保为和文件建立了适当的缓存控 [!DNL zag.gif] 制头 [!DNL zig.js] 。
