---
title: HOW TO：將 Gamma 修正套用至漸層
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gradient brushes [Windows Forms], gamma correction
- gradients [Windows Forms], gamma correction
ms.assetid: da4690e7-5fac-4fd2-b3f0-5cb35c165b92
ms.openlocfilehash: 066ccc649105018d20cb86b6e576a1a238e0dc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973262"
---
# <a name="how-to-apply-gamma-correction-to-a-gradient"></a>HOW TO：將 Gamma 修正套用至漸層
您可以藉由設定筆刷的線性漸層筆刷的 gamma 修正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>屬性設`true`。 您可以設定連線，停用 gamma 修正<xref:System.Drawing.Drawing2D.LinearGradientBrush.GammaCorrection%2A>屬性設`false`。 預設會停用 gamma 修正。  
  
## <a name="example"></a>範例  

下列範例是呼叫從控制項的方法<xref:System.Windows.Forms.Control.Paint>事件處理常式。 範例會建立線形漸層筆刷，並使用以填滿兩個矩形的筆刷。 Gamma 修正沒有填滿第一個矩形，第二個矩形填滿的 gamma 修正。  
  
 下圖顯示兩個填滿的矩形。 最上方的矩形，並沒有 gamma 修正，會在中間項目出現深。 下方的矩形，其具有 gamma 修正，似乎有多個統一的濃度。  
  
 ![漸層停駐](./media/gammagradient1.png "gammagradient1")  
  
 [!code-csharp[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.UsingaGradientBrush#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingaGradientBrush/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 上述範例中專為搭配 Windows Form 使用，而且需要<xref:System.Windows.Forms.PaintEventArgs> `e`，這是參數的<xref:System.Windows.Forms.Control.Paint>事件處理常式。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>
- [使用漸層筆刷填滿形狀](using-a-gradient-brush-to-fill-shapes.md)
