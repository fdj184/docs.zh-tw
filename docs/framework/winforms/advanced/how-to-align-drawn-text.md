---
title: HOW TO：對齊繪製的文字
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 0e77e4d8eeb9d7a07115b89525ac80074afeb6e8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937809"
---
# <a name="how-to-align-drawn-text"></a>HOW TO：對齊繪製的文字
當您執行自訂繪圖時，您通常可以在表單或控制項上的繪製的文字置中對齊。 您可以輕鬆地將以繪製文字的對齊<xref:System.Drawing.Graphics.DrawString%2A>或<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法藉由建立正確的格式物件，並設定適當的格式旗標。  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>若要繪製置中對齊文字使用 GDI + (DrawString)  
  
1. 使用<xref:System.Drawing.StringFormat>與適當<xref:System.Drawing.Graphics.DrawString%2A>方法來指定置中對齊的文字。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>若要繪製置中對齊文字使用 GDI (DrawText)  
  
1. 使用<xref:System.Windows.Forms.TextFormatFlags>列舉型別換行，以及以垂直和水平置中與適當的文字<xref:System.Windows.Forms.TextRenderer.DrawText%2A>方法。  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 上述程式碼範例專為搭配 Windows Form 使用，而且它們需要<xref:System.Windows.Forms.PaintEventArgs> `e`，這是參數的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>另請參閱

- [如何：使用 GDI 繪製文字](how-to-draw-text-with-gdi.md)
- [使用字型和文字](using-fonts-and-text.md)
- [如何：建構字型系列和字型](how-to-construct-font-families-and-fonts.md)
