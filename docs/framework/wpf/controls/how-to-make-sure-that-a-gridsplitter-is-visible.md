---
title: HOW TO：確保 GridSplitter 是可見的
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: b7543d14ba39d854b5a2c3f4d0d19b9a457ea89b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770847"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>HOW TO：確保 GridSplitter 是可見的
此範例示範如何確定<xref:System.Windows.Controls.GridSplitter>中的其他控制項並未隱藏控制項<xref:System.Windows.Controls.Grid>。  
  
## <a name="example"></a>範例  
 <xref:System.Windows.Controls.Panel.Children%2A>的<xref:System.Windows.Controls.Grid>控制項以它們在標記或程式碼中定義的順序呈現。 <xref:System.Windows.Controls.GridSplitter> 控制項可以隱藏的其他控制項，如果您沒有定義輸出中的最後一個項目<xref:System.Windows.Controls.Panel.Children%2A>集合，或如果您提供其他控制較高<xref:System.Windows.Controls.Panel.ZIndexProperty>。  
  
 若要避免隱藏<xref:System.Windows.Controls.GridSplitter>控制項，執行下列其中一項。  
  
- 請確定<xref:System.Windows.Controls.GridSplitter>控制項是最後<xref:System.Windows.Controls.Panel.Children%2A>新增至<xref:System.Windows.Controls.Grid>。 下列範例所示<xref:System.Windows.Controls.GridSplitter>中的最後一個元素<xref:System.Windows.Controls.Panel.Children%2A>的集合<xref:System.Windows.Controls.Grid>。  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- 設定<xref:System.Windows.Controls.Panel.ZIndexProperty>上<xref:System.Windows.Controls.GridSplitter>到以上的控制項，否則會隱藏起來。 下列範例會提供<xref:System.Windows.Controls.GridSplitter>控制較高<xref:System.Windows.Controls.Panel.ZIndexProperty>比<xref:System.Windows.Controls.Button>控制項。  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- 否則會隱藏在控制項上設定邊界<xref:System.Windows.Controls.GridSplitter>以便<xref:System.Windows.Controls.GridSplitter>公開。 下列範例會設定邊界上的控制項，否則會重疊，並會隱藏<xref:System.Windows.Controls.GridSplitter>。  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Controls.GridSplitter>
- [HOW-TO 主題](gridsplitter-how-to-topics.md)
