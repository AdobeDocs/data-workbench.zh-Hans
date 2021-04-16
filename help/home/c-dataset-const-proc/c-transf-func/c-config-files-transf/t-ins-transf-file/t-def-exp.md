---
description: 导出程序为输出事件数据提供了说明。
title: 定义导出程序
uuid: 565d4482-6c25-407c-bda7-0d116180902a
exl-id: 5de6266a-e959-414c-9512-5e9f4011881b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1120'
ht-degree: 90%

---

# 定义导出程序{#defining-exporters}

导出程序为输出事件数据提供了说明。

转换功能提供了三种类型的导出器，用于将[!DNL .vsl]文件、日志文件、XML文件和ODBC数据导出为[!DNL .vsl]文件、文本文件或分隔文本文件，这些文本文件可由DataWarehouse加载例程、审计机构或其他目标使用。

>[!NOTE]
>
>要使导出器正常工作，日志源必须满足[日志处理配置文件](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)的[日志源](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea)部分中讨论的适当要求。

**定义导出程序**

1. 在Data Workbench中打开[!DNL Transform.cfg]。 请参阅[编辑Insight Transform.cfg文件](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13)。
1. 右键单击&#x200B;**[!UICONTROL Exporters]**，然后单击&#x200B;**[!UICONTROL Add New]**。
1. 选择以下选项之一：

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**

   >[!NOTE]
   >
   >对于[!DNL ExportVSLFile]选项，输入文件中的所有扩展字段和表单cs(*header*)的所有用户定义字段始终写入VSL输出文件。 如果您覆盖现有扩展字段，则新值会写入输出文件中，即使该字段为空也是如此。

