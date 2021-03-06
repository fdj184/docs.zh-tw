---
title: HOW TO：在 Windows Forms 應用程式中建立 HTML 文件檢視器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebBrowser control [Windows Forms], creating an HTML document viewer
- document viewers
- Windows Forms, creating document viewers
ms.assetid: 6a6338fe-f7ee-4f5e-9d8f-0465c57e9039
ms.openlocfilehash: 99609e4bf5a352c436986e0773375d1c8e15e790
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746968"
---
# <a name="how-to-create-an-html-document-viewer-in-a-windows-forms-application"></a>HOW TO：在 Windows Forms 應用程式中建立 HTML 文件檢視器
您可以使用<xref:System.Windows.Forms.WebBrowser>控制項來顯示和列印 HTML 文件，而不需提供網際網路網頁瀏覽器的完整功能。 當您想要利用 HTML 格式化功能，但不是希望使用者載入任意的網頁可能包含不受信任的 Web 控制項或潛在的惡意指令碼時，這非常有用。 您可能想要限制的功能<xref:System.Windows.Forms.WebBrowser>以這種方式，例如，控制，使用它作為 HTML 電子郵件檢視器，或提供您的應用程式中 HTML 格式的說明。  
  
### <a name="to-create-an-html-document-viewer"></a>若要建立 HTML 文件檢視器  
  
1. 設定<xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>屬性，以`false`若要避免<xref:System.Windows.Forms.WebBrowser>控制項開啟放到它上面的檔案。  
  
     [!code-csharp[WebBrowserMisc#20](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#20)]
     [!code-vb[WebBrowserMisc#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#20)]  
  
2. 設定<xref:System.Windows.Forms.WebBrowser.Url%2A>屬性顯示的初始檔案的位置。  
  
     [!code-csharp[WebBrowserMisc#21](~/samples/snippets/csharp/VS_Snippets_Winforms/WebBrowserMisc/CS/WebBrowserMisc.cs#21)]
     [!code-vb[WebBrowserMisc#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/WebBrowserMisc/vb/WebBrowserMisc.vb#21)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 這個範例需要：  
  
- 名為 `webBrowser1` 的 <xref:System.Windows.Forms.WebBrowser> 控制項。  
  
- `System` 和 `System.Windows.Forms` 組件的參考。  
  
## <a name="see-also"></a>另請參閱

- <xref:System.Windows.Forms.WebBrowser>
- <xref:System.Windows.Forms.WebBrowser.AllowWebBrowserDrop%2A>
- <xref:System.Windows.Forms.WebBrowser.Url%2A>
- [WebBrowser 控制項概觀](webbrowser-control-overview.md)
- [WebBrowser 安全性](webbrowser-security.md)
- [如何：瀏覽至 URL，以使用 WebBrowser 控制項](how-to-navigate-to-a-url-with-the-webbrowser-control.md)
- [如何：使用 WebBrowser 控制項列印](how-to-print-with-a-webbrowser-control.md)
