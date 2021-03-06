---
title: 類型 <typename> 不符合 CLS 標準
ms.date: 07/20/2015
f1_keywords:
- bc40041
- vbc40041
helpviewer_keywords:
- BC40041
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
ms.openlocfilehash: 243f51b3e6c798c82fdbe7b28557c4f96c728bf2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764370"
---
# <a name="type-typename-is-not-cls-compliant"></a>型別\<類型名稱 > 不符合 CLS 標準
使用不符合 CLS 標準的資料類型來宣告變數、 屬性或函式傳回。  
  
 若要符合應用程式[Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) （cls） 標準，它必須使用只有符合 CLS 規範的型別。  
  
 下列 Visual Basic 資料類型不符合 CLS 標準：  
  
- [SByte 資料類型](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [UInteger 資料類型](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [ULong 資料類型](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [UShort 資料類型](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **錯誤 ID:** BC40041  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
- 如果您的應用程式必須符合 CLS 標準，變更資料類型的這個項目以最符合 CLS 規範的型別。 例如，如果您不需要 2,147,483,647 以上的值範圍，而且不使用 `UInteger` ，則可能可以使用 `Integer` 。 如果您需要擴充範圍，則可以將 `UInteger` 取代為 `Long`。  
  
- 如果您的應用程式不需要符合 CLS 標準，您不需要變更任何項目。 您應留意其不符合規範，不過。