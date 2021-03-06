---
title: HOW TO：呼叫程序不會傳回值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 6e3ce2a184ca5411a6a016929a16bf3d67e669ca
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864230"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>HOW TO：呼叫程序不會傳回值 (Visual Basic)
A`Sub`程序不會傳回呼叫程式碼的值。 明確呼叫它，以獨立的呼叫陳述式。 您無法直接使用其名稱，在運算式內呼叫它。  
  
### <a name="to-call-a-sub-procedure"></a>若要呼叫子函數程序  
  
1. 指定的名稱`Sub`程序。  
  
2. 程序名稱後面加上括號括住的引數清單。 如果不有任何引數，您可以選擇性地省略括號。 不過，使用括號可讓您的程式碼更方便閱讀。  
  
3. 以括弧括住，並以逗號分隔的引數清單括住的引數。 確定您提供的相同順序的引數，`Sub`程序會定義對應的參數。  
  
     下列範例會呼叫 Visual Basic<xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>函式來啟動應用程式視窗。 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 使用視窗標題做為其唯一引數。 它不會傳回呼叫程式碼的值。 如果未執行 「 記事本 」 處理程序，此範例會擲回<xref:System.ArgumentException>。 `Shell`程序會假設應用程式都在指定的路徑。  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>另請參閱

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [程序](./index.md)
- [Sub 程序](./sub-procedures.md)
- [程序參數和引數](./procedure-parameters-and-arguments.md)
- [Sub 陳述式](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [如何：建立程序](./how-to-create-a-procedure.md)
- [如何：呼叫傳回值的程序](./how-to-call-a-procedure-that-returns-a-value.md)
- [如何：在 Visual Basic 中呼叫事件處理常式](./how-to-call-an-event-handler.md)
