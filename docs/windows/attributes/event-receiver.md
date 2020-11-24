---
title: event_receiver (C++ COM özniteliği)
description: Microsoft C++ uzantısı com özniteliğini nasıl kullanacağınızı öğrenin `event_receiver` .
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_receiver
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.openlocfilehash: 8ed6ef6113d72a9565b275dff4e035dc56f11e82
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483288"
---
# <a name="event_receiver-attribute"></a>`event_receiver` özniteliği

Bir olay alıcısı (havuz) oluşturur.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../../build/reference/permissive-standards-conformance.md) .

## <a name="syntax"></a>Söz dizimi

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Parametreler

*`type`*\
Aşağıdaki değerlerden birini numaralandırma:

- `native` yönetilmeyen C/C++ kodu için (yerel sınıflar için varsayılan).

- `com` COM kodu için. Bu değer, bu üst bilgi dosyalarını dahil etmeniz gerekir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`layout_dependent`*\
*`layout_dependent`* Yalnızca com için belirtin `type` = **com**. *`layout_dependent`* bir Boole değeri:

- **`true`** olay alıcısındaki temsilcilerin imzasının, olay kaynağında bağlandıkları olanlarla tam olarak eşleşmesi gerektiği anlamına gelir. Olay alıcısı işleyici adları, ilgili olay kaynağı arabiriminde belirtilen adlarla eşleşmelidir. `coclass`Ne olduğunda *`layout_dependent`* kullanın **`true`** . Belirtmek biraz daha etkilidir **`true`** .

- **`false`** (varsayılan) çağrı kuralının ve depolama sınıfının ( `virtual` , `static` ve diğer) olay yöntemiyle ve işleyicilerle eşleşmesi gerekmediği anlamına gelir. İşleyici adlarının Ayrıca olay kaynağı arabirim yöntemi adlarıyla eşleşmesi gerekmez.

## <a name="remarks"></a>Açıklamalar

**`event_receiver`** C++ özniteliği, Microsoft C++ Birleşik olay modeli kullanılarak uygulamanın uygulandığı sınıf veya yapının bir olay alıcısı olacağını belirtir.

**`event_receiver`**[`event_source`](event-source.md)özniteliği ve [`__hook`](../../cpp/hook.md) ve [`__unhook`](../../cpp/unhook.md) anahtar kelimeleri ile kullanılır. `event_source`Olay kaynakları oluşturmak için kullanın. Olay alıcı **`__hook`** yöntemlerini olay kaynağı olaylarına ilişkilendirmek için bir olay alıcısının yöntemleri içinde kullanın. **`__unhook`** Bunları kaldırmak için kullanın.

*`layout_dependent`* yalnızca COM Olay alıcıları () için belirtilir `type` = **`com`** . İçin varsayılandır *`layout_dependent`* **`false`** .

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|--|--|
| **Şunlara uygulanır** | **`class`**, **`struct`** |
| **Yinelenebilir** | Hayır |
| **Gerekli öznitelikler** | `coclass` oluşturulurken *`layout_dependent`*=**`true`** |
| **Geçersiz öznitelikler** | Yok |

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)\
[`event_source`](event-source.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[Class öznitelikleri](class-attributes.md)
