---
title: requires_category (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.requires_category
helpviewer_keywords:
- requires_category attribute
ms.assetid: a645fdc6-1ef5-414d-8c56-5fe2686d4687
ms.openlocfilehash: 044f868a6be8391a4b0dfafd58ff0f3178575047
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231565"
---
# <a name="requires_category"></a>requires_category

Hedef sınıfın gerekli bileşen kategorilerini belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ requires_category(
  requires_category) ]
```

### <a name="parameters"></a>Parametreler

*requires_category*<br/>
Gerekli kategorinin KIMLIĞI.

## <a name="remarks"></a>Açıklamalar

**Requires_category** C++ özniteliği, hedef sınıf için gereken bileşen kategorilerini belirtir. Daha fazla bilgi için bkz. [REQUIRED_CATEGORY](../../atl/reference/category-macros.md#required_category).

Bu öznitelik, [coclass](coclass.md), [ProgID](progid.md)veya [vi_progid](vi-progid.md) özniteliğinin (ya da bunlardan birini belirten başka bir özniteliğin) aynı öğeye uygulanmasını gerektirir.

## <a name="example"></a>Örnek

Aşağıdaki kod nesnenin denetim kategorisini uygulamasını gerektirir.

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
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Aşağıdakilerden biri veya daha fazlası: `coclass` , `progid` , veya `vi_progid` .|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM öznitelikleri](com-attributes.md)<br/>
[implements_category](implements-category.md)
