---
title: 安全性驗證和驗證失敗數
ms.date: 03/30/2017
ms.assetid: 0d4e3666-dfc6-421c-baf8-9479c22f7050
ms.openlocfilehash: 32a7d41f93dd99f1950a073e1cac1b62177ff6c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61916041"
---
# <a name="security-validation-and-authentication-failures"></a>安全性驗證和驗證失敗數
計數器名稱：安全性驗證和驗證失敗數  
  
## <a name="description"></a>描述  
 每當因為「未授權的安全性呼叫數」計數器所未涵蓋的安全性問題而拒絕訊息時，這個計數器就會遞增。 這類問題包括：  
  
- 無法從訊息中讀取用戶端權杖。  
  
- 用戶端權杖已經驗證失敗 (例如密碼錯誤)。  
  
- 簽章驗證已經失敗 (例如訊息遭到竄改)。  
  
- 此訊息與之前的訊息重複，這可能會在重新執行攻擊時發生。  
  
- 發生解密失敗。  
  
- 訊息中遺失某些必要的項目 (例如遺失時間戳記或加密的資料區塊)。  
  
- 在 TLSNEGO/SPNEGO 交換期間發生錯誤。
