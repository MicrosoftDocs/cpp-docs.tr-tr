---
title: BLOB_ENTRY_STATUS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB_ENTRY_STATUS
dev_langs:
- C++
helpviewer_keywords:
- BLOB_ENTRY_STATUS macro
ms.assetid: 191007f4-dfcc-4ae2-a7fc-6f7899accc9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 207f42094ea62db103fb39a0057f595182a2ec9a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="blobentrystatus"></a>BLOB_ENTRY_STATUS
İle kullanılan `BEGIN_COLUMN_MAP` veya `BEGIN_ACCESSOR_MAP` ikili büyük nesne bağlamak için ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Benzer şekilde [BLOB_ENTRY](../../data/oledb/blob-entry.md)dışında bu makrosu BLOB sütun durumunu da alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_ENTRY_STATUS(nOrdinal, IID, flags, data, status)  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nOrdinal`  
 [in] Sütun numarası.  
  
 *IID*  
 [in] GUID, gibi arabirim **IDD_ISequentialStream**, BLOB almak için kullanılan.  
  
 `flags`  
 [in] OLE yapılı depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, **STGM_READ**).  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *Durumu*  
 [out] BLOB alanı durumu.  
  
## <a name="example"></a>Örnek  
 Bkz: [nasıl ı alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_ENTRY](../../data/oledb/blob-entry.md)   
 [BLOB_ENTRY_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB_ENTRY_LENGTH_STATUS](../../data/oledb/blob-entry-length-status.md)