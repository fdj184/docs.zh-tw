---
title: 必須是初始設定式
ms.date: 07/20/2015
f1_keywords:
- vbc30996
- bc30996
helpviewer_keywords:
- BC30996
ms.assetid: 6e183fe0-8888-43ed-a062-01571079455f
ms.openlocfilehash: 0795fdc1c4b177e13979d7555cd7588217b8cb4c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59334961"
---
# <a name="initializer-expected"></a>必須是初始設定式
您嘗試使用物件初始設定式中的初始設定清單是空的如下列範例所示，宣告類別的執行個體。  
  
 `' Not valid.`  
  
 `' Dim aStudent As New Student With {}`  
  
 至少一個欄位或屬性必須在初始設定式清單中，初始化，如下列範例所示。  
  
 `Dim aStudent As New Student With {.year = "Senior"}`  
  
 **錯誤 ID:** BC30996  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
1. 初始化至少一個欄位或屬性初始設定式，或不使用物件初始設定式。  
  
## <a name="see-also"></a>另請參閱

- [物件初始設定式：具名和匿名類型](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [如何：使用物件初始設定式宣告物件](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-declare-an-object-by-using-an-object-initializer.md)
