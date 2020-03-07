---
description: 对于所有语言，Report Server 6.0和更高版本要求将“insight.zbin”文件复制到Report Server根文件夹。
solution: Analytics
title: 使用语言文件（.zbin文件）更新报告服务器
topic: Data workbench
uuid: 2ecf2afc-bb5f-4fc7-8fb8-a904fb7ed407
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Update Report Server with a language file (.zbin file){#update-report-server-with-a-language-file-zbin-file}

对于所有语言，Report Server 6.0和更高版本要求将“insight.zbin”文件复制到Report Server根文件夹。

更新 Report Server 语言文件：

1. 将重命名的“insight.zbin”文件添加到报表服务器根目录中。
1. Report Server 配置文件 (reportserver.cfg) 需要对双字节语言设置字体。例如，中文要求添加使用 SimSun 的字体：

   ```
   <b>Report Server.cfg - Add Fonts</b> 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. 需要在命令行中传递一个 Report Server 6.0 参数以进行本地化，例如：

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >如果未指定区域设置，则报表服务器默认为英语。

   按照以下步骤，使用区域设置参数将报表服务器作为服务启动：

   1. 以管理员身份启动命令提示符。
   1. 导航至报表服务器安装文件夹。
   1. 键入下列命令以启动该服务：

      * 对于英语： [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * 对于中文： [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. 验证报表服务器是否使用正确的参数运行：

   1. 打开 Windows 服务管理器。
   1. 右键单击 [!DNL Adobe Insight Report Server - Properties]。
   可执行文件的路径将包含以下参数：

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```
