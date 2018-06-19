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
ms.openlocfilehash: 420e863fcd5d4c666bf8e9a25a2f0f53e726c871
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105211"
---
# <a name="retrieving-a-blob"></a>BLOB Alma
Çeşitli şekillerde ikili büyük nesne (BLOB) alabilir. Kullanabileceğiniz **DBTYPE_BYTES** bayt dizisi olarak BLOB almak veya gibi bir arabirim kullanmak için `ISequentialStream`. Daha fazla bilgi için bkz: [BLOBLARI ve OLE nesneleri](https://msdn.microsoft.com/en-us/library/ms711511.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Aşağıdaki kod kullanarak bir BLOB alma gösterir `ISequentialStream`. Makro [BLOB_ENTRY](../../data/oledb/blob-entry.md) arabirimi ve arabirim için kullanılan bayraklarını belirtmenize olanak tanır. Tablo açıldıktan sonra kod çağırır **okuma** üzerinde sürekli `ISequentialStream` BLOBUNDAN bayt okunamıyor. Kod çağrıları **sürüm** çağırmadan önce arabirimi işaretçisinin silmek için `MoveNext` sonraki kaydı elde edilir.  
  
```  
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
  
 BLOB verilerini işleyen makrolar hakkında daha fazla bilgi için bkz: "Sütun eşleme makroları" [makrolar ve genel işlevler OLE DB Tüketici Şablonları için](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri kullanma](../../data/oledb/using-accessors.md)   
 [OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)