---
title: HOW TO：在設計階段將控制項對齊表單邊緣
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], docking using designer
- Dock property [Windows Forms], aligning controls (using designer)
ms.assetid: 51f08998-5e3b-4330-be58-a4edd0eb60f4
ms.openlocfilehash: 8ca6fd64edbd73301fd298f42c3d4d97d021888a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331856"
---
# <a name="how-to-align-a-control-to-the-edges-of-forms-at-design-time"></a>HOW TO：在設計階段將控制項對齊表單邊緣
您可以讓控制項對齊表單邊緣藉由設定<xref:System.Windows.Forms.Control.Dock%2A>。 這個屬性會指定您的控制項在表單中的位置。 可將 <xref:System.Windows.Forms.Control.Dock%2A> 屬性設為下列值：  
  
|設定|對控制項的影響|  
|-------------|----------------------------|  
|<xref:System.Windows.Forms.DockStyle.Bottom>|停駐在表單下方。|  
|<xref:System.Windows.Forms.DockStyle.Fill>|填滿表單中剩下的空間。|  
|<xref:System.Windows.Forms.DockStyle.Left>|停駐在表單左方。|  
|<xref:System.Windows.Forms.DockStyle.None>|未停駐在任何地方，且會出現在所指定的位置及其<xref:System.Windows.Forms.Control.Location%2A>。|  
|<xref:System.Windows.Forms.DockStyle.Right>|停駐在表單右方。|  
|<xref:System.Windows.Forms.DockStyle.Top>|停駐在表單上方。|  
  
 也可以在程式碼中設定這些值。 如需詳細資訊，請參閱[如何：將控制項和表單邊緣對齊](how-to-align-a-control-to-the-edges-of-forms.md)。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-set-the-dock-property-for-your-control-at-design-time"></a>若要在設計階段設定控制項的 Dock 屬性  
  
1. 在 Windows Form 設計工具中，選取您的控制項。  
  
2. 在 [**屬性**視窗中，按一下下拉式清單方塊的下的一步]<xref:System.Windows.Forms.Control.Dock%2A>屬性。  
  
     代表六個可能的圖形化介面<xref:System.Windows.Forms.Control.Dock%2A>設定隨即出現。  
  
3. 選擇適當的設定。  
  
4. 您的控制項現在會設定所指定的方式停駐。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.Control.Dock%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.Anchor%2A?displayProperty=nameWithType>
- [如何：將控制項和表單邊緣對齊](how-to-align-a-control-to-the-edges-of-forms.md)
- [逐步解說：使用對齊線的 Windows Form 上排列控制項](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [如何：在 Windows Forms 上控制項的錨定](how-to-anchor-controls-on-windows-forms.md)
- [如何：錨定和停駐 TableLayoutPanel 控制項中的子控制項](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [如何：錨定和停駐 FlowLayoutPanel 控制項中的子控制項](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [逐步解說：排列 Windows Form 使用 TableLayoutPanel 控制項](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [逐步解說：排列 Windows Form 使用 FlowLayoutPanel 控制項](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [在設計階段開發 Windows Forms 控制項](developing-windows-forms-controls-at-design-time.md)
