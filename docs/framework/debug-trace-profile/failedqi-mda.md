---
title: failedQI MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- failed QueryInterface
- FailedQI MDA
- QueryInterface call failures
- MDAs (managed debugging assistants), failed QueryInterface
- managed debugging assistants (MDAs), failed QueryInterface
ms.assetid: 902dc863-34b3-477c-b433-b8a6bb6133c6
caps.latest.revision: 15
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 313676abe0732fcd4f3285c5c1f935302695d3cc
ms.contentlocale: zh-tw
ms.lasthandoff: 08/21/2017

---
# <a name="failedqi-mda"></a>failedQI MDA
當執行階段代表執行階段可呼叫包裝函式 (RCW)，在 COM 介面指標上呼叫 `QueryInterface`，而 `QueryInterface` 呼叫失敗時，就會啟動 `failedQI` Managed 偵錯助理 (MDA)。  
  
## <a name="symptoms"></a>徵兆   
 在 RCW 上轉換失敗，或從 RCW 呼叫 COM 時意外失敗。  
  
## <a name="cause"></a>原因  
  
-   從錯誤的內容進行呼叫。  
  
-   所註冊的 Proxy 導致 `QueryInterface` 呼叫失敗，因為是嘗試在錯誤的內容中呼叫。  
  
-   OLE 擁有的 Proxy 傳回失敗 HRESULT。  
  
## <a name="resolution"></a>解決方式  
 請參閱有關 COM 規則的 MSDN 文件。  
  
## <a name="effect-on-the-runtime"></a>對執行階段的影響  
 如果 `QueryInterface` 呼叫失敗，內容就會切換，然後重新嘗試 `QueryInterface` 呼叫，以查看是否有不正確的內容出錯。  
  
## <a name="output"></a>輸出  
 介面的 Managed 名稱、介面的 GUID，以及失敗的 HRESULT。  
  
## <a name="configuration"></a>組態  
  
```xml  
<mdaConfig>  
  <assistants>  
    <failedQI/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [使用 Managed 偵錯助理診斷錯誤](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop 封送處理](../../../docs/framework/interop/interop-marshaling.md)

