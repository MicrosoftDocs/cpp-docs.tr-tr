---
description: 'Daha fazla bilgi edinin: CColumnAccessor sınıfı'
title: CColumnAccessor Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CColumnAccessor
- ATL::CColumnAccessor
- ATL.CColumnAccessor
helpviewer_keywords:
- CColumnAccessor class
ms.assetid: 6ce1e67f-6a20-490d-9326-c168b43eee7e
ms.openlocfilehash: 7551f39d34bb4f13b4ffae358db05aede2adb9e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335529"
---
# <a name="ccolumnaccessor-class"></a>CColumnAccessor Sınıfı

Eklenen tüketici kodu oluşturur.

## <a name="syntax"></a>Syntax

```cpp
class CColumnAccessor : public CAccessorBase
```

## <a name="remarks"></a>Açıklamalar

Eklenen kodda, her sütun ayrı bir erişimci olarak bağlanır. Bu sınıfın eklenen kodda kullanıldığını bilmeniz gerekir (örneğin, hata ayıklama sırasında onunla karşılaşabilirsiniz), ancak genellikle bunu veya yöntemlerini doğrudan kullanmak zorunda kalmaz.

`CColumnAccessor` her biri işlevleri diğer erişimci sınıfı yöntemlerine karşılık gelen aşağıdaki saplama yöntemlerini uygular:

- `CColumnAccessor` Oluşturucu; nesneyi örnekleyen ve başlatır `CColumnAccessor` .

- `CreateAccessor` Sütun bağlama yapıları için bellek ayırır ve sütun veri üyelerini başlatır.

- `BindColumns` Sütunları erişimcilere bağlar.

- `SetParameterBuffer` Parametreler için arabellekleri ayırır.

- `AddParameter` Parametre girişi yapılarına bir parametre girişi ekler.

- `HasOutputColumns` Erişimcinin çıkış sütunları içerip içermediğini belirler

- `HasParameters` Erişimcinin parametrelere sahip olup olmadığını belirler.

- `BindParameters` Oluşturulan parametreleri sütunlara bağlar.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
