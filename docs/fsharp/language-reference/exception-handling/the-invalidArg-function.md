---
title: '例外狀況: invalidArg 函式'
description: 了解如何F#'invalidArg' 函式會產生引數例外狀況。
ms.date: 05/16/2016
ms.openlocfilehash: 7fd8d48b80970dbbafc0c23a478b4ccf3490f3ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996876"
---
# <a name="exceptions-the-invalidarg-function"></a>例外狀況: invalidArg 函式

`invalidArg`函式會產生引數例外狀況。

## <a name="syntax"></a>語法

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>備註

先前語法中的參數名稱是參數的其引數無效名稱的字串。 *錯誤訊息字串*是字串常值或型別的值`string`。 它會變成`Message`例外狀況物件的屬性。

產生的例外狀況`invalidArg`是`System.ArgumentException`例外狀況。 下列程式碼說明如何使用`invalidArg`擲回例外狀況。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

輸出是下列項目，後面接著 （未顯示） 的堆疊追蹤。

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>另請參閱

- [例外狀況處理](index.md)
- [例外狀況類型](exception-types.md)
- [例外狀況：`try...with`運算式](the-try-with-expression.md)
- [例外狀況：`try...finally`運算式](the-try-finally-expression.md)
- [例外狀況：`raise` 函式](the-raise-function.md)
- [例外狀況：`failwith`函式](the-failwith-function.md)