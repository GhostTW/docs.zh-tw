---
title: "HOW TO：若要以受限的保留項目取代 WCF URL URL 保留項目 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2754d223-79fc-4e2b-a6ce-989889f2abfa
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# HOW TO：若要以受限的保留項目取代 WCF URL URL 保留項目
URL 保留項目可讓您限制誰可以接收來自某個 URL 或一組 URL 的訊息。保留項目是由一個 URL 範本、一個存取控制清單 \(ACL\)，以及一組旗標所組成。URL 範本會定義保留項目所影響的 URL。[!INCLUDE[crabout](../../../../includes/crabout-md.md)]如何處理 URL 範本的詳細資訊，請參閱[路由傳入的要求](http://go.microsoft.com/fwlink/?LinkId=136764)。ACL 會控制允許從指定之 URL 接收訊息的使用者或使用者群組。旗標會指出保留項目是要提供使用者或群組直接在 URL 上接聽的權限，還是要委派接聽其他特定處理序的權限。  
  
 As part of the default operating system configuration, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 會針對通訊埠 80 建立可全域存取的保留項目，讓所有使用者執行使用雙重 HTTP 繫結進行雙工通訊的應用程式。此保留項目的 ACL 是攻所有人使用，因此，系統管理員無法明確地允許或不允許在一個 URL 或一組 URL 上接聽的權限。本主題說明如何刪除此保留項目，以及如何使用受限的 ACL 重新建立保留項目。  
  
 在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 或 [!INCLUDE[lserver](../../../../includes/lserver-md.md)] 上，您可以從更高權限的命令提示字元輸入 `netsh http show urlacl`，以檢視所有 HTTP URL 保留項目。下列範例顯示應該類似的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 保留項目。  
  
```  
Reserved URL : http://+:80/Temporary_Listen_Addresses/  
        User: \Everyone  
            Listen: Yes  
            Delegate: No  
            SDDL: D:(A;;GX;;;WD)  
```  
  
 保留項目是由 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 應用程式使用 HTTP 雙重繫結進行雙工通訊時所使用的 URL 範本所組成。透過 HTTP 雙重繫結進行通訊時，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服務會使用這種形式的 URL，將訊息傳回 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 用戶端。所有人都會得到在 URL 上接聽的權限，但沒有委派接聽其他處理序的權限。最後，ACL 會以 Security Descriptor Definition Language \(SSDL\) 描述。[!INCLUDE[crabout](../../../../includes/crabout-md.md)] SSDL 的詳細資訊，請參閱 [SSDL](http://go.microsoft.com/fwlink/?LinkId=136789) \(英文\)  
  
### 若要刪除 WCF URL 保留項目  
  
1.  按一下 \[**開始**\]、指向 \[**所有程式**\]、按一下 \[**附屬應用程式**\]、以滑鼠右鍵按一下 \[**命令提示字元**\]，然後在出現的內容功能表上，按一下 \[**以系統管理員身分執行**\]。在可能會要求權限的 \[使用者帳戶控制 \(UAC\)\] 視窗中按一下 \[**繼續**\] 以繼續。  
  
2.  在 \[命令提示字元\] 視窗中，輸入 **netsh http delete urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/**。  
  
3.  如果成功刪除保留項目，就會顯示下列訊息。**URL reservation successfully deleted**  
  
## 建立新的安全性群組與新的受限 URL 保留項目  
 若要以受限的保留項目取代 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URL 保留項目，您必須先建立一個新的安全性群組。您可以從命令提示字元或電腦管理主控台執行這個動作。您只需要選擇其中一種方式。  
  
#### 若要從命令提示字元建立新的安全性群組  
  
1.  按一下 \[**開始**\]、指向 \[**所有程式**\]、按一下 \[**附屬應用程式**\]、以滑鼠右鍵按一下 \[**命令提示字元**\]，然後在出現的內容功能表上，按一下 \[**以系統管理員身分執行**\]。在可能會要求權限的 \[使用者帳戶控制 \(UAC\)\] 視窗中按一下 \[**繼續**\] 以繼續。  
  
2.  在命令提示字元中輸入 **net localgroup "\<security group name\>" \/comment:"\<security group description\>" \/add**。將 **\<security group name\>** 取代成您要建立之安全性群組的名稱，並將 **\<security group description\>** 取代成適合安全性群組的描述。  
  
3.  如果成功建立安全性群組，就會顯示下列訊息。**The command completed successfully.**  
  
#### 若要從電腦管理主控台建立新的安全性群組  
  
1.  依序按一下 \[**開始**\]、\[**控制台**\]、\[**系統管理工具**\] 和 \[**電腦管理**\] 以開啟電腦管理主控台。在可能會要求權限的 \[使用者帳戶控制 \(UAC\)\] 視窗中按一下 \[**繼續**\] 以繼續。  
  
2.  依序按一下 \[**系統工具**\] 和 \[**本機使用者和群組**\]，以滑鼠右鍵按一下 \[**群組**\] 資料夾，然後在出現的內容功能表上按一下 \[**新增群組**\]。輸入所需的 \[**群組名稱**\]、\[**描述**\] 以及這個新安全性群組的其他詳細資料，然後按一下 \[**建立**\] 按鈕來建立安全性群組。  
  
#### 若要建立受限的 URL 保留項目  
  
1.  按一下 \[**開始**\]、指向 \[**所有程式**\]、按一下 \[**附屬應用程式**\]、以滑鼠右鍵按一下 \[**命令提示字元**\]，然後在出現的內容功能表上，按一下 \[**以系統管理員身分執行**\]。在可能會要求權限的 \[使用者帳戶控制 \(UAC\)\] 視窗中按一下 \[**繼續**\] 以繼續。  
  
2.  在命令提示字元中輸入 **netsh http add urlacl url\=http:\/\/\+:80\/Temporary\_Listen\_Addresses\/ user\="\<machine name\>\\\<security group name\>**。將 **\<machine name\>** 取代成必須在其上建立群組的電腦名稱，並將 **\<security group name\>** 取代成您先前建立之安全性群組的名稱。  
  
3.  如果成功建立保留項目，就會顯示下列訊息。**URL reservation successfully added**.