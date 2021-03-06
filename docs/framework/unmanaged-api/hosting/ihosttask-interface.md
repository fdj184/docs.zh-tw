---
title: IHostTask 介面
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb15da31d91565d49df83099045f742866eebcaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081498"
---
# <a name="ihosttask-interface"></a>IHostTask 介面
提供方法，可讓 common language runtime (CLR) 與主應用程式管理工作進行通訊。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Alert 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|要求主機喚醒表示由目前的工作`IHostTask`執行個體，因此可以中止的工作。|  
|[GetPriority 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|取得表示目前的工作的執行緒優先權層級`IHostTask`執行個體。|  
|[Join 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|表示由目前的工作之前會封鎖呼叫的工作`IHostTask`執行個體完成後，將指定的時間間隔過去後，或是[ihosttask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)呼叫。|  
|[SetCLRTask 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|將產生關聯[ICLRTask 介面](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)與目前的執行個體`IHostTask`執行個體。|  
|[SetPriority 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|表示由目前的工作要求主應用程式調整的執行緒優先權層級`IHostTask`執行個體。|  
|[Start 方法](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|要求主機移到表示由目前的工作`IHostTask`從暫停狀態的即時狀態，可以在其中執行程式碼的執行個體。|  
  
## <a name="remarks"></a>備註  
 CLR 會呼叫所定義的方法`IHostTask`啟動工作，設定它的執行緒優先權層級，依此類推。  
  
## <a name="requirements"></a>需求  
 **平台：** 請參閱[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** MSCorEE.h  
  
 **LIBRARY:** 包含做為 MSCorEE.dll 中的資源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱

- [ICLRTask 介面](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 介面](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager 介面](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [裝載介面](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
