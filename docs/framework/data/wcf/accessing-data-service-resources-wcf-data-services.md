---
title: 存取資料服務資源 (WCF 資料服務)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, querying
- getting started, WCF Data Services
- querying the data service [WCF Data Service]
- WCF Data Services, getting started
- WCF Data Services, accessing data
ms.assetid: 9665ff5b-3e3a-495d-bf83-d531d5d060ed
ms.openlocfilehash: 6d4b0af7f20cbf932773df3ae226729a0a6c2500
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793571"
---
# <a name="accessing-data-service-resources-wcf-data-services"></a>存取資料服務資源 (WCF 資料服務)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 支援[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]將資料公開為可由 Uri 定址的資源摘要。 會根據實體-關聯性慣例呈現這些資源[Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)。 在此模型中，實體代表資料運算單位 (這些資料在應用程式定義域中為資料型別)，例如客戶、訂單、項目及產品。 使用具像狀態傳輸 (REST) 的語意即可存取及變更實體資料，尤其是標準 HTTP 動作，例如 GET、PUT、POST 和 DELETE。  
  
## <a name="addressing-resources"></a>設定資源存取位址  
 在 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 中，您會使用 URI 來定址資料模型所公開的任何資料。 例如，下列 URI 會傳回一個摘要，Customer 實體集，其中包含 Customer 實體類型的所有執行個體的項目：  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers  
```  
  
 實體還包含稱為實體索引鍵的特殊屬性。 實體索引鍵用於以唯一方式識別實體集中的單一實體。 這樣可以讓您定址實體集中某個實體型別的特殊執行個體。 例如，下列 URI 會傳回 Customer 實體類型之特定執行個體的項目，此執行個體的索引鍵值為 `ALFKI`：  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')  
```  
  
 您也可以個別定址實體執行個體的基本和複雜屬性。 例如，下列 URI 會傳回 XML 項目，其中包含特定 Customer 的 `ContactName` 屬性值：  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName  
```  
  
 當您在之前的 URI 中包含 `$value` 端點時，回應訊息中只會傳回基本屬性的值。 下列範例只會傳回 "Maria Anders" 字串而沒有 XML 項目：  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/ContactName/$value  
```  
  
 資料模型中會以關聯性定義實體之間的關係。 這些關聯可讓您定址相關實體，其方式是使用實體執行個體的導覽屬性。 導覽屬性可在多對一關聯性中傳回單一相關實體，或是在一對多關聯性中傳回一組相關實體。 例如，下列 URI 會傳回一個摘要，它是與特定 Customer 相關之所有 Order 的集合：  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders  
```  
  
 關聯性 (通常是雙向關聯性) 是由一對導覽屬性來表示。 下列 URI 會傳回特定 Order 實體所屬之 Customer 實體的參考，與之前範例所示的關聯性相反：  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/Customer  
```  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 也可讓您根據查詢運算式的結果定址資源。 這讓您能夠篩選評估的運算式為基礎的資源集。 例如，下列 URI 會篩選資源，只傳回自 1997 年 9 月 22 日後配送且屬於指定 Customer 的 Orders。  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=ShippedDate gt datetime'1997-09-22T00:00:00'  
```  
  
 如需詳細資訊，請參閱[OData:URI 慣例](https://go.microsoft.com/fwlink/?LinkId=185564)。  
  
## <a name="system-query-options"></a>系統查詢選項  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 定義一組系統查詢選項可供您執行傳統查詢運算資源，例如篩選、 排序和分頁。 例如，下列 URI 會傳回的所有集合`Order`實體以及相關`Order_Detail`實體，其中的郵遞區號結尾不`100`:  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')&$expand=Order_Details&$orderby=ShipCity  
```  
  
 傳回之摘要中的項目也會依據訂單之 ShipCity 屬性的值來排序。  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 支援下列[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]系統查詢選項：  
  
