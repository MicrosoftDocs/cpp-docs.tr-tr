---
title: BLOB_NAME_LENGTH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB_NAME_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME_LENGTH macro
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 38b6a2c048461521bfd4b7a1881e3410e80e7bac
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="blobnamelength"></a>BLOB_NAME_LENGTH
İle kullanılan `BEGIN_COLUMN_MAP` ve `END_COLUMN_MAP` ikili büyük nesne bağlamak için ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Benzer şekilde [BLOB_NAME](../../data/oledb/blob-name.md)dışında bu makrosu de BLOB veri sütunu bayt cinsinden uzunluğu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME_LENGTH(pszName, IID, flags, data, length )  
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
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME](../../data/oledb/blob-name.md)   
 [BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)