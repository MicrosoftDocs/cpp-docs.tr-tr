---
description: 'Daha fazla bilgi edinin: CNoAccessor sınıfı'
title: CNoAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: 624c72c841280ec56bacf0edd29efeb4b1005988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170392"
---
# <a name="cnoaccessor-class"></a>CNoAccessor Sınıfı

, Ve gibi bir `TAccessor` `CCommand` `CTable` erişimci sınıfı bağımsız değişkeni gerektiren şablon sınıfları için şablon bağımsız değişkeni () olarak kullanılabilir.

## <a name="syntax"></a>Syntax

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Açıklamalar

`CNoAccessor`Sınıfın parametreleri veya çıkış sütunlarını desteklemesini istemediğiniz durumlarda şablon bağımsız değişkeni olarak kullanın.

`CNoAccessor` her biri diğer erişimci sınıfı yöntemlerine karşılık gelen aşağıdaki saplama yöntemlerini uygular:

- `BindColumns` -Sütunları erişimcilere bağlar.

- `BindParameters` -Oluşturulan parametreleri sütunlara bağlar.

- `Bind` -Bağlamaları oluşturur.

- `Close` -Erişimciyi kapatır.

- `ReleaseAccessors` -Sınıf tarafından oluşturulan erişimcileri yayınlar.

- `FreeRecordMemory` -Geçerli kayıttaki, serbest olması gereken tüm sütunları serbest bırakır.

- `GetColumnInfo` -Açılan satır kümesinden sütun bilgisini alır.

- `GetNumAccessors` -Sınıf tarafından oluşturulan erişimcilerinin sayısını alır.

- `IsAutoAccessor` -Bir taşıma işlemi sırasında erişimci için veriler otomatik olarak alınırsa true döndürür.

- `GetHAccessor` -Belirtilen erişimcinin erişimci tanıtıcısını alır.

- `GetBuffer` -İşaretçiyi yer işareti arabelleğine alır.

- `NoBindOnNullRowset` -Boş satır kümelerinde veri bağlamayı engeller.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
