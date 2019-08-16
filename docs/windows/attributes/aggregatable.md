---
title: toplanamayanC++ (com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: aa70c2417b3262e98118b5e717ce39d0147024de
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491009"
---
# <a name="aggregatable"></a>toplanabilir

Sınıfın toplamayı desteklediğini gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>Parametreler

*value*<br/>
Seçim COM nesnesinin toplanabileceği zaman gösteren bir parametre:

- `never`COM nesnesi toplanamıyor.

- `allowed`COM nesnesi doğrudan oluşturulabilir veya toplanabilir. Bu varsayılandır.

- `always`COM nesnesi doğrudan oluşturulamaz ve yalnızca toplanabilir. Bu nesne için `CoCreateInstance` çağırdığınızda, toplanan `IUnknown` nesnenin arabirimini (Denetim `IUnknown`) belirtmeniz gerekir.

## <a name="remarks"></a>Açıklamalar

**Toplanamayan** C++ öznitelik, [toplanabilir](/windows/win32/Midl/aggregatable) MIDL özniteliğiyle aynı işlevselliğe sahiptir. Bu, derleyicinin **toplanabilir** özniteliğini oluşturulan. IDL dosyasına geçimeyeceği anlamına gelir.

Bu öznitelik, [coclass](coclass.md), [ProgID](progid.md)veya [vi_progid](vi-progid.md) özniteliğinin (ya da bunlardan birini belirten başka bir özniteliğin) aynı öğeye uygulanmasını gerektirir. Tek bir öznitelik kullanılırsa, diğer ikisi otomatik olarak uygulanır. Örneğin, `progid` `vi_progid` uygulanmışsa ve`coclass` de uygulanır.

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
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Aşağıdakilerden biri veya daha fazlası: `coclass`, `progid`, veya `vi_progid`.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Toplama](/windows/win32/com/aggregation)