---
title: "How to: Handle Exceptions in Parallel Loops | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "parallel loops, how to handle exceptions"
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Handle Exceptions in Parallel Loops
<xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> 和 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> 多載沒有任何特殊機制可用來處理可能擲回的例外狀況。  它們在這一方面類似於一般 `for` 和 `foreach` 迴圈 \(在 Visual Basic 中為 `For` 和 `For Each`\)；未處理的例外狀況會導致此迴圈立即終止。  
  
 當您將自己的例外狀況處理邏輯加入平行迴圈時，請處理多個執行緒上可能同時擲回類似例外狀況的情況，以及某個執行緒上擲回的例外狀況導致在另一個執行緒上擲回另一個例外狀況的情況。  您可以來自此迴圈的所有例外狀況包裝在 <xref:System.AggregateException?displayProperty=fullName> 中，同時處理這兩種情況。  下列範例會示範一種可能的方式。  
  
> [!NOTE]
>  啟用 \[Just My Code\] 時，Visual Studio 在某些情況下會在擲回例外狀況的字行上中斷，並顯示錯誤訊息，指出「使用者程式碼未處理例外狀況」。 這個錯誤是良性的。  您可以按 F5 從中斷的地方繼續，並查看下面範例中示範的例外處理行為。  若要防止 Visual Studio 在遇到第一個錯誤時就中斷，只要取消核取 \[工具\]、\[選項\]、\[偵錯\]、\[一般\] 下的 \[Just My Code\] 核取方塊即可。  
  
## 範例  
 在此範例中，會攔截所有例外狀況，然後包裝於擲回的 <xref:System.AggregateException?displayProperty=fullName> 之中。  呼叫端可決定要處理哪一個例外狀況。  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## 請參閱  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)