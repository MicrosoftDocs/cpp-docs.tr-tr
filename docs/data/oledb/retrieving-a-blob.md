---
title: BLOB alma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2d3c66fdb15a27b027be656ab07152e74d848526
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086908"
---
# <a name="retrieving-a-blob"></a>BLOB Alma

Çeşitli şekillerde ikili büyük nesne (BLOB) alabilir. Kullanabileceğiniz `DBTYPE_BYTES` bayt dizisi olarak BLOB alınamıyor veya bir arabirim `ISequentialStream`. Daha fazla bilgi için [BLOB'ları ve OLE nesneleri](/previous-versions/windows/desktop/ms711511\(v=vs.85\)) içinde *OLE DB Programcının Başvurusu*.  
  
Aşağıdaki kodu kullanarak bir BLOB alma işlemi gösterilmektedir `ISequentialStream`. Makro [BLOB_ENTRY](../../data/oledb/blob-entry.md) arabirimi ve arabirim için kullanılan bayraklar belirtmenizi sağlar. Tablo açtıktan sonra kodu çağıran `Read` üzerinde sürekli `ISequentialStream` BLOBUNDAN bayt okunamadı. Kod çağrıları `Release` çağırmadan önce arabirim işaretçisi elden çıkarmak `MoveNext` sonraki kayıt elde edilir.  
  
```cpp  
class CCategories  
{  
public:  
   ISequentialStream*   pPicture;  
  
BEGIN_COLUMN_MAP(CCategories)  
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CCategories>> categories;  
ULONG          cb;  
BYTE            myBuffer[65536];  
  
categories.Open(session, "Categories");  

while (categories.MoveNext() == S_OK)  
{  
   do  
   {  
      categories.pPicture->Read(myBuffer, 65536, &cb);  
      // Do something with the buffer  
   } while (cb > 0);  
   categories.pPicture->Release();  
}  
```  
  
BLOB verilerini işleme makrolar hakkında daha fazla bilgi için bkz: "Sütun eşleme makroları" [makroları ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)<br/>
[OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)