---
description: 初始化和更新配置文件的架构定义
title: 初始化和更新配置文件的架构定义
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# 初始化和更新配置文件的架构定义{#initializing-and-updating-a-profile-s-schema-definition}

1. 打开要设置的配置文件的&#x200B;**[!UICONTROL Schema Builder]**。
1. 在从Insight配置文件中检索架构时，将显示&#x200B;**[!UICONTROL Loading]**&#x200B;消息。 加载架构的时间长短取决于加载的用户档案的复杂程度。
1. 完成后，您将在左窗格中看到&#x200B;**[!UICONTROL Insight Schema]**&#x200B;与右窗格中&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;之间差异的摘要。 此摘要将显示在&#x200B;**[!UICONTROL Schema Builder]**&#x200B;窗口的左下部。

   >[!NOTE]
   >
   >首次设置架构时，每个量度、维度和过滤器将与功能板的架构以不同的方式列出。 这是因为功能板架构对象当前不存在。

   ![](assets/schema_builder2.png)

1. 单击&#x200B;**[!UICONTROL Synchronize with Schema]**&#x200B;按钮可将“分析架构”视图中的所有量度、维度和过滤器与“功能板架构”视图同步。
1. 完成后，您应会看到一条消息，指示未找到任何差异：

   ![](assets/diff_found.png)

1. 如果功能板架构存在任何错误（如重复的量度和维度），则必须先手动更正它们，然后才能保存。

   >[!NOTE]
   >
   >您可以从&#x200B;**[!UICONTROL Dashboard Schema]**&#x200B;中选择性删除您不希望向功能板最终用户显示的任何量度、维度或过滤器。 您将收到一则警告，指出功能板架构中不存在项目，但不会阻止您进行保存。

1. 准备就绪后，单击&#x200B;**[!UICONTROL Save]**&#x200B;以保存对功能板架构所做的更改。
1. 功能板系统将使用此架构定义来填充功能板界面最终用户可用的维度、量度和过滤器。
