---
title: SqlStreamChars.IsNull 屬性 (System.Data.SqlTypes)
author: stevestein
ms.author: sstein
ms.date: 12/19/2018
ms.technology: dotnet-data
topic_type:
- apiref
api_name:
- System.Data.SqlTypes.SqlStreamChars.IsNull
- System.Data.SqlTypes.SqlStreamChars.get_IsNull
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: ec00b0afa1597c3ae6488c12fe5a0667dad70e2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61675217"
---
# <a name="sqlstreamcharsisnull-property"></a>SqlStreamChars.IsNull 屬性

當在衍生類別中覆寫時，取得值，指出資料流是否`null`。 包含此屬性的組件有 SQLAccess.dll friend 關聯性。 它適用於 SQL server。 其他資料庫，請使用該資料庫所提供的主控機制。

## <a name="syntax"></a>語法

```csharp
public abstract bool IsNull { get; }
```

## <a name="property-value"></a>屬性值

<xref:System.Boolean>\
`true` 如果資料流`null`; 否則`false`。

## <a name="remarks"></a>備註

> [!WARNING]
> `SqlStreamChars.IsNull`屬性是 private，而且不適合直接在您的程式碼中使用。
>
> Microsoft 不支援在生產環境應用程式中任何情況下使用此欄位。

## <a name="requirements"></a>需求

**命名空間︰** <xref:System.Data.SqlTypes>

**組件：** System.Data （在 System.Data.dll 中)

**.NET framework 版本：** 自 2.0 起可用。