|查詢選項|描述|  
|------------------|-----------------|  
|`$orderby`|在傳回的摘要中定義實體的預設排序次序。 下列查詢會依據縣市和城市來排序傳回的客戶摘要：<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$orderby=Country,City`<br /><br /> 如需詳細資訊，請參閱[OData:OrderBy 系統查詢選項 ($orderby)](https://go.microsoft.com/fwlink/?LinkId=186968)。|  
|`$top`|指定要併入傳回之摘要中的實體數。 下列範例會略過前 10 名客戶，然後傳回接下來的 10 名：<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> 如需詳細資訊，請參閱[OData:Top 系統查詢選項 ($top)](https://go.microsoft.com/fwlink/?LinkId=186969)。|  
|`$skip`|指定開始傳回摘要中的實體之前所要略過的實體數。 下列範例會略過前 10 名客戶，然後傳回接下來的 10 名：<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$skip=10&$top=10`<br /><br /> 如需詳細資訊，請參閱[OData:Skip 系統查詢選項 ($skip)](https://go.microsoft.com/fwlink/?LinkId=186971)。|  
|`$filter`|定義運算式，根據特定準則來篩選摘要中傳回的實體。 這個查詢選項可支援一組邏輯比較運算子、算術運算子及預先定義的查詢函數，這些是用來評估篩選運算式。 下列範例會傳回郵遞區號不是以 100 結尾的所有訂單：<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Orders?$filter=not endswith(ShipPostalCode,'100')`<br /><br /> 如需詳細資訊，請參閱[OData:篩選系統查詢選項 ($filter)](https://go.microsoft.com/fwlink/?LinkId=186972)。|  
|`$expand`|指定查詢傳回哪些相關實體。 相關實體會當做摘要或是內嵌項目 (連同查詢傳回的實體) 併入。 下列範例會傳回客戶 'ALFKI' 的訂單，連同每一份訂單的項目詳細資料：<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$expand=Order_Details`<br /><br /> 如需詳細資訊，請參閱[OData:Expand 系統查詢選項 ($expand)](https://go.microsoft.com/fwlink/?LinkId=186973)。|  
|`$select`|指定投射，可定義要在投射中傳回之實體的屬性。 依預設，實體的所有屬性都會在摘要中傳回。 下列查詢只會傳回 `Customer` 實體的三個屬性：<br /><br /> `http://services.odata.org/Northwind/Northwind.svc/Customers?$select=CustomerID,CompanyName,City`<br /><br /> 如需詳細資訊，請參閱[OData:選取系統查詢選項 ($select)](https://go.microsoft.com/fwlink/?LinkID=186076)。|  
|`$inlinecount`|要求摘要中傳回的實體計數應該要隨附在摘要中。 如需詳細資訊，請參閱[OData:Inlinecount 系統查詢選項 ($inlinecount)](https://go.microsoft.com/fwlink/?LinkId=186975)。|  
  
## <a name="addressing-relationships"></a>定址關聯性  
 除了定址實體集和實體執行個體，[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]也可讓您定址表示實體之間的關聯性的關聯。 必須具備此功能，您才能夠建立或變更兩個實體執行個體之間的關聯性，例如，在 Northwind 範例資料庫中的承運者與指定訂單相關。 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 支援`$link`運算子特別定址實體之間的關聯。 例如，在 HTTP PUT 要求訊息中，指定以下 URI 將特定訂單的承運者變更為新承運者。  
  
```  
http://services.odata.org/Northwind/Northwind.svc/Orders(10643)/$links/Shipper  
```  
  
 如需詳細資訊，請參閱[OData:定址的項目之間的連結](https://go.microsoft.com/fwlink/?LinkId=187351)。  
  
## <a name="consuming-the-returned-feed"></a>取用傳回的摘要  
 URI[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]資源可讓您定址服務所公開的實體資料。 當您的網頁瀏覽器的網址欄位中輸入 URI[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]傳回要求之資源的摘要表示法。 如需詳細資訊，請參閱 < [WCF Data Services 快速入門](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。 雖然 Web 瀏覽器可能適用於測試資料服務資源傳回預期的資料，可以也建立、 更新和刪除資料的實際執行資料服務通常會存取應用程式程式碼或指令碼語言，在網頁中的。 如需詳細資訊，請參閱 <<c0> [ 用戶端應用程式中使用的資料服務](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)。  
  
## <a name="see-also"></a>另請參閱

- [開放式資料通訊協定網站](https://go.microsoft.com/fwlink/?LinkID=182204)
