---
title: COLUMN_ENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_ENTRY
dev_langs: C++
helpviewer_keywords: COLUMN_ENTRY macro
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f509ebc6e3e8a050d6b3bd5fb18b999024ec8af1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="columnentry"></a>COLUMN_ENTRY
Satır kümesi bağlamada satır kümesindeki belirli sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
COLUMN_ENTRY(  
nOrdinal  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IAccessor::CreateAccessor'ı](https://msdn.microsoft.com/en-us/library/ms716845.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
## <a name="remarks"></a>Açıklamalar  
 `COLUMN_ENTRY` Makrosu aşağıdaki konumlarda kullanılır:  
  
-   Arasında [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [END_COLUMN_MAP](../../data/oledb/end-column-map.md) makroları.  
  
-   Arasında [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) ve [END_ACCESSOR](../../data/oledb/end-accessor.md) makroları.  
  
-   Arasında [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) ve [END_PARAM_MAP](../../data/oledb/end-param-map.md) makroları.  
  
## <a name="example"></a>Örnek  
 Makro konularda örneklere bakın [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) ve [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN_ENTRY_PS_STATUS](../../data/oledb/column-entry-ps-status.md)   
 [COLUMN_ENTRY_TYPE](../../data/oledb/column-entry-type.md)   
 [COLUMN_ENTRY_TYPE_SIZE](../../data/oledb/column-entry-type-size.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)