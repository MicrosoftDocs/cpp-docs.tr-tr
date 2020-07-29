---
title: toplanamayan (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: 883094c85418c15455a020cfe73538a6576eddd0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224493"
---
# <a name="aggregatable"></a>toplanabilir

Sınıfın toplamayı desteklediğini gösterir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>Parametreler

*deeri*<br/>
Seçim COM nesnesinin toplanabileceği zaman gösteren bir parametre:

- `never`COM nesnesi toplanamıyor.

- `allowed`COM nesnesi doğrudan oluşturulabilir veya toplanabilir. Bu varsayılan seçenektir.

- `always`COM nesnesi doğrudan oluşturulamaz ve yalnızca toplanabilir. `CoCreateInstance`Bu nesne için çağırdığınızda, toplanan nesnenin `IUnknown` arabirimini (denetim) belirtmeniz gerekir `IUnknown` .

## <a name="remarks"></a>Açıklamalar

**Toplanabilir** C++ özniteliği, [toplanabilir](/windows/win32/Midl/aggregatable) MIDL özniteliğiyle aynı işlevselliğe sahiptir. Bu, derleyicinin **toplanabilir** özniteliğini oluşturulan. IDL dosyasına geçimeyeceği anlamına gelir.

Bu öznitelik, [coclass](coclass.md), [ProgID](progid.md)veya [vi_progid](vi-progid.md) özniteliğinin (ya da bunlardan birini belirten başka bir özniteliğin) aynı öğeye uygulanmasını gerektirir. Tek bir öznitelik kullanılırsa, diğer ikisi otomatik olarak uygulanır. Örneğin, `progid` uygulanmışsa `vi_progid` ve `coclass` de uygulanır.

### <a name="atl-projects"></a>ATL projeleri

Bu öznitelik, ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışı değişir. Daha önce açıklanan davranışa ek olarak, özniteliği de hedef sınıfa aşağıdaki makrolardan birini ekler:

|Parametre değeri|Makro ekleniyor|
|---------------------|--------------------|
|`Never`|[DECLARE_NOT_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|
|`Allowed`|[DECLARE_POLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|
|`Always`|[DECLARE_ONLY_AGGREGATABLE](../../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_aggregatable.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyModule")];

[ coclass, aggregatable(allowed),
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]
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

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Toplama](/windows/win32/com/aggregation)
