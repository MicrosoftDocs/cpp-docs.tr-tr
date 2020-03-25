---
title: toplanamayanC++ (com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: d929543f699dcd20471ff9a9b45f54119f82a40a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168531"
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

- COM nesnesi `never` toplanamıyor.

- COM nesnesinin doğrudan oluşturulabilmesi veya toplanabilecek `allowed`. Bu varsayılandır.

- `always` COM nesnesi doğrudan oluşturulamaz ve yalnızca toplanabilir. Bu nesne için `CoCreateInstance` çağırdığınızda, toplanan nesnenin `IUnknown` arabirimini (denetim `IUnknown`) belirtmeniz gerekir.

## <a name="remarks"></a>Açıklamalar

**Toplanamayan** C++ öznitelik, [toplanabilir](/windows/win32/Midl/aggregatable) MIDL özniteliğiyle aynı işlevselliğe sahiptir. Bu, derleyicinin **toplanabilir** özniteliğini oluşturulan. IDL dosyasına geçimeyeceği anlamına gelir.

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
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Aşağıdakilerden biri veya daha fazlası: `coclass`, `progid`veya `vi_progid`.|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Toplama](/windows/win32/com/aggregation)
