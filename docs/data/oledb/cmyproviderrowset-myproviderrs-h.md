---
title: CCustomRowset (CustomRS.H) | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- cmyproviderrowset
- myproviderrs.h
- ccustomrowset
- customrs.h
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
- CMyProviderRowset class in MyProviderRS.H
- CCustomRowset class in CustomRS.H
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 211c83ec63611c493f03e48b58619caca373ce65
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216363"
---
# <a name="ccustomrowset-customrsh"></a>CCustomRowset (CustomRS.H)

Sihirbaz, bir giriş satır kümesi nesnesi oluşturur. Bu durumda, adlı `CCustomRowset`. `CCustomRowset` Sınıfı olarak adlandırılan bir OLE DB sağlayıcısı sınıfından devralan `CRowsetImpl`, satır kümesi nesnesi için tüm gerekli arabirimleri uygular. Aşağıdaki kod için devralma zincirini göstermektedir `CRowsetImpl`:

```cpp
template <class T, class Storage, class CreatorClass, 
   class ArrayType = CAtlArray<Storage>>
class CMyRowsetImpl:
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType, 
      CSimpleRow, IRowsetLocateImpl< T >>
```

`CRowsetImpl` Ayrıca kullanan `IAccessor` ve `IColumnsInfo` arabirimleri. Bu arabirimler, tablolardaki çıktı alanları için kullanır. Sınıfı için bir uygulama sağlar `IRowsetIdentity`, iki satır aynı olup olmadığını belirlemek tüketici sağlar. `IRowsetInfo` Arabirimi uygulayan satır kümesi nesnesi için özellikler. `IConvertType` Tüketici tarafından istenen veri türleri ve sağlayıcı tarafından kullanılan arasındaki farklılıkları çözmeye sağlayıcı arabirimi sağlar.

`IRowset` Arabirimi aslında veri almayı da işler. Tüketici ilk adlı bir yöntemi çağıran `GetNextRows` olarak bilinen, bir satır için bir tanıtıcı döndürülecek bir `HROW`. Daha sonra tüketici çağırır `IRowset::GetData` , ile `HROW` istenen verileri almak için.

`CRowsetImpl` Ayrıca birkaç şablon parametresi alır. Bu parametreleri belirlemenizi sağlar nasıl `CRowsetImpl` sınıf verilerini işler. `ArrayType` Bağımsız değişkeni hangi depolama mekanizmasını satır verileri depolamak için kullanılan belirlemenize olanak verir. *RowClass* parametresinin belirttiği hangi sınıfı içeren bir `HROW`.

*RowsetInterface* parametresi de kullanmanıza olanak verir `IRowsetLocate` veya `IRowsetScroll` arabirimi. `IRowsetLocate` Ve `IRowsetScroll` arabirimleri hem de devralan `IRowset`. Bu nedenle, OLE DB sağlayıcı şablonları özel işleme için bu arabirimler sağlamanız gerekir. Bu arabirimler birini kullanmak istiyorsanız, bu parametreyi kullanmanız gerekir.

## <a name="see-also"></a>Ayrıca Bkz.

[Sağlayıcı Sihirbazı Tarafından Üretilen Dosyalar](../../data/oledb/provider-wizard-generated-files.md)<br/>
