---
title: BLOB_NAME | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB_NAME
dev_langs:
- C++
helpviewer_keywords:
- BLOB_NAME macro
ms.assetid: 757acd0d-946d-447d-937e-94ecd700ba38
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b4d5d7bbad25c7b2921e7b379c1014f893216d3d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="blobname"></a>BLOB_NAME
İle kullanılan `BEGIN_COLUMN_MAP` ve `END_COLUMN_MAP` ikili büyük nesne bağlamak için ([BLOB](https://msdn.microsoft.com/en-us/library/ms711511.aspx)). Benzer şekilde [BLOB_ENTRY](../../data/oledb/blob-entry.md)dışında bu makrosu sütun numarası yerine sütun adını alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
BLOB_NAME(pszName, IID, flags, data )  
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
  
## <a name="example"></a>Örnek  
 Bkz: [nasıl ı alabilir BLOB?](../../data/oledb/retrieving-a-blob.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makrolar ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB_NAME_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB_NAME_LENGTH_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB_NAME_STATUS](../../data/oledb/blob-name-status.md)