---
title: HOW TO：列出已安裝的解碼器
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: c92b8010def2f77f859ee0bd9cdb1ed51dd15f27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61723039"
---
# <a name="how-to-list-installed-decoders"></a>HOW TO：列出已安裝的解碼器
若要列出可用的電腦上，影像解碼器，來判斷您的應用程式是否可以讀取特定影像檔案格式。 <xref:System.Drawing.Imaging.ImageCodecInfo>類別提供<xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>靜態方法，如此您就可以判斷哪一個映像會提供解碼器。 <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> 傳回的陣列<xref:System.Drawing.Imaging.ImageCodecInfo>物件。  
  
## <a name="example"></a>範例  
 下列程式碼範例會輸出一份已安裝的解碼器和其屬性值。  
  
 [!code-csharp[UsingImageEncodersDecoders#2](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>編譯程式碼  
 這個範例需要：  
  
- Windows Forms 應用程式。  
  
- A <xref:System.Windows.Forms.PaintEventArgs>，這是參數的<xref:System.Windows.Forms.PaintEventHandler>。  
  
## <a name="see-also"></a>另請參閱

- [如何：列出已安裝的編碼器](how-to-list-installed-encoders.md)
- [使用 Managed GDI+ 中的影像編碼器和解碼器](using-image-encoders-and-decoders-in-managed-gdi.md)
