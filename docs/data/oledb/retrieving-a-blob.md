---
title: BLOB alma | Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 1608bf5db491a090f70da5242173fc96419a6179
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070172"
---
# <a name="retrieving-a-blob"></a>BLOB Alma

Çeşitli şekillerde ikili büyük nesne (BLOB) alabilir. Kullanabileceğiniz `DBTYPE_BYTES` bayt dizisi olarak BLOB alınamıyor veya bir arabirim `ISequentialStream`. Daha fazla bilgi için [BLOB'ları ve OLE nesneleri](/previous-versions/windows/desktop/ms711511) içinde **OLE DB Programcının Başvurusu**.

Aşağıdaki kodu kullanarak bir BLOB alma işlemi gösterilmektedir `ISequentialStream`. Makro [BLOB_ENTRY](../../data/oledb/blob-entry.md) arabirimi ve arabirim için kullanılan bayraklar belirtmenizi sağlar. Tablo açtıktan sonra kodu çağıran `Read` üzerinde sürekli `ISequentialStream` BLOBUNDAN bayt okunamadı. Kod çağrıları `Release` çağırmadan önce arabirim işaretçisi elden çıkarmak `MoveNext` sonraki kayda alınamıyor.

```cpp
class CCategories
{
public:
   ISequentialStream* pPicture;

BEGIN_COLUMN_MAP(CCategories)
   BLOB_ENTRY(4, IID_ISequentialStream, STGM_READ, pPicture)
END_COLUMN_MAP()
};
```

Ardından, aşağıdaki kod tarafından kullanılır:

```cpp
CTable<CAccessor<CCategories>> categories;
ULONG cb;
BYTE myBuffer[65536];

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

BLOB verilerini işleme makrolar hakkında daha fazla bilgi için bkz. **sütun eşleme makroları** içinde [makroları ve genel işlevler için OLE DB Tüketici Şablonları](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)<br/>
[OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
