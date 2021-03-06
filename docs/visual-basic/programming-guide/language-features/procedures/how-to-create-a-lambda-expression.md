---
title: HOW TO：建立 Lambda 運算式 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: fc2b7ed2004b842116d051b393f00506428def61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665932"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a>HOW TO：建立 Lambda 運算式 (Visual Basic)
A *lambda 運算式*函式或副程式，並沒有名稱。 只要委派型別有效，則可以使用 lambda 運算式。  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a>若要建立的單行 lambda 運算式函式  
  
1. 在委派型別可以使用其中任何情況下，輸入關鍵字`Function`，如下列範例所示：  
  
     `Dim add1 =`   `Function`  
  
2. 在括號內，直接在之後`Function`，型別函式的參數。 請注意，您不指定的名稱之後`Function`。  
  
     `Dim add1 = Function`   `(num As Integer)`  
  
3. 下列參數清單中，輸入單一運算式做為函式的主體。 運算式評估為值是函式所傳回的值。 您不使用`As`子句，以指定的傳回型別。  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     Lambda 運算式可以呼叫傳入整數引數。  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. 或者，是由下列的範例來完成相同的結果：  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a>若要建立副程式，單行 lambda 運算式  
  
1. 在委派型別可以使用其中任何情況下，輸入關鍵字`Sub`，如下列範例所示。  
  
     `Dim add1 =`   `Sub`  
  
2. 在括號內，直接在之後`Sub`，型別參數的副程式。 請注意，您不指定的名稱之後`Sub`。  
  
     `Dim add1 = Sub`   `(msg As String)`  
  
3. 下列參數清單中，輸入單一陳述式為副程式的內文。  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     Lambda 運算式可以呼叫傳入的字串引數。  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a>若要建立多行 lambda 運算式函式  
  
1. 在委派型別可以使用其中任何情況下，輸入關鍵字`Function`，如下列範例所示。  
  
     `Dim add1 =`   `Function`  
  
2. 在括號內，直接在之後`Function`，型別函式的參數。 請注意，您不指定的名稱之後`Function`。  
  
     `Dim add1 = Function`   `(index As Integer)`  
  
3. 請按 ENTER 鍵。 `End Function`陳述式會自動加入。  
  
4. 在函式主體中，新增下列程式碼，以建立運算式，並傳回值。 您不使用`As`子句，以指定的傳回型別。  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     Lambda 運算式可以呼叫傳入整數引數。  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a>若要建立多行 lambda 運算式副程式  
  
1. 在委派型別可以使用其中任何情況下，輸入關鍵字`Sub`，如下列範例所示：  
  
     `Dim add1 =`   `Sub`  
  
2. 在括號內，直接在之後`Sub`，型別參數的副程式。 請注意，您不指定的名稱之後`Sub`。  
  
     `Dim add1 = Sub`  `(msg As String)`  
  
3. 請按 ENTER 鍵。 `End Sub`陳述式會自動加入。  
  
4. 在函式主體中，新增下列程式碼執行時叫用副程式。  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     Lambda 運算式可以呼叫傳入的字串引數。  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a>範例  
 Lambda 運算式的常見用法是定義的函式，可以做為參數的型別引數傳入`Delegate`。 在下列範例中，<xref:System.Diagnostics.Process.GetProcesses%2A>方法會傳回陣列的本機電腦上執行的處理程序。 <xref:System.Linq.Enumerable.Where%2A>方法，從<xref:System.Linq.Enumerable>類別需要`Boolean`委派作為其引數。 在範例中的 lambda 運算式用於該目的。 它會傳回`True`每個處理序具有只有一個執行緒，且在已選取這些`filteredList`。  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 上述範例相當於下列程式碼，以撰寫[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]語法：  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Linq.Enumerable>
- [Lambda 運算式](./lambda-expressions.md)
- [Function 陳述式](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub 陳述式](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [委派](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [如何：傳遞至另一個程序，在 Visual Basic 中的程序](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)
- [Delegate 陳述式](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Visual Basic 中的 LINQ 簡介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
