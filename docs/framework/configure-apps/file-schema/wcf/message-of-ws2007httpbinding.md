---
title: "&lt;ws2007HttpBinding&gt; 的 &lt;message&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9ffd8db6-84a8-4b38-a9fe-2cb1a87a1c97
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;ws2007HttpBinding&gt; 的 &lt;message&gt;
定義 [\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) 項目的訊息層級安全性設定。  
  
## 語法  
  
```  
  
<ws2007HttpBinding>  
 <binding >  
  <security>  
   <message clientCredentialType =  
    "None/Windows/UserName/Certificate/IssuedToken"  
    establishSecurityContext="Boolean"  
    negotiateServiceCredential="Boolean"  
    algorithmSuite= Enumeration. See algorithmSuite Attribute below.  
    defaultProtectionLevel="None/Sign/EncryptionAndSign" />  
  </security>  
 </binding>  
</ws2007HttpBinding>  
```  
  
## 類型  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>  
  
## 屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### 屬性  
  
|屬性|描述|  
|--------|--------|  
|`algorithmSuite`|設定訊息加密和金鑰包裝演算法。  這些演算法和金鑰大小是由 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 類別所決定。  這些演算法會對應至安全性原則語言 \(WS\-SecurityPolicy\) 規格中指定的演算法。<br /><br /> 預設值為 Basic256。|  
|`clientCredentialType`|選擇項。  指定使用的安全性模式為 `Message` 或 `TransportWithMessageCredentials` 執行用戶端驗證時，要使用的認證類型。  請參閱下表的列舉數值。  預設為 Windows。<br /><br /> 此屬性的型別為 <xref:System.ServiceModel.MessageCredentialType>。|  
|`establishSecurityContext`|數值，這個數值會決定安全性通道是否建立安全工作階段。  安全工作階段會先建立安全性內容權杖 \(SCT\)，再交換應用程式訊息。  建立 SCT 後，安全性通道會提供 <xref:System.ServiceModel.Channels.ISession> 介面給上層通道。  如需使用安全工作階段的詳細資訊，請參閱 [HOW TO：建立安全工作階段](../../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)。<br /><br /> 預設值是 `true`。|  
|`negotiateServiceCredential`|選擇項。  數值，這個數值會指定是否在超出範圍的用戶端佈建服務認證，或透過交涉處理取得從服務到用戶端的服務認證。  此類交涉是一般訊息交換的前兆。<br /><br /> 如果 `clientCredentialType` 屬性等於 None、Username 或 Certificate，則將這個屬性設定為 `false` 意指服務憑證可在超出範圍的用戶端使用，且用戶端必須指定 [\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)服務行為中的服務憑證 \(使用 [\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\)。  這個模式可與實作 WS\-Trust 和 WS\-SecureConversation 的 SOAP 堆疊互通。<br /><br /> 如果 `ClientCredentialType` 屬性設定為 `Windows`，則將這個屬性設定為 `false` 可指定 Kerberos 驗證。  這表示用戶端和服務必須屬於同一個 Kerberos 網域。  這個模式可與實作 Kerberos 語彙基元設定檔 \(如在 OASIS WSS TC 所定義\) 以及 WS\-Trust 和 WS\-SecureConversation 的 SOAP 堆疊互通。<br /><br /> 當這個屬性是 `true` 時，會造成透過 SOAP 訊息以通道連接 <xref:System.ServiceModel.Security.Tokens.ServiceModelSecurityTokenTypes.Spnego%2A> 交換的 .NET SOAP 交涉。<br /><br /> 預設為 `true`。|  
  
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
|`None`|這會允許服務與匿名用戶端互動。  在服務上，這表示此服務不需要任何用戶端認證。  在用戶端上，這表示此用戶端不提供任何用戶端認證。|  
|`Certificate`|允許服務要求用戶端使用憑證進行驗證。  如果使用 `message` 安全性模式且 `negotiateServiceCredential` 屬性設定為 `false`，則必須為用戶端佈建服務憑證。|  
|`IssuedToken`|指定通常由安全性權杖服務 \(STS\) 所發出的自訂權杖。|  
|`UserName`|允許服務要求用戶端使用 `UserName` 認證進行驗證。  [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 不支援傳送密碼摘要，或是使用密碼衍生金鑰，甚至對訊息安全性使用該金鑰。  這麼一來，[!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 會在使用 `UserName` 認證時強制保護傳輸。  這個認證模式會產生可互通交換或是無法互通的交涉 \(根據 `negotiateServiceCredential` 屬性\)。|  
|`Windows`|允許 SOAP 交換在 `Windows` 認證的已驗證內容中。  如果 `negotiateServiceCredential` 屬性設定為 `true`，這會執行 SSPI 交涉或 Kerberos \(互通標準\)。|  
  
### 子項目  
 無  
  
### 父項目  
  
|項目|描述|  
|--------|--------|  
|[\<安全性\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|定義 [\<ws2007HttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)的安全性設定。|  
  
## 請參閱  
 <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>   
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.WSHttpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.NonDualMessageSecurityOverHttpElement>   
 [確保服務與用戶端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [繫結](../../../../../docs/framework/wcf/bindings.md)   
 [設定系統提供的繫結](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/zh-tw/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<繫結\>](../../../../../docs/framework/misc/binding.md)