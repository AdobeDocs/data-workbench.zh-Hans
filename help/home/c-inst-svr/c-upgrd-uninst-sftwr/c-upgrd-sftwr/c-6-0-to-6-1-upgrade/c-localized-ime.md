---
description: Data Workbench 现在支持使用输入法编辑器 (IME) 作为国际语言的辅助文本输入程序。
title: 安装输入法编辑器
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 79%

---

# 安装输入法编辑器{#installing-the-input-method-editor}

{{eol}}

Data Workbench 现在支持使用输入法编辑器 (IME) 作为国际语言的辅助文本输入程序。

通过 IME，可以使用各种适合您本地语言的方法输入国际字符。Data Workbench 提供了一个输入对话框，允许您打开所需的 IME 并将其用于文本字段。

>[!NOTE]
>
>对于Data Workbench 6.1版本，将仅支持虚拟简体中文键盘。 通过 IME 输入其他语言可能导致异常行为。

## 使用 IME {#section-5f008d75a7b24119ab6aebc55454f927}

要使用浮动的 IME 文本输入功能，请执行以下操作：

1. 单击 **[!UICONTROL Alt + Space]** ，用于任何文本输入区域。
1. 使用系统的 IME 输入值。
1. 通过选择 **[!UICONTROL Enter]** 键或单击 **[!UICONTROL OK]** 按钮。

   对话框将消失，随后字符将出现在所选字段中。

**更新 Insight.cfg 文件**

要使用 IME，必须用以下设置更新 [!DNL Insight.cfg] 文件：

```
Localized IME = bool: true
```

如果配置文件中不存在此设置，则按 **[!UICONTROL Alt + Space]** 将不使用IME功能。

**启动其他语言版本的 Insight：**&#x200B;为更好地支持本地化的资产（如启动屏幕）并在未来支持多种语言，Data Workbench 需要命令行参数来识别要加载的语言。默认语言是英语。

要启动中文版的 Data Workbench，需要使用“-zh-cn”参数调用 [!DNL Insight.exe]：

```
Insight.exe -zh-cn
```

（这些命令行参数不区分大小写。）
