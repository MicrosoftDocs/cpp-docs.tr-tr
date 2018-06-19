---
title: COLUMN_ENTRY_TYPE_SIZE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- COLUMN_ENTRY_TYPE_SIZE
dev_langs:
- C++
helpviewer_keywords:
- COLUMN_ENTRY_TYPE_SIZE macro
ms.assetid: d8b169e8-af22-464b-8cb3-eaa346f7a739
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1acb969015acda4213532cac3e185bf97a3ac31d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33097178"
---
# <a name="columnentrytypesize"></a>COLUMN_ENTRY_TYPE_SIZE
Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler `type` ve `size` parametreleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
COLUMN_ENTRY_TYPE_SIZE(nOrdinal, wType, nLength, data)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 `wType`  
 [in] Sütun giriş veri türü.  
  
 `nLength`  
 [in] Sütun giriş bayt cinsinden boyutu.  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir özel bu makrosu çeşididir [COLUMN_ENTRY](../../data/oledb/column-entry.md) makrosu veri boyutunu ve türünü belirten bir sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)