1. 参考下表，编辑该配置文件中的 Exporters（导出程序）参数：

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> 参数 </th> 
      <th colname="col2" class="entry"> 描述 </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Data Format（数据格式） </td> 
      <td colname="col2"> <p>仅用于 <span class="wintitle">ExportTextFile</span>。每个输出行的格式，由字段名称转义（以 %<i>字段名称</i>% 表示）以及其他任何所需固定文本组成。该格式应该包含行分隔符（通常是 [CR][LF]）。 </p> <p> 通过如下方式转义文本形式的百分号 (%)，可以将该字符嵌入格式字符串中：%% </p> <p> Data Format（数据格式）参数条目的示例为 <span class="filepath">%x-timestring% %x-trackingid%[CR][LF]</span>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 字段 </td> 
      <td colname="col2">仅用于 <span class="wintitle">ExportDelimitedTextFile</span>。要输出的字段名称。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 分隔符 </td> 
      <td colname="col2"> <p>可选。仅用于 <span class="wintitle">ExportDelimitedTextFile</span>。在输出文件中用于分隔字段的字符。 </p> <p> 软件无法转义数据值中包含的分隔符。因此，Adobe 建议不要将逗号用作分隔符。 </p> <p> 如果按住 Ctrl 键并且右键单击 Delimiter（分隔符）参数内部，则会显示“<span class="wintitle">插入</span>”菜单。此菜单包含通常用作分隔符的特殊字符列表。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Line Separator（行分隔符） </td> 
      <td colname="col2">可选。仅用于 <span class="wintitle">ExportDelimitedTextFile</span>。在输出文件中用于分隔行的字符。默认值为 [CR][LF]。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 名称 </td> 
      <td colname="col2"> <p>可选。导出程序的标识符。此名称显示在<span class="wintitle">详细状态</span>界面中。 </p> <p> 有关<span class="wintitle">详细状态</span>界面的信息，请参阅《Data Workbench 用户指南》<i></i>。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> 评论 </td> 
      <td colname="col2"> 可选。有关导出程序的说明。 </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Output Path（输出路径） </td> 
      <td colname="col2"> <p>存储输出文件的路径。该路径相对于 Data Workbench Server 安装文件夹。 </p> <p> <p>注意：存储输出数据的 Data Workbench Server 是 <span class="filepath">profile.cfg</span> 文件中的处理服务器 #0。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> File Rotation Period（文件旋转周期） </td> 
      <td colname="col2"> <p>可选。数据导出至输出文件的频率。每个输出文件都包含与特定时间段（称为旋转周期）相关的数据。所有时间计算都采用 GMT：一天从午夜 GMT 开始，于后一日的午夜 GMT 结束，即使写入文件的数据包含已转换为本地时间的字段也是如此。 </p> <p> 可用值如下： </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> YEAR（年）。每个文件都包含一个日历年的数据。 </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MONTH（月）。每个文件都包含一个日历月的数据。月份按 1（1 月）到 12（12 月）进行编号。 </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> WEEK（周）。每个文件都包含一周的数据。一周从星期一开始。始于一年中第一个七天中的某一天的周为第 1 周，之前的（部分）周（如果有）为第 0 周。 </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> DAY（日）。每个文件都包含一个日历天的数据。 </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> HOUR（小时）。每个文件都包含一小时的数据。 </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NONE（无）。不执行任何旋转。所有数据都写入同一个文件（或由其他参数设置确定的一组文件）中。请参阅此表中的 <span class="wintitle">File Name Format</span>（文件名格式）参数。 </li> 
      </ul> <p>默认文件旋转周期为 DAY（日）。 </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> 仅当在<span class="wintitle">离线模式</span>下进行操作时，才将文件旋转设为 NONE（无）。请参阅<a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13">脱机模式</a>参数说明。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> File Name Format（文件名格式） </td> 
      <td colname="col2"> <p>可选。输出文件名称的格式。 </p> <p> 每个日志条目的存储文件名称可以从旋转周期的开始时间派生，或者，也可以从该文件包含的行字段值派生。文件名中使用的字段会作为字段名称转义（以 %<i>字段名称</i>% 表示）来嵌入。 </p> <p>与旋转周期相关的文件名组件会嵌入使用以下转义序列的格式字符串中： 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy%（四位数年份） </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy%（两位数年份） </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm%（两位数月份，01 - 12） </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww%（两位数周数，01 - 52） </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd%（两位数日期，01 - 31） </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH%（两位数小时，00 - 23） </li> 
      </ul> </p> <p> 默认文件名格式为 <span class="filepath">%yyyy%%mm%%dd%-%x-mask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> 转义序列区分大小写。 </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> 当 File Rotation Period（文件旋转周期）设为 NONE（无）时，每个转义序列（如果有）会替换为空字符串。 </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> 如果 <span class="wintitle">File Name Format</span>（文件名格式）没有为每个旋转周期生成唯一的文件名（请参阅此表中的 File Rotation Period（文件旋转周期）参数），则会生成错误。例如，在使用 DAY（日）旋转周期时，%dd%、%mm% 和 %yy% 或 %yyyy% 转义序列必须以该模式存在以避免数据丢失。 </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> 如果您在模式中使用字段名称转义序列，并且给定字段有多个不同的值，则会为每个旋转周期写入多个输出文件。请注意，此方案可能会导致性能降低，因此应该谨慎使用此功能。 </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> 所有时间计算都采用 GMT。 </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Execute at Rollover（在滚动时执行） </td> 
      <td colname="col2"> <p>可选。在完成每个文件之后，可以执行外部 (Windows) 命令。通过将此参数替换为以下转义序列，可以从最终文件名派生命令行： </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%。最终文件名的目录部分，包括尾部的反斜杠。 </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%。最终文件的名称（不包括目录和扩展名）。 </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%。最终文件名的扩展名（包括前置的“.”）。 </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %path%。文件的完整路径名，等同于 %dir%%file%%ext%。 </li> 
      </ul> <p> 默认情况下，此参数为空（不执行任何命令）。 </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Memory Limit（内存限制） </td> 
      <td colname="col2"> <p>可选。用于缓冲导出程序的输出的内存量（以字节为单位）。默认值为 10,000,000 字节。 </p> <p> <p>注意：如果您的多个输出文件同时打开，则可能需要增大此值，但这可能会减少可供其他系统组件使用的内存量。而减小此值则可能会减慢导出过程。要寻求帮助，请联系 Adobe。 </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Open Files Limit（打开文件限制） </td> 
      <td colname="col2"> <p>可选。可同时从导出程序打开以进行输出的最大文件数。如果超过此数量，则事件日志中会记录一条错误，并且 Data Workbench Server 会停止运行。默认值为 1000。 </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. 在 [!DNL Transform.cfg] 文件中定义导出程序（并对其他参数进行更改）之后，将该文件保存在本地，然后将其保存到 Data Workbench Server 计算机上的相应配置文件中。
