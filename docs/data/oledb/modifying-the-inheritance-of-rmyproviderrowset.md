---
title: RCustomRowset devralmayı değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 10/26/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 13e15b470be6f6a5af4f8012e3a70896f648e665
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216519"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset devralmayı değiştirme

Eklenecek `IRowsetLocate` arabirim basit bir salt okunur sağlayıcı örneği, devralınmasını Değiştir `RCustomRowset`. Başlangıçta `RCustomRowset` devraldığı `CRowsetImpl`. Devralınacak şekilde değiştirmeniz gerekir `CRowsetBaseImpl`.

Bunu yapmak için yeni bir sınıf oluşturun `CCustomRowsetImpl`, CustomRS.h içinde:

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.h

template <class T, class Storage, class CreatorClass, class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, CSimpleRow, IRowsetLocateImpl< T, IRowsetLocate >>
{
...
};
```

Şimdi, COM arabirim eşlemesini düzenle *özel*RS.h şu şekilde olacak:

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Bu kod söyleyen bir COM arabirim eşlemesi oluşturur `CMyRowsetImpl` çağrılacak `QueryInterface` hem `IRowset` ve `IRowsetLocate` arabirimleri. Tüm diğer satır kümesi uygulamasını almak için sınıflar, eşleme bağlantıları `CMyRowsetImpl` sınıfı yeniden `CRowsetBaseImpl` sınıfı OLE DB Şablonları tarafından tanımlı; içindeki COM eşlemesine taramak için OLE DB Şablonları söyler COM_INTERFACE_ENTRY_CHAIN makro eşlemesini kullanır `CRowsetBaseImpl` yanıt olarak bir `QueryInterface` çağırın.

Son olarak, bağlantı `RAgentRowset` için `CMyRowsetBaseImpl` değiştirerek `RAgentRowset` devralınacak `CMyRowsetImpl`gibi:

```cpp
class RAgentRowset : public CMyRowsetImpl<RAgentRowset, CAgentMan, CCustomCommand>
```

`RAgentRowset` artık `IRowsetLocate` yararlanırken satır kümesi sınıfı için uygulama rest arabirimi.

Bu yapıldığında, yapabilecekleriniz [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
