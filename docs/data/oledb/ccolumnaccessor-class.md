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
ms.openlocfilehash: 2a3b1dac51a8300a915a7177c36f15512b583fa0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212116"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor Sınıfı

Eklenen tüketici kodu oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Açıklamalar

Eklenen kodda, her sütun ayrı bir erişimci olarak bağlanır. Bu sınıfın eklenen kodda kullanıldığını bilmeniz gerekir (örneğin, hata ayıklama sırasında onunla karşılaşabilirsiniz), ancak genellikle bunu veya yöntemlerini doğrudan kullanmak zorunda kalmaz.

`CColumnAccessor`, her biri işlevleri diğer erişimci sınıfı yöntemlerine karşılık gelen aşağıdaki saplama yöntemlerini uygular:

- oluşturucuyu `CColumnAccessor`; `CColumnAccessor` nesnesini başlatır ve başlatır.

- `CreateAccessor`, sütun bağlama yapıları için bellek ayırır ve sütun veri üyelerini başlatır.

- `BindColumns`, sütunları erişimcilere bağlar.

- `SetParameterBuffer` parametreler için arabellekleri ayırır.

- `AddParameter` parametre girişi yapılarına bir parametre girişi ekler.

- `HasOutputColumns` erişimcinin çıkış sütunları olup olmadığını belirler

- `HasParameters` erişimcinin parametrelere sahip olup olmadığını belirler.

- `BindParameters` oluşturulan parametreleri sütunlara bağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
