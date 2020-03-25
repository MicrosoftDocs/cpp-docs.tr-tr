---
title: CNoAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: c82d756690c6c2a719cb03f458c471aa44e3d5b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211737"
---
# <a name="cnoaccessor-class"></a>CNoAccessor Sınıfı

, Bir erişimci sınıfı bağımsız değişkeni gerektiren `CCommand` ve `CTable`gibi şablon sınıfları için şablon bağımsız değişkeni (`TAccessor`) olarak kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Açıklamalar

Sınıfın parametreleri veya çıkış sütunlarını desteklemesini istemediğiniz durumlarda `CNoAccessor` şablon bağımsız değişkeni olarak kullanın.

`CNoAccessor`, her biri diğer erişimci sınıfı yöntemlerine karşılık gelen aşağıdaki saplama yöntemlerini uygular:

- `BindColumns`-sütunları erişimcilere bağlar.

- `BindParameters`-oluşturulan parametreleri sütunlara bağlar.

- `Bind`-bağlamalar oluşturur.

- `Close`-erişimciyi kapatır.

- `ReleaseAccessors`-sınıfı tarafından oluşturulan erişimcileri yayınlar.

- `FreeRecordMemory` serbest olması gereken geçerli kayıttaki tüm sütunları serbest bırakır.

- `GetColumnInfo`-açılan satır kümesinden sütun bilgilerini alır.

- `GetNumAccessors`-sınıf tarafından oluşturulan erişimcilerinin sayısını alır.

- `IsAutoAccessor`-bir taşıma işlemi sırasında erişimci için veriler otomatik olarak alınırsa true döndürür.

- `GetHAccessor`-belirtilen erişimcinin erişimci tanıtıcısını alır.

- `GetBuffer`-işaretçiyi yer işareti arabelleğine alır.

- `NoBindOnNullRowset`-boş satır kümelerinde veri bağlamayı önler.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
