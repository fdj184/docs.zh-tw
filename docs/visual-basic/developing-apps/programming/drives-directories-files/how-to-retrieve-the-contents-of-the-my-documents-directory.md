---
title: HOW TO：在 Visual Basic 中擷取 [我的文件] 目錄的內容
ms.date: 07/20/2015
helpviewer_keywords:
- My Documents directory
ms.assetid: 26560d01-7dda-4457-8e95-21db23d71aea
ms.openlocfilehash: fe98d3e92726dc6c4ed576ef989d968852c846d6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770291"
---
# <a name="how-to-retrieve-the-contents-of-the-my-documents-directory-in-visual-basic"></a>HOW TO：在 Visual Basic 中擷取 [我的文件] 目錄的內容
<xref:Microsoft.VisualBasic.FileIO.SpecialDirectories> 物件可以用來讀取許多 [所有使用者] 目錄，例如 [我的文件] 或 [桌面]。  
  
### <a name="to-read-from-the-my-documents-folder"></a>讀取 [我的文件] 資料夾  
  
-   使用 `ReadAllText` 方法，讀取特定目錄中每個檔案的文字。 下列程式碼指定目錄和檔案，然後使用 `ReadAllText` 將它們讀入名為 `patients` 的字串。  
  
     [!code-vb[VbVbcnMyFileSystem#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyFileSystem/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>另請參閱

- <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>
- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllText%2A>
