---
title: HOW TO：使用設計工具繫結 Windows Forms 控制項和 BindingSource 元件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: a4f87303954494e8e32d32e68fb3f1244f25680a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011708"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a>HOW TO：使用設計工具繫結 Windows Forms 控制項和 BindingSource 元件
您已將控制項新增至您的表單，並判斷您的應用程式的使用者介面之後，您可以將控制項繫結到資料來源，以便在執行階段，使用者可以改變，並將儲存應用程式相關的資料。  
  
 Windows Form 中的繫結的控制項或一系列的控制項最容易完成使用<xref:System.Windows.Forms.BindingSource>控制項在表單上的控制項與資料來源之間的橋樑。  
  
 在表單上的一個或多個控制項可以繫結至資料;在下列程序中，<xref:System.Windows.Forms.TextBox>控制項所繫結至資料來源。  
  
 若要完成此程序，則會假設您將繫結至衍生自資料庫的資料來源。 如需有關如何從其他存放區的資料建立資料來源的詳細資訊，請參閱 <<c0> [ 加入新的資料來源](/visualstudio/data-tools/add-new-data-sources)。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-bind-a-control-at-design-time"></a>將控制項繫結在設計階段  
  
1. 拖曳<xref:System.Windows.Forms.TextBox>入表單的控制項。  
  
2. 在 **屬性**視窗：  
  
    1.  依序展開 **(DataBindings)** 節點。  
  
    2.  按一下箭號旁<xref:System.Windows.Forms.TextBox.Text%2A>屬性。  
  
         **DataSource** UI 類型編輯器隨即開啟。  
  
         如果先前已設定資料來源的專案或表單，它會出現。  
  
3. 按一下 [新增專案資料來源] 以連接至資料，並建立資料來源。  
  
4. 在 [資料來源組態精靈] 歡迎頁面上，按 [下一步]。  
  
5. 在 **選擇資料來源類型**頁面上，選取**資料庫**。  
  
6. 在 **選擇資料連接**頁面上，從可用連線清單中選取資料連接。 如果您想要的資料連接不是可用的選取**新的連接**來建立新的資料連接。  
  
7. 選取  **是，將連接儲存為**應用程式組態檔中儲存的連接字串。  
  
8. 選取要帶入應用程式中的資料庫物件。 在此情況下，選取您想要的資料表中的 欄位<xref:System.Windows.Forms.TextBox>來顯示。  
  
9. 您可以視需要更換預設資料集名稱。  
  
10. 按一下 [ **完成**]。  
  
11. 在 [**屬性**] 視窗中，按一下箭號旁<xref:System.Windows.Forms.TextBox.Text%2A>屬性一次。 在  **DataSource** UI 類型編輯器中，選取要繫結的欄位名稱<xref:System.Windows.Forms.TextBox>到。  
  
     **DataSource** UI 類型編輯器關閉和資料集，<xref:System.Windows.Forms.BindingSource>和資料表配接器的特定資料連接會加入至您的表單。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [新增資料來源](/visualstudio/data-tools/add-new-data-sources)
- [資料來源視窗](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))