---
title: "使用 Serviced 元件和全域組件快取"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: 8
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 493ca9a2da4a06528eab9b87db78a5b7a49a2f1d
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# 使用 Serviced 元件和全域組件快取
Serviced 元件 \(Managed 程式碼 COM\+ 元件\) 應放入全域組件快取。  在某些案例中，Common Language Runtime 和 COM\+ 服務可以處理不在全域組件快取中的 Serviced 元件；但在某些案例中則不行。  下列案例便可說明：  
  
-   如果是 COM\+ 伺服器應用程式中的服務元件，含有元件的組件必須在全域組件快取中，因為 Dllhost.exe 執行的目錄與含有 Serviced 元件的目錄並不相同。  
  
-   如果是 COM\+ 程式庫應用程式的 Serviced 元件，Runtime 和 COM\+ 服務可搜尋目前目錄，以便解析對含有元件的組件參考。  在這種情況下，組件並非一定要位於全域組件快取中。  
  
-   如果是 ASP.NET 應用程式的 Serviced 元件，情況則有所不同。  如果您將含有 Serviced 元件的組件放到應用程式基底的 Bin 目錄中，並且使用需求的註冊，則組件將陰影複製至下載快取中，因為 ASP.NET 會使用執行階段的陰影複製功能。  
  
## 請參閱  
 [How to: Create a Serviced Component](http://msdn.microsoft.com/zh-tw/7ec0b488-e5fc-46f2-a48d-1278ea4e301d)   
 [使用組件和全域組件快取](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe (全域組件快取工具)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)

