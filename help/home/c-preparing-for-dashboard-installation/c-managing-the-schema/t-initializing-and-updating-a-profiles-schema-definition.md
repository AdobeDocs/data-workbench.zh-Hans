---
description: 'null'
solution: Analytics
title: 初始化和更新配置文件的架构定义
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 初始化和更新配置文件的架构定义{#initializing-and-updating-a-profile-s-schema-definition}

1. 打开 **[!UICONTROL Schema Builder]** 要设置的配置文件。
1. 从 **[!UICONTROL Loading]** Insight配置文件检索架构时，将显示一条消息。 加载架构的时间长度取决于加载的配置文件的复杂性。
1. 完成后，您将在左侧窗格中看到 **[!UICONTROL Insight Schema]** 与右侧窗格之间差异 **[!UICONTROL Dashboard Schema]** 的摘要。 此摘要将显示在窗口的左下部 **[!UICONTROL Schema Builder]** 分。

   >[!NOTE]
   >
   >首次设置架构时，每个度量、维和筛选器的列表将与功能板的架构不同。 这是因为功能板架构对象目前不存在。

   ![](assets/schema_builder2.png)

1. 单击该按 **[!UICONTROL Synchronize with Schema]** 钮，以将“分析架构”视图中的所有度量、维度和筛选器与“功能板架构”视图同步。
1. 完成后，您应当看到一条消息，指示未找到任何差异：

   ![](assets/diff_found.png)

1. 如果功能板架构有任何错误（如重复的度量和维度），则必须先手动更正它们，然后才能保存。

   >[!NOTE]
   >
   >您可以选择性地从您不希望显示给功能板 **[!UICONTROL Dashboard Schema]** 最终用户的任何指标、维度或过滤器中删除。 您将收到一条警告，指出功能板架构中不存在项目，但不会阻止您保存这些项目。

1. 准备就绪后，单 **[!UICONTROL Save]** 击以保存对功能板架构所做的更改。
1. 功能板系统将使用此架构定义填充功能板界面的最终用户可用的维度、度量和筛选器。
