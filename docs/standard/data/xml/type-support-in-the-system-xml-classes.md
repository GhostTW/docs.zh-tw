---
title: "System.Xml 類別中的型別支援 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 63570538-06e3-4401-ad4d-ac50be90c7bf
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# System.Xml 類別中的型別支援
在 .NET Framework 2.0 版中，核心 XML 類別已增強為包括類型支援功能。  <xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 及 <xref:System.Xml.XPath.XPathNavigator> 類別包含類型支援功能，包括在 XML 結構描述類型與 Common Language Runtime \(CLR\) 類型之間轉換的能力。  
  
 在 .NET Framework 2.0 版中，<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 及 <xref:System.Xml.XPath.XPathNavigator> 類別已增強為包括類型支援功能。  
  
-   每個 <xref:System.Xml.XmlReader> 及 <xref:System.Xml.XPath.XPathNavigator> 類別都包含 **SchemaInfo** 屬性，可傳回節點的結構描述資訊。  
  
-   **ReadContentAs**、**ReadElementContentAs** 及 <xref:System.Xml.XmlReader> 類別上的方法，會在單一方法呼叫中讀取文字值，並將其轉換成 CLR 值。  
  
-   <xref:System.Xml.XmlWriter> 類別上的 <xref:System.Xml.XmlWriter.WriteValue%2A> 方法會在寫出 XML 時，將 CLR 類型轉換成 XML 結構描述類型。  
  
-   <xref:System.Xml.XPath.XPathNavigator> 類別上的 **ValueAs** 及 <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> 屬性會在單一方法呼叫中傳回節點值，並將其轉換成 CLR 值。  
  
> [!NOTE]
>  在 .NET Framework 1.0 版中，需要 <xref:System.Xml.XmlConvert> 類別以在 XML 結構描述與 CLR 類型之間進行轉換。  
  
## 在本節中  
 [將 XML 資料型別對應至 CLR 型別](../../../../docs/standard/data/xml/mapping-xml-data-types-to-clr-types.md)  
 說明 XML 資料類型與 CLR 類型的預設對應。  
  
 [XML 型別支援實作注意事項](../../../../docs/standard/data/xml/xml-type-support-implementation-notes.md)  
 討論部分類型支援實作細節。  
  
 [XML 資料型別轉換](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 說明如何使用 <xref:System.Xml.XmlConvert> 類別在 XML 結構描述與 CLR 類型之間進行轉換。  
  
## 相關章節  
 [使用 XPathNavigator 存取強型別 XML 資料](../../../../docs/standard/data/xml/accessing-strongly-typed-xml-data-using-xpathnavigator.md)