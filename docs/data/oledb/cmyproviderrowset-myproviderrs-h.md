---
description: 'Daha fazla bilgi edinin: CCustomRowset (CustomRS. H)'
title: CCustomRowset (CustomRS.H)
ms.date: 10/22/2018
f1_keywords:
- cmyproviderrowset
- ccustomrowset
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
ms.openlocfilehash: 87025be2a34f8c850bde2be53ab01519968654d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170470"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Sihirbaz, satır kümesi nesnesi için bir giriş oluşturur. Bu durumda, çağırılır `CCustomRowset` . `CCustomRowset`Sınıfı `CRowsetImpl` , satır kümesi nesnesi için gerekli tüm arabirimleri uygulayan adlı bir OLE DB sağlayıcı sınıfından devralır. Aşağıdaki kod, için devralma zincirini göstermektedir `CRowsetImpl` :

```cpp
template <class T, class Storage, class CreatorClass,
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` Ayrıca `IAccessor` ve arabirimlerini kullanır `IColumnsInfo` . Tablolardaki çıktı alanları için bu arabirimleri kullanır. Sınıfı, için bir uygulama sağlar `IRowsetIdentity` ve bu da tüketicinin iki satır aynı olup olmadığını belirlemesine olanak sağlar. `IRowsetInfo`Arabirim, satır kümesi nesnesi için özellikler uygular. `IConvertType`Arabirim, sağlayıcının tüketici tarafından istenen veri türleri arasındaki farkları ve sağlayıcı tarafından kullanılan farklılıkları çözümlemesine izin verir.

`IRowset`Arabirim aslında veri alımı işler. Tüketici, `GetNextRows` olarak bilinen bir satıra tanıtıcı döndürmek için çağrılan bir yöntemi çağırır `HROW` . Ardından tüketici, `IRowset::GetData` `HROW` istenen verileri almak için ile çağırır.

`CRowsetImpl` Ayrıca birkaç şablon parametresi alır. Bu parametreler, `CRowsetImpl` sınıfının verileri nasıl işleyeceğini belirlemenizi sağlar. `ArrayType`Bağımsız değişkeni, satır verilerini depolamak için kullanılan depolama mekanizmasını belirlemenizi sağlar. *RowClass* parametresi hangi sınıfın içerdiğini belirtir `HROW` .

*RowsetInterface* parametresi, veya arabirimini de kullanmanıza olanak sağlar `IRowsetLocate` `IRowsetScroll` . `IRowsetLocate`Ve `IRowsetScroll` arabirimlerinin her ikisi de öğesinden devralınır `IRowset` . Bu nedenle, OLE DB sağlayıcı şablonlarının bu arabirimler için özel işleme sağlaması gerekir. Bu arabirimlerden birini kullanmak istiyorsanız bu parametreyi kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Wizard-Generated dosyaları](../../data/oledb/provider-wizard-generated-files.md)<br/>
