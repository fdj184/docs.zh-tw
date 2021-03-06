---
title: x:Members 指示詞
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: d23e6b459af932e0a6f69309f26a1cce70a9d256
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938888"
---
# <a name="xmembers-directive"></a>x:Members 指示詞
會保留一份定義在標記中，其會套用至父元素的 x： 類別的成員。  
  
## <a name="xaml-attribute-usage"></a>XAML Attribute Usage  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|`className`|XAML 生產的支援類別或部分類別名稱。 請參閱＜備註＞。|  
|`oneOrMoreMembers`|表示成員定義的一或多個物件元素。 一般來說，這些是`x:Property`物件項目。 請參閱＜備註＞。|  
  
## <a name="remarks"></a>備註  
 在.NET Framework XAML 服務實作中中,，沒有任何支援類別或基礎成員實作`x:Members`。 `x:Members` 是特殊的 XAML 成員可以是存在於任何型別上的成員。 在 XAML 節點資料流中，`x:Members`代表成員，名為`Members`，從 XAML 語言 XAML 命名空間。 成員`Members`包含唯讀的泛型清單`Member`物件。 在典型的標記中的個別成員指定為`x:Property`屬性項目。 `x:Property` 更精確的類型，特別是針對類型的屬性並指派給`x:Member`。 如需詳細資訊，請參閱 < [X:property 指示詞](x-property-directive.md)。  
  
 若要支援實際使用 `x:Members` 做為在標記中指定成員定義的方法，這些成員必須與可修改的類別相關聯。 預期的模型是 `x:Members` 做為可指定 `x:Class` 之類型成員的形式存在。 不過，.NET Framework XAML 服務層級不支援關聯類型與成員或產生動態成員定義的機制。 這會保留給具有支援 XAML 成員定義之應用程式模型的個別架構。 通常需要 MSBUILD 建置動作以標記編譯 XAML，然後與程式碼後置整合，或是從 XAML 產生純組件，才能支援該功能。  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>X:members for Windows Workflow Foundation  
 對於 Windows Workflow Foundation，`x:Members`包含完全以 XAML 或 XAML 撰寫之自訂活動的成員-定義活動設計工具與程式碼後置的動態成員。 `x:Class` 也必須在 XAML 生產的根項目上指定。 這不是 .NET Framework XAML 服務層級的需求，但是當 XAML 生產是由支援自訂活動和 Windows Workflow Foundation XAML 的 MSBUILD 建置動作載入時，通常會變成需求。 `x:Members` 必須是第一個子項目在標記中宣告的物件項目`x:Class`。
