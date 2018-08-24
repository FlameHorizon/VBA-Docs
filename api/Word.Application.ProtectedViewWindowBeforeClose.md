---
title: Application.ProtectedViewWindowBeforeClose Event (Word)
keywords: vbawd10.chm4000033
f1_keywords:
- vbawd10.chm4000033
ms.prod: word
api_name:
- Word.Application.ProtectedViewWindowBeforeClose
ms.assetid: 4557dd3d-b795-94d9-ee53-5e83dcdd03d0
ms.date: 06/08/2017
---


# Application.ProtectedViewWindowBeforeClose Event (Word)

Occurs immediately before a protected view window or a document in a protected view window closes.


## Syntax

 _expression_. `ProtectedViewWindowBeforeClose`( `_PvWindow_` , `_CloseReason_` , `_Cancel_` )

 _expression_ An expression that returns an '[Application](Word.Application.md)' object.


### Parameters



|**Name**|**Required/Optional**|**Data Type**|**Description**|
|:-----|:-----|:-----|:-----|
| _PvWindow_|Required| **ProtectedViewWindow**|The protected view window that is closed.|
| _CloseReason_|Required| **[INT]**|A constant in the [WdProtectedViewCloseReason](Word.WdProtectedViewCloseReason.md) enumeration that specifies the reason the protected view window is closed.|
| _Cancel_|Required| **Boolean**| **False** when the event occurs. If the event procedure sets this argument to **True** , the window does not close when the procedure is finished.
 **Note**  If the  **ProtectedViewWindowsBeforeClose** event is called as part of the[ProtectedView.Edit](Word.ProtectedViewWindow.Edit.md) method, setting _Cancel_ to **True** produces no action.

|

## Example

The following code example prompts the user for a yes or no response before closing any document. This code must be placed in a class module, and an instance of the class must be correctly initialized to see this example work. For more information about how to do this, see [Using Events with the Application Object](../word/Concepts/Objects-Properties-Methods/using-events-with-the-application-object-word.md).

The following code example assumes that you have declared an application variable called "App" in your general declarations and have set the variable equal to the Word Application object.




```vb
Private Sub App_ProtectedViewWindowBeforeClose(ByVal PvWindow As ProtectedViewWindow, ByVal CloseReason As Long, Cancel As Boolean) 
Dim intResponse As Integer 
 
    intResponse = MsgBox("Do you really " _ 
        & "want to close the document?", _ 
        vbYesNo) 
 
    If intResponse = vbNo Then Cancel = True 
 
End Sub
```


## See also


[Application Object](Word.Application.md)
