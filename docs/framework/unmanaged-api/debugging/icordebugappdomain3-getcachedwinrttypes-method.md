---
title: ICorDebugAppDomain3::GetCachedWinRTTypes 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a08e83d67c973294938a030b95b906aec6be6d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126603"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a>ICorDebugAppDomain3::GetCachedWinRTTypes 方法
取得列舉值，所有快取[!INCLUDE[wrt](../../../../includes/wrt-md.md)]型別。  
  
## <a name="syntax"></a>語法  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a>參數  
 `ppGuidToTypeEnum`  
 [out]指標[ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)介面的物件可以列舉的受管理的表示法[!INCLUDE[wrt](../../../../includes/wrt-md.md)]目前載入的應用程式定義域中的類型。  
  
## <a name="requirements"></a>需求  
 **平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 **標頭：** CorDebug.idl、CorDebug.h  
  
 **LIBRARY:** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>另請參閱

- [ICorDebugAppDomain3 介面](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
