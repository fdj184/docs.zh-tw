---
title: "'Module' 陳述式只可以發生在檔案或命名空間層級"
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: bf0239422fb5a98e4670aea407f684753d3a7ea4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920857"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a>'Module' 陳述式只可以發生在檔案或命名空間層級
`Module` 陳述式必須出現在原始程式檔頂端之後立即`Option`和`Imports`陳述式、 全域屬性和命名空間宣告，但所有其他宣告前面。  
  
 **錯誤 ID:** BC30617  
  
## <a name="to-correct-this-error"></a>更正這個錯誤  
  
-   將 `Module` 陳述式移至命名空間宣告或原始程式檔的上方。  
  
## <a name="see-also"></a>另請參閱

- [Module 陳述式](../../../visual-basic/language-reference/statements/module-statement.md)
