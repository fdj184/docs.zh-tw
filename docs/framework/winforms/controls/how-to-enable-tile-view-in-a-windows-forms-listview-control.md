---
title: HOW TO：在 Windows Forms ListView 控制項中啟用並排顯示
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tile view feature
- tiling
- Windows Forms, controls
- ListView control [Windows Forms], tile view
ms.assetid: c20e67a3-2d94-413d-9fcf-ecbd0fe251da
ms.openlocfilehash: 14eb21fa0285275e510b865c5cee7d1fc82fd0fd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941530"
---
# <a name="how-to-enable-tile-view-in-a-windows-forms-listview-control"></a>HOW TO：在 Windows Forms ListView 控制項中啟用並排顯示
使用的 <xref:System.Windows.Forms.ListView> 控制項的並排顯示檢視功能，您可以提供圖形和文字資訊之間的視覺化平衡。 並排顯示檢視中針對項目顯示的文字資訊與詳細資料檢視所定義的資料行資訊相同。 並排顯示檢視與 <xref:System.Windows.Forms.ListView> 控制項中的群組或插入標記功能相配合。  
  
 並排顯示檢視會使用 32 x 32 像素圖示和數行的文字，如下列影像所示。  
  
 ![ListView 控制項中並排](./media/how-to-enable-tile-view-in-a-windows-forms-listview-control/tile-view-in-listview-control.gif "圖格的圖示和文字")  
 
 若要啟用並排顯示檢視，請將 <xref:System.Windows.Forms.ListView.View%2A> 屬性設定為 <xref:System.Windows.Forms.View.Tile>。 您可以藉由設定 <xref:System.Windows.Forms.ListView.TileSize%2A> 屬性調整並排顯示的大小，並藉由調整 <xref:System.Windows.Forms.ListView.Columns%2A> 集合來調整並排顯示中顯示的文字行數。  
  
> [!NOTE]
>  並排顯示檢視是僅在您的應用程式呼叫 <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> 方法時適用於 [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] 上。 在舊版作業系統中，任何與並排顯示檢視相關的程式碼都無效，而且 <xref:System.Windows.Forms.ListView> 控制項會顯示在大圖示檢視中。 如需詳細資訊，請參閱<xref:System.Windows.Forms.ListView.View%2A?displayProperty=nameWithType>。  
  
### <a name="to-set-tile-view-programmatically"></a>以程式設計方式設定並排顯示檢視  
  
1. 使用 <xref:System.Windows.Forms.ListView> 控制項的 <xref:System.Windows.Forms.View> 的列舉。  
  
    ```vb  
    ListView1.View = View.Tile  
    ```  
  
    ```csharp  
    listView1.View = View.Tile;  
    ```  
  
## <a name="example"></a>範例  
 下列完整的程式碼範例示範並排顯示檢視，並修改為可顯示三行文字。 已經調整並排顯示大小以避免自動換行。  
  
 [!code-cpp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CPP/listviewtilingexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/CS/listviewtilingexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Tiling#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Tiling/VB/listviewtilingexample.vb#1)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 這個範例需要：  
  
- System 和 System.Windows.Forms 組件的參考。  
  
- 名為 book.ico 的圖示檔，位於與可執行檔相同的目錄中。  
  
 Visual Basic 或 Visual C# 建置此範例從命令列的相關資訊，請參閱[從命令列建置](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或是[命令列使用 csc.exe 建置](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 您也可以將程式碼貼入新的專案，以建置此範例的 Visual Studio。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.TileSize%2A>
- [ListView 控制項](listview-control-windows-forms.md)
- [ListView 控制項概觀](listview-control-overview-windows-forms.md)
