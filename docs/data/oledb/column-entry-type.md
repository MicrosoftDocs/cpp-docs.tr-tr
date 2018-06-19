---
title: COLUMN_ENTRY_TYPE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_TYPE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_TYPE macro
ms.assetid: ac424261-ff6c-443b-a197-2cec8d78d738
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b297b641913c59c95cd54fdb4e5e02a293dbf71e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091550"
---
# <a name="columnentrytype"></a>COLUMN_ENTRY_TYPE
Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler `type` parametresi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_TYPE (nOrdinal, wType, data)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 `wType`  
 [in] Sütun giriş veri türü.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir özel bu makrosu çeşididir [COLUMN_ENTRY](../../data/oledb/column-entry.md) makrosu veri türünü belirten bir sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)