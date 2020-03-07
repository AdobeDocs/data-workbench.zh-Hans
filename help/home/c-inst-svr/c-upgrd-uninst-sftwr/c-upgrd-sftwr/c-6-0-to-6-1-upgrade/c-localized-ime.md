---
description: Data Workbench 现在支持使用输入法编辑器 (IME) 作为国际语言的辅助文本输入程序。
solution: Analytics
title: 安装输入法编辑器
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# 安装输入法编辑器{#installing-the-input-method-editor}

Data Workbench 现在支持使用输入法编辑器 (IME) 作为国际语言的辅助文本输入程序。

通过 IME，可以使用各种适合您本地语言的方法输入国际字符。Data Workbench 提供了一个输入对话框，允许您打开所需的 IME 并将其用于文本字段。

>[!NOTE]
>
>对于Data Workbench 6.1版本，仅支持虚拟简体中文键盘。 通过 IME 输入其他语言可能导致异常行为。

## 使用 IME {#section-5f008d75a7b24119ab6aebc55454f927}

要使用浮动的 IME 文本输入功能，请执行以下操作：

1. 单击 **[!UICONTROL Alt + Space]** 可输入任何文本区域。
1. 使用系统的 IME 输入值。
1. Close the input dialog by selecting the **[!UICONTROL Enter]** key or clicking the **[!UICONTROL OK]** button.

   对话框将消失，随后字符将出现在所选字段中。

**更新 Insight.cfg 文件**

要使用 IME，必须用以下设置更新 [!DNL Insight.cfg] 文件：

```
Localized IME = bool: true
```

If this setting does not exist in the configuration file, then pressing **[!UICONTROL Alt + Space]** will not engage the IME feature.

**启动其他语言版本的 Insight：**&#x200B;为更好地支持本地化的资产（如启动屏幕）并在未来支持多种语言，Data Workbench 需要命令行参数来识别要加载的语言。默认语言是英语。

要启动中文版的 Data Workbench，需要使用“-zh-cn”参数调用 [!DNL Insight.exe]：

```
Insight.exe -zh-cn
```

（这些命令行参数不区分大小写。）
