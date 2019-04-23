---
title: CColumnAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 2d65fb047e758f449ed76c954bb4ac0c3623f6dd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032134"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor Sınıfı

Eklenen tüketici kod oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Açıklamalar

Eklenen kodun her sütun ayrı bir erişimci bağlıdır. Bu sınıf eklenen kodun kullanıldığını bilmeniz gerekir (örneğin, bu hata ayıklama sırasında karşılaşabileceğiniz), ancak genellikle hiçbir zaman doğrudan veya yöntemlerini kullanın.

`CColumnAccessor` işlev diğer erişimcisi sınıf yöntemleri karşılık her biri aşağıdaki saptama yöntemleri uygular:

- `CColumnAccessor` Oluşturucusu oluşturur ve başlatır `CColumnAccessor` nesne.

- `CreateAccessor` Bağlama yapıları sütun için bellek ayırır ve sütun veri üyelerine başlatır.

- `BindColumns` Sütunları için erişimciler bağlar.

- `SetParameterBuffer` Arabellekler için parametreleri ayırır.

- `AddParameter` Bir parametre girişi parametre girişi yapılara ekler.

- `HasOutputColumns` Erişimci sütunları çıktısı olup olmadığını belirler

- `HasParameters` Erişimcisi parametrelere sahip olup olmadığını belirler.

- `BindParameters` Oluşturulan parametre sütunları bağlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)