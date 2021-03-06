---
title: HOW TO：建立和設定 Windows Forms 中 ToolStrip 控制項的自訂轉譯器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: ca1a7444c029632f83b1600e5855a13c83777594
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772901"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a>HOW TO：建立和設定 Windows Forms 中 ToolStrip 控制項的自訂轉譯器
<xref:System.Windows.Forms.ToolStrip> 控制項讓您輕鬆支援佈景主題和樣式。 您可以達到完全自訂的外觀和行為 （外觀及操作） 設定<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>屬性或<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>自訂轉譯器的屬性。  
  
 您可以將轉譯器指派給每個個別<xref:System.Windows.Forms.ToolStrip>， <xref:System.Windows.Forms.MenuStrip>， <xref:System.Windows.Forms.ContextMenuStrip>，或<xref:System.Windows.Forms.StatusStrip>控制項，或者您可以使用<xref:System.Windows.Forms.ToolStripManager.Renderer%2A>屬性，以便藉由設定影響所有物件<xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType>屬性設<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> 會傳回<xref:System.Windows.Forms.ToolStripRenderMode.Custom>只有當的值<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>不是`null`。  
  
### <a name="to-create-a-custom-renderer"></a>若要建立自訂轉譯器  
  
1. 擴充<xref:System.Windows.Forms.ToolStripRenderer>類別。  
  
2. 實作所需的自訂轉譯藉由覆寫適當*上...* 成員  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a>若要設定為目前的轉譯器的自訂轉譯器  
  
1. 若要設定自訂轉譯器，其中<xref:System.Windows.Forms.ToolStrip>，將<xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>自訂轉譯器的屬性。  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. 或若要設定所有的自訂轉譯器<xref:System.Windows.Forms.ToolStrip>類別包含在您的應用程式：設定<xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>為自訂轉譯器並將屬性<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>屬性設<xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>。  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [ToolStrip 控制項概觀](toolstrip-control-overview-windows-forms.md)
- [ToolStrip 控制項架構](toolstrip-control-architecture.md)
- [ToolStrip 技術摘要](toolstrip-technology-summary.md)
