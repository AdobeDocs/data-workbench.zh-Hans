---
description: 归因配置文件是可直接使用的继承配置文件。将此配置文件与 Adobe SC 配置文件和 Analytics (SC/Insight) 数据源一起部署，可以快速揭露跨数字渠道的新归因模型。
title: 部署归因配置文件
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 68%

---

# 部署归因配置文件{#deploying-the-attribution-profile}

{{eol}}

归因配置文件是可直接使用的继承配置文件。将此配置文件与 Adobe SC 配置文件和 Analytics (SC/Insight) 数据源一起部署，可以快速揭露跨数字渠道的新归因模型。

将归因配置文件保存到主服务器以后，需要另外执行两个步骤以集成到 [!DNL Profile] 目录中的当前配置文件：(1) 设置 Profile.cfg 文件， (2) 声明必填字段。

## 设置 Profile.cfg 文件 {#section-7531cb865d994207baba692a6fc842d7}

与所有配置文件一样，需要将归因配置文件添加到 [!DNL profile.cfg] 文件。因为归因配置文件依赖于 Adobe SC 配置文件，需要在配置文件中首先列出 Adobe SC 配置文件，位置保持在归因配置文件之前。

>[!NOTE]
>
>这些步骤需要重新转换数据集。

1. 在您的自定义配置文件文件夹中打开 [!DNL profile.cfg] 文件。(在中打开 [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. 如果归因配置文件未列在配置文件中，请将其添加到列表中。 ![](assets/new_profile_cfg.png)

1. 确保 **[!UICONTROL Attribution]** 字符串列在下面 **[!UICONTROL Adobe SC]** 配置文件字符串。

1. 保存更新后的 [!DNL profile.cfg] 文件，然后将其从配置文件管理器保存到服务器。

## 声明必填字段 {#section-23d4273af0c34b7a85ae3430e2c9350e}

归因配置文件包含预定义的字段以及一系列转换，将这些字段以新的实用方式用于扩展维度。要提供最直接的值，归因配置文件依赖于 Adobe SC 配置文件可用的字段。

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 默认变量 </th> 
   <th colname="col2" class="entry"> 字段名称和解码器位置 (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 促销活动 </td> 
   <td colname="col2"> <p>x-campaign，#199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 营销渠道 </td> 
   <td colname="col2"> <p>x-va_closer_detail，#162 </p> <p>x-va_instance_event，#163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 订购事件 </td> 
   <td colname="col2"> <p>x-order，#206 </p> <p>x-purchaseid，#200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 收入 </td> 
   <td colname="col2"> x-revenue，#205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 件数 </td> 
   <td colname="col2"> <p>x-units，#204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. 确认这些用于定义 Adobe Analytics 数据源的字段已在解码器组中声明。默认解码器组在 [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. 验证是否在 **[!UICONTROL Fields]** 部分 [!DNL SC Fields.cfg] 文件。 此文件可位于 [!DNL Dataset\Log Processing\SC Fields.cfg].

## 归因增加项和疑难解答 {#section-168133a8a1a54e1281e532033878d246}

归因配置文件添加了一个配置文件， [!DNL 0a_Marketing Channels.cfg]，它复制 [!DNL x-va_closer_detail] 输入名为 [!DNL x-marketing-channel]，当 [!DNL x-va_instance_event] 字段与“1”匹配。 两者兼有 [!DNL x-va_closer_detail] 和 [!DNL x-va_instant_event] 默认情况下，将进行解码，并在您更新到版本6.2时，从已安装包中的解码进行传递。

然后在称作“营销渠道”的简单维度中使用 [!DNL x-marketing-channel] 字段。

>[!IMPORTANT]
>
>如果您通过删除以前未使用的当前正在使用的字段来更改用户档案，则需要验证 [!DNL x-va_closer_detail] 和 [!DNL x-va_instance_event] 字段正在解码并传递以供使用。

如果字段缺失，您会收到详细的状态信息：

```
<b>x-va_closer_detail</b> is not available
```

或

```
<b>x-va_instance_event</b> is not available
```
