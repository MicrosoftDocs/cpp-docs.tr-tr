---
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
ms.openlocfilehash: 2c84ff359bdbb39f281928fa0135edd40b1f7d20
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446085"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Sihirbaz, satır kümesi nesnesi için bir giriş oluşturur. Bu durumda, `CCustomRowset`çağırılır. `CCustomRowset` sınıfı, satır kümesi nesnesi için gerekli tüm arabirimleri uygulayan `CRowsetImpl`adlı OLE DB sağlayıcı sınıfından devralır. Aşağıdaki kod `CRowsetImpl`devralma zincirini gösterir:

```cpp
template <class T, class Storage, class CreatorClass, 
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, 
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` Ayrıca `IAccessor` ve `IColumnsInfo` arabirimlerini kullanır. Tablolardaki çıktı alanları için bu arabirimleri kullanır. Sınıfı ayrıca, `IRowsetIdentity`için bir uygulama sağlar ve bu da tüketicinin iki satır aynı olup olmadığını belirlemesine izin verir. `IRowsetInfo` arabirimi satır kümesi nesnesinin özelliklerini uygular. `IConvertType` arabirimi, sağlayıcının tüketici tarafından istenen veri türleri arasındaki farkları ve sağlayıcı tarafından kullanılan farklılıkları çözümlemesine izin verir.

`IRowset` arabirimi aslında veri alımını işler. Tüketici, `HROW`olarak bilinen bir satıra tanıtıcı döndürmek için `GetNextRows` adlı bir yöntemi çağırır. Ardından tüketici, istenen verileri almak için bu `HROW` `IRowset::GetData` çağırır.

`CRowsetImpl` Ayrıca birkaç şablon parametresi alır. Bu parametreler `CRowsetImpl` sınıfının verileri nasıl işleyeceğini belirlemenizi sağlar. `ArrayType` bağımsız değişkeni, satır verilerini depolamak için kullanılan depolama mekanizmasını belirlemenizi sağlar. *RowClass* parametresi hangi sınıfın `HROW`içerdiğini belirtir.

*RowsetInterface* parametresi, `IRowsetLocate` veya `IRowsetScroll` arabirimini de kullanmanıza olanak sağlar. `IRowsetLocate` ve `IRowsetScroll` arabirimleri her ikisi de `IRowset`devralınır. Bu nedenle, OLE DB sağlayıcı şablonlarının bu arabirimler için özel işleme sağlaması gerekir. Bu arabirimlerden birini kullanmak istiyorsanız bu parametreyi kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
