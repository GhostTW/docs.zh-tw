---
title: "&lt;ws2007FederationHttpBinding&gt; 的 &lt;message&gt; 項目 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 52cd941d-e230-4c82-8b29-333a7d20eca8
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;ws2007FederationHttpBinding&gt; 的 &lt;message&gt; 項目
定義 [\<ws2007FederationHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) 項目的訊息層級安全性設定。  
  
## 語法  
  
```  
  
<ws2007FederationBinding>  
   <binding >  
      <security>  
         <message   
            algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            issuedTokenType="string"   
            issuedKeyType="SymmetricKey/PublicKey"  
            negotiateServiceCredential="Boolean" >  
            <claimTypeRequirements>  
               <add claimType="URI"  
                    isOptional="Boolean" />  
            </claimTypeRequirements>  
            <issuer address="Uri" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     x509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
            </issuer>  
            <issuerMetadata address=String" >  
               <headers>  
                  <add name="String"  
                       namespace="String" />  
               </headers>  
               <identity>  
                  <certificate encodedValue="String"/>  
                  <certificateReference findValue="String"   
                     isChainIncluded="Boolean"  
                     storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
                     storeLocation="LocalMachine/CurrentUser"  
                     X509FindType=System.Security.Cryptography.X509certificates.X509findtype/>  
                  <dns value="String"/>  
                  <rsa value="String"/>  
                  <servicePrincipalName value="String"/>  
                  <usePrincipalName value="String"/>  
               </identity>  
            </issuerMetadata>  
            <tokenRequestParameters>  
               <xmlElement>  
               </xmlElement>  
            </tokenRequestParameters>  
         </message>  
      </security>  
   </binding>  
</ws2007FederationBinding>  
```  
  
## 屬性和項目  
 下列章節說明屬性、子項目和父項目。  
  
### 屬性  
  
|屬性|描述|  
|--------|--------|  
|`algorithmSuite`|選擇項。  設定訊息加密、簽章和金鑰包裝演算法。  這些演算法和金鑰大小是由 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 類別所決定。  這些演算法會對應至安全性原則語言 \(WS\-SecurityPolicy\) 規格中指定的演算法。<br /><br /> 請參閱下表列出的可能值。  預設值為 Basic256。|  
|`issuedKeyType`|指定要發行的金鑰類型。  有效值包括以下的值：<br /><br /> -   SymmetricKey<br />-   PublicKey<br />-   BearerKey<br /><br /> 預設為 SymmetricKey。  此屬性的型別為 <xref:System.IdentityModel.Tokens.SecurityKeyType>。|  
|`issuedTokenType`|URI，指定要發行的權杖型別。  預設為 `null`。|  
|`negotiateServiceCredential`|這個值會指定服務認證是否應交換做為交涉的一部分，或可供超出範圍使用。  預設為 `true`，意指交涉服務認證。|  
  
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
  
### 子項目  
  
|項目|描述|  
|--------|--------|  
|[\<claimTypeRequirements\>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|指定這個繫結之宣告型別的集合。  每個項目的型別為 <xref:System.ServiceModel.Configuration.ClaimTypeElement>。|  
|[\<issuer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|指定發行安全性權杖的端點。  此項目的型別為 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>。|  
|[\<issuerMetadata\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|指定簽發者的端點位址。|  
|[\<tokenRequestParameters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|權杖要求參數的集合。  每個參數都是 XML 項目。|  
  
### 父項目  
  
|項目|描述|  
|--------|--------|  
|[\<安全性\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)|定義繫結的安全性設定。|  
  
## 請參閱  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp>   
 <xref:System.ServiceModel.Configuration.WSFederationHttpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.WSFederationHttpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityElement>   
 [確保服務與用戶端的安全](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [繫結](../../../../../docs/framework/wcf/bindings.md)   
 [設定系統提供的繫結](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/zh-tw/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<繫結\>](../../../../../docs/framework/misc/binding.md)