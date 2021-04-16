---
description: 初始化和更新配置文件的架构定义
title: 初始化和更新配置文件的架构定义
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# 初始化和更新配置文件的架构定义{#initializing-and-updating-a-profile-s-schema-definition}

1. 为要设置的用户档案打开&#x200B;**[!UICONTROL Schema Builder]**。
1. 从Insight用户档案检索模式时，将显示&#x200B;**[!UICONTROL Loading]**&#x200B;消息。 加载模式的时间长度取决于加载用户档案的复杂性。
1. 完成后，您将看到左窗格中&#x200B;**[!UICONTROL Insight Schema]**&#x200B;与右窗格中&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;之间差异的摘要。 此摘要将显示在&#x200B;**[!UICONTROL Schema Builder]**&#x200B;窗口的左下部。

   >[!NOTE]
   >
   >首次设置模式时，每个量度、维度和筛选器的列表将与仪表板的模式不同。 这是因为仪表板模式对象此时不存在。

   ![](assets/schema_builder2.png)

1. 单击&#x200B;**[!UICONTROL Synchronize with Schema]**&#x200B;按钮，将Insight模式视图中的所有量度、维度和过滤器与仪表板模式视图同步。
1. 完成后，您应当看到一条消息，指示未找到任何差异：

   ![](assets/diff_found.png)

1. 如果仪表板模式有任何错误，例如重复量度和维度，则必须先手动更正它们，然后才能保存。

   >[!NOTE]
   >
   >您可以有选择地从&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;中删除您不希望显示给该仪表板最终用户的任何量度、维度或过滤器。 您将收到一条警告，指出仪表板模式中不存在项目，但不会阻止您进行保存。

1. 准备就绪后，单击&#x200B;**[!UICONTROL Save]**&#x200B;以保存对仪表板模式所做的更改。
1. 仪表板系统将使用此模式定义填充仪表板界面的最终用户可用的维度、量度和过滤器。
