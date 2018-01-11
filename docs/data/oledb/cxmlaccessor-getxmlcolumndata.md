---
title: CXMLAccessor::GetXMLColumnData | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CXMLAccessor.GetXMLColumnData
- CXMLAccessor::GetXMLColumnData
- CXMLAccessor.GetXMLColumnData
- ATL::CXMLAccessor::GetXMLColumnData
- GetXMLColumnData
dev_langs: C++
helpviewer_keywords: GetXMLColumnData method
ms.assetid: 719e8efe-8758-4af7-a855-0e44ea196546
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9183521d8c627d2d4befb33aa171a1651451ea12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cxmlaccessorgetxmlcolumndata"></a>CXMLAccessor::GetXMLColumnData
Tablodaki sütun türü bilgisini XML biçimli dize verisi olarak sütuna göre alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetXMLColumnData(   
   CSimpleStringW& strOutput    
) throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `strOutput`  
 [out] Alınacak sütun türü bilgileri içeren bir dize arabellek referansı. Veri deposunun sütun adları eşleşen XML etiket adları ile biçimlendirilmiş bir dize.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdaki sütun türü bilgilerini XML biçiminde nasıl biçimlendirilmiş gösterir. `type`sütunun veri türünü belirtir. Veri türleri OLE DB veri türlerinde, erişilen veritabanı bu dayalı unutmayın.  
  
 `<columninfo>`  
  
 `<column type = I2/> ColumnName`  
  
 `</columninfo>`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CXMLAccessor Sınıfı](../../data/oledb/cxmlaccessor-class.md)