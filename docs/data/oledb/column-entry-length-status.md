---
title: COLUMN_ENTRY_LENGTH_STATUS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_LENGTH_STATUS
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_LENGTH_STATUS macro
ms.assetid: 6069967c-4665-462b-b822-1e6c22b5bee1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 90f05219da4382f759934e39c074bc6cb81817a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097815"
---
# <a name="columnentrylengthstatus"></a>COLUMN_ENTRY_LENGTH_STATUS
Satır kümesi bağlamada veritabanındaki belirli sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_LENGTH_STATUS(nOrdinal, data, length, status)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *uzunluğu*  
 [in] Sütun uzunluğu bağlanması için değişken.  
  
 *Durumu*  
 [in] Sütun durumuna bağlı olmasını değişkeni.  
  
## <a name="remarks"></a>Açıklamalar  
 Uzunluğu ve durumu değişkenlerini destekle istediğinizde bu makrosu kullanın. Aşağıdaki konumlarda kullanılır:  
  
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
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)