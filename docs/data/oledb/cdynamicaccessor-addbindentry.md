---
title: CDynamicAccessor::AddBindEntry | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CDynamicAccessor::AddBindEntry
- AddBindEntry
- CDynamicAccessor.AddBindEntry
- CDynamicAccessor::AddBindEntry
- ATL.CDynamicAccessor.AddBindEntry
dev_langs:
- C++
helpviewer_keywords:
- AddBindEntry method
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b49af256ea5f2f4fcc87474019c184e4c5babc58
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096018"
---
# <a name="cdynamicaccessoraddbindentry"></a>CDynamicAccessor::AddBindEntry
Çıkış sütunlarında bir BIND girdisi ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT AddBindEntry(const DBCOLUMNINFO& info) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `info`  
 [in] A **DBCOLUMNINFO** sütun bilgileri içeren yapısı. "DBCOLUMNINFO yapıları" bölümüne bakın [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart birini `HRESULT` değerleri.  
  
## <a name="remarks"></a>Açıklamalar  
 İle oluşturulan varsayılan erişimciyi geçersiz kılma bu yöntemi kullanın `CDynamicAccessor` (bkz [nasıl yedeklerim Fetch Data?](../../data/oledb/fetching-data.md)).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor Sınıfı](../../data/oledb/cdynamicaccessor-class.md)