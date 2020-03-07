---
description: 通过使用参考页面标记来简化链接点击的收集步骤。
solution: Analytics
title: 跟踪链接点击
topic: Data workbench
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 跟踪链接点击{#tracking-link-clicks}

通过使用参考页面标记来简化链接点击的收集步骤。

通过部署，可 [!DNL Reference Page Tag]以收集指示访客在访问特定页面时点击的链接（或href值）的测量数据。 通常，此集合不涉及在HTML页面中实施其他链接标识符。

要通过使用方便收集链接点击次数，请 [!DNL Reference Page Tag]完成以下步骤：

1. 将以下代码复制到名为的现有文件中 [!DNL zig.js]:

   ```
   //REFERENCE LINK AND FORM CLICK PAGE TAG 
   //INITIATE FUNCTIONS ONLOAD 
   function addEvent(obj, evType, fn){  
    if (obj.addEventListener){  
      obj.addEventListener(evType, fn, false);  
      return true;  
    } else if (obj.attachEvent){  
      var r = obj.attachEvent("on"+evType, fn);  
      return r;  
    } else {  
      return false;  
    }  
   } 
   addEvent(window, 'load', startCapture); 
   addEvent(window, 'load', startCapture); 
   function startCapture(){ 
   //TO CAPTURE LINK CLICKS 
     if (vlc == "1"){captureLink();} 
     //TO CAPTURE FORM FIELD CLICKS 
     if (vfc == "1"){captureForm();} 
   } 
   //BEGIN LINK CAPTURE PAGE TAG 
   function captureLink(){ 
     if (document.links[0]){ 
       if (document.links){ 
         var links = document.links, link, k=0; 
         while(link=links[k++]) { 
           link.onclick = captureLinkName; 
    } 
       } 
     } 
   } 
   function captureLinkName() { 
     var lc=new Image(); 
     this.parent = this.parentNode; 
     lc.src='zag2.gif?linkname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END LINK CAPTURE PAGE TAG 
   //BEGIN FORM CLICK CAPTURE PAGE TAG 
   function captureForm(){ 
     if (document.forms[0]) { 
       if(document.forms){ 
    for(i=0; i<document.forms[0].elements.length; i++){ 
           var forms = document.forms[0].elements[i]; 
           forms.onfocus = captureFormName; 
         } 
       } 
     } 
   } 
   function captureFormName() { 
     var fc=new Image(); 
     fc.src='zag3.gif?fieldname=' + escape(this.name) + "&cd=" + new Date().getTime(); 
   } 
   //END FORM CLICK CAPTURE PAGE TAG
   ```

1. 创建或放置名为“1 x 1像素”的图像文件，并将其放 [!DNL zag2.gif] 置到Web服务器上现有的目录中。
1. 修改变 [!DNL lc.src] 量以引用引用文件的网站的相 [!DNL zag2.gif]应域。

1. 确保为和文件建立了适当的缓存控 [!DNL zag.gif] 制头 [!DNL zig.js] 。

1. 在要从中收集链接点击值的HTML文件中，必 [!DNL Reference Page Tag Execution Call] 须修改链接点击值，以通知 [!DNL Page Tag Execution Script] 捕获该页面的链接点击。 为此，请将vlc变量值更改为“1”，如下面的代码示例中高亮显示：

```
<!-- BEGIN REFERENCE PAGE TAG--> 
<script language="javascript"> 
var vlc = "1" //Capture Link Click  1=TRUE, 0=FALSE 
var vfc = "0"; //Capture Form Field Click  1=TRUE, 0=FALSE 
var v = {}; 
</script> 
 
<script language="javascript" src=”http://www.myserver.com/path/to/zig.js" type="text/javascript"></script> 
 
<noscript> 
<img src="/path/to/zag.gif?Log=1&v_jd=1" border="0" width="1" height="1"/> 
</noscript> 
 
<!-- END REFERENCE PAGE TAG-->
```

| 收集的数据 | 说明 | 示例 |
|---|---|---|
| v_ln= | 表示印象营销活动的价值 | v_ln=&quot;About%20Us&quot; |

