---
title: COLUMN_ENTRY_TYPE_SIZE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_ENTRY_TYPE_SIZE
dev_langs: C++
helpviewer_keywords: COLUMN_ENTRY_TYPE_SIZE macro
ms.assetid: d8b169e8-af22-464b-8cb3-eaa346f7a739
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1b70b4652ad89bcb8382e060740c8c627f7efb60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="columnentrytypesize"></a>COLUMN_ENTRY_TYPE_SIZE
Veritabanındaki belirli sütunu için bir bağlama temsil eder. Destekler `type` ve `size` parametreleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
COLUMN_ENTRY_TYPE_SIZE(  
nOrdinal  
,   
wType  
,   
nLength  
,   
data  
 )  
  
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