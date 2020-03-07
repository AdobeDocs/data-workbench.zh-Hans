---
description: 延迟维度是通过一个可计数父维度（如“会话”）和一个时间维度（如“日”）构建的。
solution: Analytics
title: 创建延迟维度
topic: Data workbench
uuid: 531d8bf6-a66f-4b02-9d81-05664fb9c988
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 创建延迟维度{#create-a-latency-dimension}

延迟维度是通过一个可计数父维度（如“会话”）和一个时间维度（如“日”）构建的。

在Data Workbench中创建延迟表时，会自动向可视化文件(.vw)添加延迟维度。 您可以按照下列步骤编辑某个表格的延迟维度。

**编辑延迟维度**

1. 在文本编辑器（如记事本）中打开您创建的延迟表格。It is located in the User > `working profile name` > Work folder within your Data Workbench installation directory.

   定义的延迟维度包括以下示例所示的参数。（您的延迟维度定义可能包含其他参数。）指示 [!DNL line entity = LatencyDim:] 延迟维度定义的开始。

   ```
   entity = LatencyDim:
   Name = string: dimension name
   Level = ref: wdata/model/dim/level
   Clip = ref: wdata/model/dim/clip
   Time = ref: wdata/model/dim/time dimension
   Format = printf_format: 
   format = string: %+0.0f time string
   offset = double: offset
   Time Before = int: time before
   Time After = int: time after
   ```

1. 参考下表，编辑 Name（名称）、Level（级别）、Clip（剪辑）、Time（时间）、Format（格式）、Time Before（此时间之前）或 Time After（此时间之后）参数的值：

   <table id="table_13DF30B8B7314F118D0ED5DF9EA70B9B"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> 对于该参数... </th> 
      <th colname="col2" class="entry"> 提供此信息... </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>名称 </p> </td> 
      <td colname="col2"> <p>可选。当您右键单击维度标签或元素时，出现在上下文菜单中的延迟维度名称。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Level（级别） </p> </td> 
      <td colname="col2"> <p>一个作为父延迟维度的可计数维度。示例包括 Session（会话）、Visitor（访客）和 Page View（页面查看）。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Clip（剪辑） </p> </td> 
      <td colname="col2"> <p>与延迟维度级别有一对多关系的一个可计数维度。延迟不可跨越该维度边界计算。例如，如果您指定页面查看级别和会话剪辑，则会计算与事件相同会话期间发生的页面查看的延迟。 </p> <p>有关一对多（简单）维度的信息，请参阅《数据集配置指南》<i></i>。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>时间 </p> </td> 
      <td colname="col2"> <p>用于计算延迟维度所经过时间的维度。该维度可以是一个时间维度（如“日”或者“小时”），也可以是可计数维度（如“访客”、“会话”或者“页面查看”）。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> 格式 </td> 
      <td colname="col2"> <p>可选。指定Data Workbench中延迟可视化的外观。 在 Format（格式）参数中，您可以编辑以下值： 
      <ul id="ul_ABF4C17BDE2E4F6C9CBDD933674DE861"> 
         <li id="li_5ED6A7267C81444983AF8507ADC6A5AB">Time string（时间字符串）。延迟可视化中所示的时间单位，如“日”或者“星期”。当您更改时间维度时，请务必更改时间字符串。 </li> 
         <li id="li_E3B517ECE1494221AAE90455CC0AAB42">Offset（偏移）。等于 Time Before（此时间之前）值的负数的整数。例如，如果 Time Before（此时间之前）是 7，则偏移量应该是 -7。 </li> 
      </ul> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Time Before（此时间之前） </p> </td> 
      <td colname="col2"> <p>计算延迟的事件前的最大时间量（以“时间”维度的单位表示）。如果该值设置为 0 或根本没有设置，则将仅为向前方向计算延迟。 </p> <p>如果更改此值，请务必更改 Format（格式）参数中的偏移值：偏移是 Time Before（此时间之前）值的负数。 </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Time After（此时间之后） </p> </td> 
      <td colname="col2"> <p>计算延迟的事件后的最大时间量（以“时间”维度的单位表示）。 </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Save the [!DNL .vw] file to the User\*working profile name*\Work folder.

   以下是默认延迟维度的设置：

   ```
   entity = LatencyDim:
   Name = string: 
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Day
   Time Before = int: 7
   Time After = int: 7
   ```

   在以下延迟维度中，以小时为单位计算每个会话事件的延迟，Time Before（此时间之前）值被设置为 0。因此，将仅为那些在定义事件发生后 24 小时内发生的会话计算延迟。

   ```
   entity = LatencyDim:
   Name = string:
   Level = ref: wdata/model/dim/Session
   Clip = ref: wdata/model/dim/Visitor
   Time = ref: wdata/model/dim/Hour
   Time Before = int: 0
   Time After = int: 24
   ```
