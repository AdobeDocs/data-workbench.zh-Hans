---
description: 通过使用参考页面标记来促进收集链接点击量的步骤。
title: 跟踪链接点击量
uuid: e4c492d2-9c90-4ed7-b997-6c50bdf98f93
exl-id: 0cb743e6-5c6e-4f80-bc77-83d1e706c92b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# 跟踪链接点击量{#tracking-link-clicks}

通过使用参考页面标记来促进收集链接点击量的步骤。

通过部署[!DNL Reference Page Tag]，可以收集表示访客在访问特定页面时所点击的链接（或href值）的测量数据。 通常，此集合不涉及在HTML页面中实施其他链接标识符。

要通过使用[!DNL Reference Page Tag]方便收集链接点击量，请完成以下步骤：

1. 将以下代码复制到名为[!DNL zig.js]的现有文件中：

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

1. 创建名为[!DNL zag2.gif]的1个像素乘1像素图像文件，或将其放入Web服务器上存在的目录中。
1. 修改[!DNL lc.src]变量以引用从中引用[!DNL zag2.gif]文件的网站的相应域。

1. 确保为[!DNL zag.gif]和[!DNL zig.js]文件建立了适当的缓存控制标头。

1. 在要从中收集链接点击值的HTML文件中，必须修改[!DNL Reference Page Tag Execution Call]以通知[!DNL Page Tag Execution Script]以捕获该页面的链接点击量。 为此，请将vlc变量值更改为“1”，如下面的代码示例中突出显示：

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
| v_ln= | 表示展示型营销活动的值 | v_ln=&quot;About%20Us&quot; |
