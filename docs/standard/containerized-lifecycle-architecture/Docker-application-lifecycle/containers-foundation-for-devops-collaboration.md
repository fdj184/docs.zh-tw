---
title: 作為 DevOps 共同作業基礎的容器
description: 了解容器，以簡化 DevOps 的重要角色。
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 4b40837bf2b74d801b9794c88e79eb03bcd72e95
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679095"
---
# <a name="containers-as-the-foundation-for-devops-collaboration"></a>作為 DevOps 共同作業基礎的容器

容器和 Docker 技術的本質，開發人員即可共用其軟體和相依性輕鬆地與 IT 營運及生產環境時排除的一般 「 works 我的電腦 」 的藉口。 容器會解決不同環境之間的應用程式衝突。 間接容器和 Docker 將人員和 IT 操作更接近結合在一起，讓他們有效率地共同作業更容易。 採用容器 workflow 他們已搜尋，但先前已實作透過更複雜的設定版本和建置管線的 DevOps 持續性提供許多的客戶。 容器會簡化 DevOps 中的建置/測試/部署管線。

![Docker 可協助建置開發/設計工作負載和執行/監視/管理工作負載中的 IT 營運上的開發人員和架構設計人員之間的橋接器](./media/image1.png)

**圖 2-1。** 每個容器化 Docker 應用程式生命週期中的 「 人物代表 」 的主要工作負載

使用 Docker 容器，自己的開發人員為何 （應用程式和服務和架構和元件的相依性） 的容器和容器和服務的服務集合所組成的應用程式一起行為方式。 中所定義的相互依存性的多個容器`docker-compose.yml`檔案，或可以呼叫的動作*部署資訊清單*。 同時，（IT 專業人員和管理） 的 IT 作業小組可以專注於實際執行環境; 的管理基礎結構;延展性;監視;和最終，確保 ，應用程式提供正確的使用者，而不需要知道各種容器的內容。 因此，名稱"容器，「 重新叫用至真實世界運送容器比喻。 因此，容器的內容的擁有者需要考慮本身與如何將運送容器，並傳送公司傳輸到其目的地從其來源點容器而不需要知道或在意有關內容。 以類似的方式，開發人員可以建立和擁有的內容，而不需要顧慮的 「 傳輸 」 機制的 Docker 容器內。

在左側的 圖 2-1 中的要件，開發人員撰寫和程式碼在本機 Docker 容器中執行使用 Docker for Windows 或 mac。 他們可以使用 Dockerfile，指定基底的作業系統，以及建置它們的程式碼的 Docker 映像的建置步驟執行，以定義的程式碼的作業環境。 開發人員定義如何一或多個映像將交互操作，使用上述`docker-compose.yml`檔案部署資訊清單。 當他們完成其本機開發時，它們推送其應用程式程式碼，再加上的 Docker 組態檔至他們的選擇 （也就是 Git 儲存機制） 的程式碼存放庫。

DevOps 要件定義組建 – 連續整合 (CI) 管線，使用程式碼存放庫中提供的 Dockerfile。 CI 系統會從選取的 Docker 登錄中提取的基底容器映像，並建置應用程式的自訂 Docker 映像。 然後將映像可能會是裝置進行驗證，並推送至 Docker 登錄，用於至多個環境部署。

在右側的要件，作業小組管理已部署應用程式和基礎結構，讓他們能夠提供意見反應和深入解析給開發小組應用程式的可能監視的環境和應用程式時的生產環境中已改善。 容器應用程式通常會使用容器協調器的生產環境中執行。

兩個小組正在進行共同作業，透過基礎平台 （Docker 容器中） 所提供的關注點分離做為合約，同時大幅提升應用程式生命週期中的兩個小組的共同作業。 開發人員擁有容器內容、 其作業的環境和容器相互依存性，而作業小組需要建置的映像，以及資訊清單，且其協調流程系統中執行它們。

## <a name="challenges-in-application-life-cycle-when-using-docker"></a>使用 Docker 時，循環顯示應用程式生命週期中的挑戰。

有許多原因，可在即將推出的幾年，提升容器化應用程式的數目和這些原因之一是建立微服務為基礎的應用程式。

在過去 15 年來，使用 web 服務已基底的數千個應用程式，並可能幾年之後，我們會發現相同的情況的 Docker 容器上執行的微服務架構應用程式。

也很值得一提，您也可以使用 Docker 容器的整合型應用程式，而您仍然收到最大的 Docker 的優勢。 容器不會以僅微服務為目標。

