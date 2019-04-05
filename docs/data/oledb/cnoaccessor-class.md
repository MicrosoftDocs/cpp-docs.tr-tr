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
ms.openlocfilehash: 0cf1b47cc03d1839ae5c547393c3c193dab439d4
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027668"
---
# <a name="cnoaccessor-class"></a>CNoAccessor Sınıfı

Bir şablon bağımsız değişkeni kullanılabilir (`TAccessor`) için şablon sınıfları gibi `CCommand` ve `CTable`, bir erişimci sınıfında bağımsız değişken gerektirir.

## <a name="syntax"></a>Sözdizimi

```cpp
class CNoAccessor
```

## <a name="remarks"></a>Açıklamalar

Kullanım `CNoAccessor` parametrelerini veya sütunlarını çıkış desteklemeye sınıfı istemediğinizde bir şablon bağımsız değişkeni olarak.

`CNoAccessor` karşılık gelen her biri için diğer erişimcisi sınıf yöntemleri aşağıdaki saptama yöntemleri uygular:

- `BindColumns` -Sütunları için erişimciler bağlar.

- `BindParameters` -Sütun oluşturulan parametreleri bağlar.

- `Bind` -Bağlamaları oluşturur.

- `Close` -Erişimci kapatır.

- `ReleaseAccessors` -Sınıfı tarafından oluşturulan erişimcileri serbest bırakır.

- `FreeRecordMemory` -Boşaltılması için gereken geçerli kayıt tüm sütunları bırakır.

- `GetColumnInfo` -Açık satır kümesinden sütun bilgileri alır.

- `GetNumAccessors` -Sınıfı tarafından oluşturulan erişimcileri sayısını alır.

- `IsAutoAccessor` -Veri taşıma işlemi sırasında otomatik olarak için erişimci alınır true değerini döndürür.

- `GetHAccessor` -Belirtilen bir erişimci erişimci tanıtıcısı alır.

- `GetBuffer` -Yer işareti arabellek için işaretçi alır.

- `NoBindOnNullRowset` -Boş satır kümeleri üzerinde veri bağlamasını engeller.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)