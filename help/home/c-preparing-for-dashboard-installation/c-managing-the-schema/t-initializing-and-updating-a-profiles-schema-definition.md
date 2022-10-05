---
description: 初始化和更新配置文件的架构定义
title: 初始化和更新配置文件的架构定义
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# 初始化和更新配置文件的架构定义{#initializing-and-updating-a-profile-s-schema-definition}

{{eol}}

1. 打开 **[!UICONTROL Schema Builder]** 要设置的用户档案。
1. A **[!UICONTROL Loading]** 当从Insight配置文件中检索架构时，将显示消息。 加载架构的时间长短取决于加载的用户档案的复杂程度。
1. 完成后，您将看到 **[!UICONTROL Insight Schema]** 的 **[!UICONTROL Dashboard Schema]** 中。 此摘要将显示在 **[!UICONTROL Schema Builder]** 窗口。

   >[!NOTE]
   >
   >首次设置架构时，每个量度、维度和过滤器将与功能板的架构以不同的方式列出。 这是因为功能板架构对象当前不存在。

   ![](assets/schema_builder2.png)

1. 单击 **[!UICONTROL Synchronize with Schema]** 按钮，以将“分析架构”视图中的所有量度、维度和过滤器与“功能板架构”视图同步。
1. 完成后，您应会看到一条消息，指示未找到任何差异：

   ![](assets/diff_found.png)

1. 如果功能板架构存在任何错误（如重复的量度和维度），则必须先手动更正它们，然后才能保存。

   >[!NOTE]
   >
   >您可以从 **[!UICONTROL Dashboard Schema]** 功能板的最终用户。 您将收到一则警告，指出功能板架构中不存在项目，但不会阻止您进行保存。

1. 准备就绪后，单击 **[!UICONTROL Save]** 以保存对功能板架构所做的更改。
1. 功能板系统将使用此架构定义来填充功能板界面最终用户可用的维度、量度和过滤器。
