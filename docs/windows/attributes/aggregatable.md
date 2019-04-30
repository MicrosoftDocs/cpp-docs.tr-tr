---
title: toplanabilir (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.aggregatable
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
ms.openlocfilehash: 8d5ceb46a124db8c0082495d48e6ee0e21655422
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391003"
---
# <a name="aggregatable"></a>toplanabilir

Sınıf toplama desteklediğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ aggregatable(value) ]
```

### <a name="parameters"></a>Parametreler

*value*<br/>
(İsteğe bağlı) COM nesnesinin ne zaman toplanabilir belirtmek için bir parametre:

- `never` COM nesnesi toplanamaz.

- `allowed` COM Nesne doğrudan oluşturulabilir veya onu toplanabilir. Bu varsayılandır.

- `always` COM Nesne doğrudan oluşturulamaz ve yalnızca toplanabilir. Çağırdığınızda `CoCreateInstance` bu nesne için toplama nesnenin belirtmelisiniz `IUnknown` arabirimi (denetleme `IUnknown`).

## <a name="remarks"></a>Açıklamalar

**Toplanabilir** C++ özniteliği ile aynı işlevlere sahip [toplanabilir](/windows/desktop/Midl/aggregatable) MIDL özniteliği. Bu derleyici geçer anlamına gelir **toplanabilir** oluşturulan .idl dosyasına özniteliği aracılığıyla.

Bu öznitelik gerektiren [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye. Herhangi bir tek öznitelik kullandıysanız, diğer iki otomatik olarak uygulanır. Örneğin, varsa `progid` uygulanan `vi_progid` ve `coclass` de uygulanır.

### <a name="atl-projects"></a>ATL projeleri

Bu öznitelik ATL kullanan bir proje içinde kullanılıyorsa, öznitelik davranışını değiştirir. Daha önce açıklandığı gibi davranışa ek olarak, öznitelik ayrıca aşağıdaki makroları biri hedef sınıfına ekler:

|Parametre değeri|Eklenen makrosu|
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
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Bir veya daha fazlasını: `coclass`, `progid`, veya `vi_progid`.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[Toplama](/windows/desktop/com/aggregation)