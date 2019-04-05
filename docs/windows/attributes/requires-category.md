---
title: requires_category (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: ec35a1958d9fbcf77fef7f498c6c0dba3ab17df9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022145"
---
# <a name="requirescategory"></a>requires_category

Hedef sınıfın gerekli bileşen kategorilerini belirler.

## <a name="syntax"></a>Sözdizimi

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>Parametreler

*requires_category*<br/>
Gerekli bir kategori kimliği.

## <a name="remarks"></a>Açıklamalar

**Requires_category** C++ özniteliği hedef sınıfı tarafından gerekli bileşen kategorileri belirtir. Daha fazla bilgi için [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category).

Bu öznitelik gerektiren [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye.

## <a name="example"></a>Örnek

Aşağıdaki kod, nesneyi Denetim kategorisi uygulamak gerektirir.

```cpp
// cpp_attr_ref_requires_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLibrary")];

[ coclass, requires_category("CATID_Control"),
  uuid("1e1a2436-f3ea-4ff3-80bf-5409370e8144")]
class CMyClass {};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Bir veya daha fazlasını: `coclass`, `progid`, veya `vi_progid`.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[implements_category](implements-category.md)