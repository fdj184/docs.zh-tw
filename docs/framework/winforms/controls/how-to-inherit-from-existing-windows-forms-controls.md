---
title: HOW TO：繼承現有的 Windows Forms 控制項
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 788addee7c024577d029626da4aeb86d0ca9076a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941150"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a>HOW TO：繼承現有的 Windows Forms 控制項
如果您想要擴充現有控制項的功能，您可以透過繼承來建立衍生自現有控制項的控制項。 繼承自現有的控制項時，您會繼承該控制項的所有功能和視覺屬性。 例如，如果您所建立的控制項繼承自<xref:System.Windows.Forms.Button>、 您的新控制項看起來和 act 完全像標準<xref:System.Windows.Forms.Button>控制項。 您就可以透過實作自訂方法和屬性，來擴充或修改新控制項的功能。 在一些控制項中，您也可以變更繼承的控制項的視覺外觀藉由覆寫其<xref:System.Windows.Forms.Control.OnPaint%2A>方法。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-create-an-inherited-control"></a>建立繼承的控制項  
  
1. 建立新的 [Windows Forms 應用程式] 專案。  
  
2. 從 [專案] 功能表選擇 [新增項目]。  
  
     [新增項目] 對話方塊隨即出現。  
  
3. 在 [新增項目] 對話方塊中，連按兩下 [自訂控制項]。  
  
     新的自訂控制項會新增至您的專案。  
  
4. 如果您使用 Visual Basic，請在 [方案總管] 的頂端，按一下 [顯示所有檔案]。 展開 CustomControl1.vb，然後在程式碼編輯器中開啟 CustomControl1.Designer.vb。  
  
5. 如果您使用 C#，請在程式碼編輯器中開啟 CustomControl1.cs。  
  
6. 找出類別宣告中，繼承自<xref:System.Windows.Forms.Control>。  
  
7. 將基底類別變更為您想要繼承的控制項。  
  
     例如，如果您想要繼承自<xref:System.Windows.Forms.Button>，將類別宣告變更如下：  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8. 如果您使用 Visual Basic，請儲存並關閉 CustomControl1.Designer.vb。 在程式碼編輯器中開啟 CustomControl1.vb。  
  
9. 實作您的控制項將併入的任何自訂方法或屬性。  
  
10. 如果您想要修改您的控制項的圖形化外觀，覆寫<xref:System.Windows.Forms.Control.OnPaint%2A>方法。  
  
    > [!NOTE]
    >  覆寫<xref:System.Windows.Forms.Control.OnPaint%2A>將不允許您修改所有控制項的外觀。 所有由 Windows 完成其繪製這些控制項 (例如<xref:System.Windows.Forms.TextBox>) 絕不會呼叫其<xref:System.Windows.Forms.Control.OnPaint%2A>方法，，因此永遠不會使用自訂程式碼。 請參閱說明文件特定的控制項，您想要修改是否<xref:System.Windows.Forms.Control.OnPaint%2A>方法才有效。 如需所有 Windows Forms 控制項的清單，請參閱[要在 Windows Forms 上使用的控制項](controls-to-use-on-windows-forms.md)。 如果控制項沒有<xref:System.Windows.Forms.Control.OnPaint%2A>列為成員方法，您無法變更其外觀藉由覆寫這個方法。 如需自訂繪製的詳細資訊，請參閱[自訂控制項繪製和轉譯](custom-control-painting-and-rendering.md)。  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. 儲存並測試您的控制項。  
  
## <a name="see-also"></a>另請參閱

- [各種自訂控制項](varieties-of-custom-controls.md)
- [如何：繼承自 Control 類別](how-to-inherit-from-the-control-class.md)
- [如何：繼承自 UserControl 類別](how-to-inherit-from-the-usercontrol-class.md)
- [如何：撰寫 Windows forms 的控制項](how-to-author-controls-for-windows-forms.md)
- [Visual Basic 中的繼承事件處理常式疑難排解](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [逐步解說：繼承自使用 Visual Basic 的 Windows Forms 控制項](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [逐步解說：繼承自具有視覺效果的 Windows Forms 控制項C#](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
