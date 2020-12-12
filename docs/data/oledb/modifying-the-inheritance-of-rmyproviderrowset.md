---
description: 'Hakkında daha fazla bilgi edinin: RCustomRowset devralmayı değiştirme'
title: RCustomRowset devralınmasını değiştirme
ms.date: 10/26/2018
helpviewer_keywords:
- RMyProviderRowset
- inheritance [C++]
- RCustomRowset
ms.assetid: 33089c90-98a4-43e7-8e67-d4bb137e267e
ms.openlocfilehash: c54533122083c526ad12ac6514efa3ad9ba47cf5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287014"
---
# <a name="modifying-the-inheritance-of-rcustomrowset"></a>RCustomRowset devralınmasını değiştirme

`IRowsetLocate`Arabirimi basit salt okuma sağlayıcı örneğine eklemek için, devralınmasını değiştirin `CCustomRowset` . Başlangıçta, `CCustomRowset` öğesinden devralır `CRowsetImpl` . Öğesini öğesinden devralacak şekilde değiştirmeniz gerekir `CRowsetBaseImpl` .

Bunu yapmak için, `CCustomRowsetImpl` *özel* RS. h içinde yeni bir sınıf oluşturun:

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

Şimdi, *özel* RS. h 'de com arabirimi haritasını aşağıdaki gibi düzenleyin:

```cpp
BEGIN_COM_MAP(CMyRowsetImpl)
   COM_INTERFACE_ENTRY(IRowsetLocate)
   COM_INTERFACE_ENTRY_CHAIN(_RowsetBaseClass)
END_COM_MAP()
```

Bu kod `CMyRowsetImpl` `QueryInterface` , ve arabirimlerini çağırmak IÇIN bir com arabirimi haritası oluşturur `IRowset` `IRowsetLocate` . Diğer satır kümesi sınıflarının tüm uygulanmasını sağlamak için, eşleme, `CMyRowsetImpl` sınıfı `CRowsetBaseImpl` OLE DB Şablonları tarafından tanımlanan sınıfa geri bağlar; map, OLE DB şablonlarına `CRowsetBaseImpl` bir çağrıya yanıt olarak içinde com haritasını taramasını bildiren COM_INTERFACE_ENTRY_CHAIN makrosunu kullanır `QueryInterface` .

Son olarak, `CCustomRowset` `CMyRowsetBaseImpl` `CCustomRowset` aşağıdaki gibi, öğesinden devralacak şekilde değiştirerek bağlantısını yapın `CMyRowsetImpl` :

```cpp
class CCustomRowset : public CMyRowsetImpl<CCustomRowset, CCustomWindowsFile, CCustomCommand>
```

`CCustomRowset` Artık, `IRowsetLocate` satır kümesi sınıfı için uygulamanın geri kalanının avantajlarından yararlanarak arabirimi kullanabilir.

Bu tamamlandığında, [tüketiciye döndürülen sütunları dinamik olarak belirleyebilirsiniz](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md).

## <a name="see-also"></a>Ayrıca bkz.

[Basit Read-Only sağlayıcıyı geliştirme](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
