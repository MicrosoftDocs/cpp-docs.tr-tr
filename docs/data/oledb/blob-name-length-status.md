---
title: BLOB_NAME_LENGTH_STATUS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- BLOB_NAME_LENGTH_STATUS
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME_LENGTH_STATUS macro
ms.assetid: 3cc3ec8d-80a5-4522-848a-123fcaee58cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c819ecf270f7aee16f05b8e86bbacf01d658d22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093483"
---
# <a name="blobnamelengthstatus"></a>BLOB_NAME_LENGTH_STATUS
İle kullanılan `BEGIN_COLUMN_MAP` ve `END_COLUMN_MAP` ikili büyük nesne bağlamak için ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Benzer şekilde [BLOB_NAME](../../data/oledb/blob-name.md)dışında bu makrosu uzunluğu ve BLOB veri sütunu durumunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME_LENGTH_STATUS(pszName, IID, flags, data, length  
, status )  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszName`  
 [in] Sütun adı için bir işaretçi. Adın bir UNICODE dizesi olması gerekir. Bu örneğin adı önüne bir 'L' koyarak gerçekleştirmek: `L"MyColumn"`.  
  
 *IID*  
 [in] GUID, gibi arabirim **IDD_ISequentialStream**, BLOB almak için kullanılan.  
  
 `flags`  
 [in] OLE yapılı depolama modeli tarafından tanımlanan depolama modu bayrakları (örneğin, **STGM_READ**).  
  
 `data`  
 [in] Kullanıcı kaydındaki karşılık gelen veri üyesi.  
  
 *uzunluğu*  
 [out] Bayt BLOB sütunun (gerçek) uzunluğu.  
  
 *Durumu*  
 [out] BLOB alanı durumu.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME](../../data/oledb/blob-name.md)   
 [BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)