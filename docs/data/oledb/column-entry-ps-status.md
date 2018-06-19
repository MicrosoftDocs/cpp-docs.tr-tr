---
title: COLUMN_ENTRY_PS_STATUS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_PS_STATUS
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_PS_STATUS macro
ms.assetid: c02140c6-246f-4df5-8b86-698d7d137022
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f15c5865919c1b513107d2ef0cf400fa1cbdc262
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098088"
---
# <a name="columnentrypsstatus"></a>COLUMN_ENTRY_PS_STATUS
Satır kümesi bağlamada veritabanındaki belirli sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_PS_STATUS(nOrdinal, nPrecision, nScale, data, status)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 `nPrecision`  
 [in] Duyarlık üst sınırını bağlamak istediğiniz sütun.  
  
 `nScale`  
 [in] Ölçeğin bağlamak istediğiniz sütun.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı olmasını değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 Kesinlik ve ölçek bağlamak istediğiniz sütunun belirtmenize olanak tanır. Bu makrosu destekleyen *durum* değişkeni. Aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)