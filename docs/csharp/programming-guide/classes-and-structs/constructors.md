---
title: "建構函式 (C# 程式設計手冊)"
ms.date: 2017-05-05
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- constructors [C#]
- classes [C#], constructors
- C# language, constructors
ms.assetid: df2e2e9d-7998-418b-8e7d-890c17ff6c95
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 400afcda2fe30bf0e3621ee4c4247486e01d3ee4
ms.contentlocale: zh-tw
ms.lasthandoff: 07/28/2017

---
# 建構函式 (C# 程式設計手冊)
每當建立[類別](../../../csharp/language-reference/keywords/class.md)或[結構](../../../csharp/language-reference/keywords/struct.md)時，就會呼叫它的建構函式。  類別或結構可能會有使用不同引數的多個建構函式。  建構函式讓程式設計人員能夠設定預設值、限制具現化，以及撰寫靈活易讀的程式碼。  如需詳細資訊與範例，請參閱 [使用建構函式](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)與 [執行個體建構函式](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。  
  
如不提供類別的建構函式，C# 預設會建立一個可具現化物件的建構函式，並將成員變數設定為預設值，如[預設值表](../../../csharp/language-reference/keywords/default-values-table.md)中所列。 如不提供結構的建構函式，C# 會回覆「隱含的預設建構函式」，自動將實值型別的每個欄位初始化為其預設值，如[預設值表](../../../csharp/language-reference/keywords/default-values-table.md)中所列。 如需詳細資訊及範例，請參閱[執行個體建構函式](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)。  

## <a name="constructor-syntax"></a>建構函式語法

建構函式是名稱與其類型名稱相同的方法。 其方法簽章只包含方法名稱及其參數清單，不包含傳回的類型。 下例示範名為 `Person` 的類別建構函式。

[!code-cs[建構函式](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#1)]  

如果建構函式可以實作為單一陳述式，您就可以使用[運算式主體定義](../statements-expressions-operators/expression-bodied-members.md)。 下列範例定義 `Location` 類別，這個類別的建構函式包含名為 *name* 的單一字串參數。 運算式主體定義會將引數指派給 `locationName` 欄位。

[!code-cs[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

## <a name="static-constructors"></a>靜態建構函式

前例都已顯示建立新物件的執行個體建構函式。 類別或結構也可以有靜態建構函式，用來初始化類型的靜態成員。  靜態建構函式無參數。 如不提供靜態建構函式來初始化靜態欄位，C# 編譯器會提供預設的靜態建構函式，將靜態欄位初始化為其預設值，如[預設值表](../../../csharp/language-reference/keywords/default-values-table.md)中所列。 

下列範例會使用靜態建構函式來初始化靜態欄位。

[!code-cs[建構函式](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#2)]  

您也可以使用運算式主體定義來定義靜態建構函式，如下例所示。 

[!code-cs[建構函式](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/constructors1.cs#3)]  

如需詳細資訊及範例，請參閱[靜態建構函式](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。  
  
 靜態類別和結構也可以擁有建構函式。  如需詳細資訊與範例，請參閱[靜態建構函式](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)。  
  
## 本章節內容  
 [使用建構函式](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)  
  
 [執行個體建構函式](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md)  
  
 [私用建構函式](../../../csharp/programming-guide/classes-and-structs/private-constructors.md)  
  
 [靜態建構函式](../../../csharp/programming-guide/classes-and-structs/static-constructors.md)  
  
 [如何：撰寫複製建構函式](../../../csharp/programming-guide/classes-and-structs/how-to-write-a-copy-constructor.md)  
  
## 請參閱  
 [C\# 程式設計手冊](../../../csharp/programming-guide/index.md)   
 [類別和結構](../../../csharp/programming-guide/classes-and-structs/index.md)   
 [解構函式](../../../csharp/programming-guide/classes-and-structs/destructors.md)   
 [static](../../../csharp/language-reference/keywords/static.md)   
 [為什麼初始設定式執行的順序與建構函式相反？第一部](http://go.microsoft.com/fwlink/?LinkId=112374)

