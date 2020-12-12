---
description: 'Daha fazla bilgi edinin: BLOB alma'
title: BLOB Alma
ms.date: 10/24/2018
helpviewer_keywords:
- retrieving BLOBs
- BLOB (binary large object), retrieving
- OLE DB, BLOBs (binary large objects)
ms.assetid: 2893eb0a-5c05-4016-8914-1e40ccbaf0b3
ms.openlocfilehash: ef870d84c286f72621e87858cea944cc70cbe0cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286611"
---
# <a name="retrieving-a-blob"></a>BLOB Alma

İkili büyük nesne (BLOB) çeşitli yollarla alabilirsiniz. `DBTYPE_BYTES`Blobu bir bayt dizisi olarak almak veya gibi bir arayüz kullanmak için kullanabilirsiniz `ISequentialStream` . Daha fazla bilgi için, **OLE DB Programcı başvurusunda** [BLOB ve OLE nesneleri](/previous-versions/windows/desktop/ms711511(v=vs.85)) bölümüne bakın.

Aşağıdaki kod kullanarak bir BLOBUN nasıl alınacağını gösterir `ISequentialStream` . Makro [BLOB_ENTRY](./macros-and-global-functions-for-ole-db-consumer-templates.md#blob_entry) arabirim için kullanılan arabirimi ve bayrakları belirtmenize olanak tanır. Tabloyu açtıktan sonra kod, `Read` `ISequentialStream` BLOB 'dan baytları okumak için tekrar tekrar çağırır. Kod, `Release` `MoveNext` sonraki kaydı almak için çağrılmadan önce arabirim işaretçisinin atılmaya çağrı yapılır.

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

BLOB verilerini işleyen makrolar hakkında daha fazla bilgi için bkz. [OLE DB tüketici şablonları Için makrolar ve genel Işlevlerde](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md) **sütun Haritası makroları** .

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)<br/>
[OLE DB tüketici şablonları için makrolar ve genel Işlevler](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)<br/>