使用新挑戰會導致您的組織，因此，您的開發程序中的 Docker 容器化和微服務需要紮實的策略，以維護許多容器和微服務在生產環境系統上執行。 最後，企業應用程式會有數百或數千個生產環境中執行的容器/執行個體。

當使用 DevOps 工具，因此您必須在您的 DevOps 活動，定義新的程序，並針對這種問題的解答，這些挑戰會建立新的需求：

- 我可以使用哪些工具進行開發，CI/CD、 管理和作業？

- 我如何的公司管理在容器中的錯誤時在生產環境中執行？

- 我們要如何變更我們的軟體，以最少的停機時間的生產環境中的項目？

- 我們要如何能夠調整和我們要如何監視生產系統？

- 如何可以我們測試和部署容器中包含我們的發行管線？

- 我們要如何在 Microsoft Azure 中的容器使用開放原始碼工具/平台？

如果您可以回答所有這些問題，您就更能夠移動您的應用程式 （現有或新應用程式） 的 Docker 容器。 

## <a name="introduction-to-a-generic-end-to-end-docker-application-life-cycle-workflow"></a>泛用端對端的 Docker 應用程式生命週期工作流程簡介

圖 2-2 提供更詳細的工作流程 Docker 應用程式生命週期，著重於這個執行個體中特定的 DevOps 活動和資產。

![下圖顯示 「 外部迴圈 」 的 DevOps。 當程式碼會推送至存放庫中時，CI 管線啟動時，，然後開始 CD 管線，應用程式取得部署位置。 從已部署應用程式收集的計量會回送入的開發工作負載中，「 內部迴圈 」 的發生，因此開發小組有實際的資料，以回應使用者和商務需求。](./media/image2.png)

**圖 2-2。** 針對 Docker 容器化應用程式生命週期的高階工作流程

所有項目開始使用開發人員會啟動內部迴圈工作流程中撰寫程式碼。 內部迴圈階段可讓開發人員便會定義將程式碼推送至程式碼存放庫 （例如，原始檔控制系統 Git 等） 之前發生的所有項目。 在它之後已認可，持續整合 (CI) 的存放庫觸發程序和工作流程的其餘部分。

內部迴圈基本上包含類似 「 程式碼，"[執行，]"test"和"debug，"以及之前在本機執行應用程式所需的其他步驟的一般步驟。 這是開發人員的程序來執行和測試應用程式作為 Docker 容器。 內部迴圈工作流程將會在下列各節中說明。

採取的步驟上一步來看看的端對端工作流程，DevOps 工作流程，超過一項技術，或者一工具組： 它是一種心態需要文化特性的發展。 它的人員、 程序，以及適當的工具讓您更快速且更容易預測的應用程式生命週期。 企業通常採用容器化工作流程，重新建構其組織來代表人員和比對容器化工作流程的程序。

練習 DevOps 可協助小組更快速回應一起競爭壓力出錯的手動程序取代成自動化功能，這會導致改良的可追蹤性和可重複的工作流程。 組織也可以更有效率地管理環境和實現成本節約與內部部署和雲端資源的組合，以及緊密整合的工具。

當實作您的 DevOps 工作流程，Docker 應用程式，您會看到 Docker 技術會出現在工作流程，幾乎每個階段中您的開發電腦使用建置-測試-CI 階段中，內部迴圈 （程式碼中，執行、 偵錯） 時，最後，這些容器部署至預備和生產環境。

改善品質作法有助於找出缺失及早在開發週期，進而減少修正 bug 的成本。 映像中包括的環境和相依性，並採用更是哲學，跨多個環境中部署相同的映像，您可以升級擷取讓部署更可靠的環境特定組態的專業領域。

透過有效的檢測 （監視和診斷） 所獲得的豐富資料提供深入了解效能問題和使用者行為，以引導未來的優先順序和投資效益。

應該被視為 DevOps 之旅，而不是目的地。 它就應該透過適當地限定範圍的專案，從中展現成功、 學習和發展以累加方式實作。

## <a name="benefits-of-devops-for-containerized-applications"></a>容器化應用程式的 DevOps 的權益

以下是一些最重要的優點，提供穩固的 DevOps 工作流程名稱：

- 更快速且更好的合規性，請提供更高品質軟體。

- 推動持續改進和調整，更早版本，且更經濟實惠。

- 增加透明度和傳遞，和作業系統軟體所涉及的專案關係人之間的共同作業。

- 控制成本以及更有效地利用佈建的資源，同時安全性風險降至最低。

- 插與許多現有的 DevOps 投資，包括開放原始碼中的投資。

>[!div class="step-by-step"]
>[上一頁](index.md)
>[下一頁](../Microsoft-platform-tools-containerized-apps/index.md)
