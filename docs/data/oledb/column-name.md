---
title: COLUMN_NAME | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_NAME
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_NAME macro
ms.assetid: a213b9a0-2148-4a08-9111-d9fa8fdec462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f60acfac21e003f6a548c5702ebb975a458a93cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097529"
---
# <a name="columnname"></a>COLUMN_NAME
Satır kümesi bağlamada satır kümesindeki belirli sütunu temsil eder. Benzer şekilde [COLUMN_ENTRY](../../data/oledb/column-entry.md)dışında bu makrosu sütun numarası yerine sütun adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_NAME(pszName, data)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszName`  
 [in] Sütun adı için bir işaretçi. Adın bir UNICODE dizesi olması gerekir. Bu örneğin adı önüne bir 'L' koyarak gerçekleştirmek: `L"MyColumn"`.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
## <a name="remarks"></a>Açıklamalar  
 **COLUMN_NAME_\***  makroları aynı yerde kullanılan [COLUMN_ENTRY](../../data/oledb/column-entry.md):  
  
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
 [COLUMN_NAME_EX](../../data/oledb/column-name-ex.md)   
 [COLUMN_NAME_LENGTH](../../data/oledb/column-name-length.md)   
 [COLUMN_NAME_LENGTH_STATUS](../../data/oledb/column-name-length-status.md)   
 [COLUMN_NAME_STATUS](../../data/oledb/column-name-status.md)   
 [COLUMN_NAME_PS](../../data/oledb/column-name-ps.md)   
 [COLUMN_NAME_PS_LENGTH](../../data/oledb/column-name-ps-length.md)   
 [COLUMN_NAME_PS_STATUS](../../data/oledb/column-name-ps-status.md)   
 [COLUMN_NAME_PS_LENGTH_STATUS](../../data/oledb/column-name-ps-length-status.md)   
 [COLUMN_NAME_TYPE](../../data/oledb/column-name-type.md)   
 [COLUMN_NAME_TYPE_PS](../../data/oledb/column-name-type-ps.md)   
 [COLUMN_NAME_TYPE_SIZE](../../data/oledb/column-name-type-size.md)   
 [COLUMN_NAME_TYPE_STATUS](../../data/oledb/column-name-type-status.md)