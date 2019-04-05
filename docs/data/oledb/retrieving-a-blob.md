---
title: BLOB Alma
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: 23bc20355e1e2b17ac20cf975df2ff58d6553ef9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023093"
---
# <a name="retrieving-a-blob"></a>BLOB Alma

Çeşitli şekillerde ikili büyük nesne (BLOB) alabilir. Kullanabileceğiniz `DBTYPE_BYTES` bayt dizisi olarak BLOB alınamıyor veya bir arabirim `ISequentialStream`. Daha fazla bilgi için [BLOB'ları ve OLE nesneleri](/previous-versions/windows/desktop/ms711511(v=vs.85)) içinde **OLE DB Programcının Başvurusu**.

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

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)<br/>
[OLE DB Tüketici Şablonları için Makrolar ve Genel İşlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
