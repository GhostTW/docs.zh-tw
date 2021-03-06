---
title: "#<a name=\"define-c-reference\"></a>define (C# 參考)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#define'
dev_langs:
- CSharp
helpviewer_keywords:
- '#define directive [C#]'
ms.assetid: 23638b8f-779c-450e-b600-d55682de7d01
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8ace15f79480c9aeb0fcb4c7d46c207d4904cef0
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# #define (C# 參考)
您可以使用 `#define` 來定義符號。  當您以符號當做運算式傳遞至 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 指示詞時，這個運算式將評估為 `true`，如下列範例所示：  
  
 `#`  `define`   `DEBUG`  
  
## 備註  
  
> [!NOTE]
>  `#define` 指示詞無法用來宣告一般在 C 和 C\+\+ 中執行的常數值。  C\# 中的常數最好定義為 class 或 struct 的靜態成員。  如果擁有多個此類常數，請考慮建立個別的 "Constants" 類別來保存這些常數。  
  
 符號可以用來指定編譯條件。  您可以使用 [\#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md) 或 [\#elif](../../../csharp/language-reference/preprocessor-directives/preprocessor-elif.md) 測試符號。  您也可以使用 `conditional` 屬性來執行條件式編譯。  
  
 您可以定義符號，但是不能指定值給符號。  `#define` 指示詞必須已出現在檔案中，然後才能使用任何非同時為前置處理器指示詞的指令。  
  
 您也可以使用 [\/define](../../../csharp/language-reference/compiler-options/define-compiler-option.md) 編譯器選項定義符號。  使用 [\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md) 取消符號定義。  
  
 使用 `/define` 或 `#define` 定義的符號並不會和具相同名稱的變數發生衝突。  這是因為變數名稱並不會傳遞至前置處理器指示詞，而符號只能由前置處理器指示詞進行評估。  
  
 使用 `#define` 建立的符號範圍是定義此符號的檔案。  
  
 如下列範例所示，您必須將 `#define` 指示詞放在檔案的頂端。  
  
```c#  
#define DEBUG  
//#define TRACE  
#undef TRACE  
  
using System;  
  
public class TestDefine  
{  
    static void Main()  
    {  
#if (DEBUG)  
        Console.WriteLine("Debugging is enabled.");  
#endif  
  
#if (TRACE)  
     Console.WriteLine("Tracing is enabled.");  
#endif  
    }  
}  
// Output:  
// Debugging is enabled.  
```  
  
 如需有關定義符號的範例，請參閱[\#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)。  
  
## 請參閱  
 [C\# 參考](../../../csharp/language-reference/index.md)   
 [C\# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [C\# 前置處理器指示詞](../../../csharp/language-reference/preprocessor-directives/index.md)   
 [const](../../../csharp/language-reference/keywords/const.md)   
 [如何：使用追蹤和偵錯進行條件式編譯](../../../framework/debug-trace-profile/how-to-compile-conditionally-with-trace-and-debug.md)   
 [#undef](../../../csharp/language-reference/preprocessor-directives/preprocessor-undef.md)   
 [#if](../../../csharp/language-reference/preprocessor-directives/preprocessor-if.md)

