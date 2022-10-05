---
description: 配置时间维度以正确显示区域设置。
title: 本地化时间维度
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
exl-id: 950fe70b-a687-4b9c-b29f-555139740809
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 66%

---

# 本地化时间维度{#localizing-time-dimensions}

{{eol}}

配置时间维度以正确显示区域设置。

您可以在 **[!DNL Standard Time Dimensions.cfg]** 文件(默认位于 **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard TimeDimension.cfg]**)。

例如，在北美，您可以将日期表示为2015年5月3日5/3/15，或 **`%m/%d/%y`**. 然而，在世界其他地区，这可以解释为 `%d/%m/%y`，或2015年3月5日，由于值存在歧义。 为了避免出现这种情况，管理员可能需要更改显示格式以满足某个区域设置中用户的期望。

## 1.覆盖Standard Time Services.cfg中的默认时间DimensionDimension {#section-7d0b24657bef4b15abb3cbea66cb617f}

若要启用这项功能，管理员必须覆盖默认设置，具体方法是：编辑现有的时间维度，或者使用其他参数创建新的时间维度。

下面是有关修改时间维度的示例。

在这个示例中，星期、小时、天、月份以及一天每个小时的&#x200B;**格式**&#x200B;值都被设置为默认值。

>[!NOTE]
>
>如果忽略这些行，Data Workbench的行为将不会更改，并且将使用默认值编译维度。

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. 配置 meta.cfg 文件 {#section-5e077d3298dd48fda7f7bb16af9ea00c}

此外，包管理员有必要将这些参数及其默认设置添加到配置文件的 **[!DNL meta.cfg]** 文件中。这样操作后可以通过工作站进行编辑。

下面是有关一个已配置的 **[!DNL meta.cfg]** 文件的摘要。

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

下面是工作站中的一个 **[!DNL meta.cfg]** 文件示例：

![](assets/dwb_time_format.png)

接下来，管理员可以进入&#x200B;**文件管理器**，打开配置时间维度的文件（例如 **[!DNL Standard Time Dimensions.cfg]**），然后，在工作站中对其进行编辑。
