---
title: "&lt;netTcpBinding&gt; 的 &lt;message&gt; 項目 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d71edd9-c085-4c2e-b6d3-980c313366f9
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# &lt;netTcpBinding&gt; 的 &lt;message&gt; 項目
定義以 [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) 設定之端點的訊息層級安全性需求的類型。  
  
## 語法  
  
```  
  
<message   
      algorithmSuite=System.Servicemodel.Security.SecurityAlgorithmsuite  
    clientCredentialType="None/Windows/UserName/Certificate/IssuedToken"/>  
```  
  
## 屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### 屬性  
  
|屬性|描述|  
|--------|--------|  
|`algorithmSuite`|設定訊息加密和金鑰包裝演算法。  這些演算法和金鑰大小是由 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 類別所決定。  這些演算法會對應至安全性原則語言 \(WS\-SecurityPolicy\) 規格中指定的演算法。<br /><br /> 下表列出可能的值。  預設值是 `Basic256`。<br /><br /> 如果服務繫結指定的 `algorithmSuite` 值不等於預設值，且您是使用 Svcutil.exe 產生組態檔，則該檔案將無法正確產生，這時您就必須手動編輯組態檔，將此屬性設定為需要的值。|  
|`clientCredentialType`|指定當使用訊息安全性執行用戶端驗證時，要使用的認證類型。  下表列出可能的值。  預設值是 `UserName`。  此屬性的型別為 <xref:System.ServiceModel.MessageCredentialType>。|  
  
## algorithmSuite 屬性  
  
|值|描述|  
|-------|--------|  
|Basic128|使用 Aes128 加密，Sha1 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic192|使用 Aes192 加密，Sha1 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic256|使用 Aes256 加密，Sha1 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic256Rsa15|將 Aes256 用於訊息加密，Sha1 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|Basic192Rsa15|將 Aes192 用於訊息加密，Sha1 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|TripleDes|使用 TripleDes 加密，Sha1 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic128Rsa15|將 Aes128 用於訊息加密，Sha1 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|TripleDesRsa15|使用 TripleDes 加密，Sha1 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|Basic128Sha256|將 Aes256 用於訊息加密，Sha256 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic192Sha256|將 Aes192 用於訊息加密，Sha256 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic256Sha256|將 Aes256 用於訊息加密，Sha256 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|TripleDesSha256|將 TripleDes 用於訊息加密，Sha256 用於訊息摘要，Rsa\-oaep\-mgf1p 用於金鑰包裝。|  
|Basic128Sha256Rsa15|將 Aes128 用於訊息加密，Sha256 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|Basic192Sha256Rsa15|將 Aes192 用於訊息加密，Sha256 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|Basic256Sha256Rsa15|將 Aes256 用於訊息加密，Sha256 用於訊息摘要，Rsa15 用於金鑰包裝。|  
|TripleDesSha256Rsa15|將 TripleDes 用於訊息加密，Sha256 用於訊息摘要，Rsa15 用於金鑰包裝。|  
  
## clientCredentialType 屬性  
  
|值|描述|  
|-------|--------|  
|無|這會允許服務與匿名用戶端互動。  在服務上，這表示此服務不需要任何用戶端認證。  在用戶端上，這表示此用戶端不提供任何用戶端認證。|  
|Windows|允許 SOAP 交換在 Windows 認證的已驗證內容中。|  
|UserName|允許服務要求用戶端必須使用 UserName 認證進行驗證。  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 不支援傳送密碼摘要，或是使用密碼衍生金鑰，甚至對訊息安全性使用該金鑰。  這麼一來，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 會在使用 UserName 認證時強制保護傳輸。  這個認證模式會產生可互通交換或是無法互通的交涉 \(根據 `negotiateServiceCredential` 屬性\)。|  
|憑證|允許服務要求用戶端使用憑證進行驗證。  如果使用訊息安全性模式且 `negotiateServiceCredential` 屬性設定為 `false`，則必須為用戶端提供服務憑證。|  
|IssuedToken|指定通常由安全性權杖服務 \(STS\) 所發出的自訂權杖。|  
  
### 子項目  
 無  
  
### 父項目  
  
|項目|描述|  
|--------|--------|  
|[\<安全性\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|定義 <xref:System.ServiceModel.Configuration.NetTcpBindingElement> 的安全性功能。|  
  
## 備註  
 訊息會使用訊息層級安全性達成 SOAP 訊息的完整性與機密性，以及通訊對等兩端的交互驗證。  如果繫結上選取了這個安全性模式，通道堆疊會以訊息安全性繫結項目進行設定，且 SOAP 訊息的安全性會符合 WS\-Security\* 標準。  
  
## 請參閱  
 <xref:System.ServiceModel.MessageSecurityOverTcp>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetTcpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement>   
 [確保服務與用戶端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [繫結](../../../../../docs/framework/wcf/bindings.md)   
 [設定系統提供的繫結](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/zh-tw/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<繫結\>](../../../../../docs/framework/misc/binding.md)