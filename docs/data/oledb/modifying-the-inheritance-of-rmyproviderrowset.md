---
title: RCustomRowset devralmayı değiştirme
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: 34eb07611ebfff09918d62273d4ca4a8c9cf4f7b
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265158"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset devralmayı değiştirme

Eklenecek `IRowsetLocate` arabirim basit bir salt okunur sağlayıcı örneği, devralınmasını Değiştir `CCustomRowset`. Başlangıçta `CCustomRowset` devraldığı `CRowsetImpl`. Devralınacak şekilde değiştirmeniz gerekir `CRowsetBaseImpl`.

Bunu yapmak için yeni bir sınıf oluşturun `CCustomRowsetImpl`, *özel*RS.h:

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

Son olarak, bağlantı `CCustomRowset` için `CMyRowsetBaseImpl` değiştirerek `CCustomRowset` devralınacak `CMyRowsetImpl`gibi:

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` artık `IRowsetLocate` yararlanırken satır kümesi sınıfı için uygulama rest arabirimi.

Bu yapıldığında, yapabilecekleriniz [Tüketiciye döndürülecek olan sütunları dinamik olarak belirleyen](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Basit Salt Okunur Sağlayıcıyı Geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
