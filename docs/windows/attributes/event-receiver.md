---
title: event_receiver (C++ COM özniteliği)
ms.date: 10/02/2018
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
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
ms.openlocfilehash: 7280729a9ae3a054468e1f11bdcc4a563b32effe
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845295"
---
# <a name="event_receiver"></a>event_receiver

Bir olay alıcısı (havuz) oluşturur.

## <a name="syntax"></a>Söz dizimi

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Aşağıdaki değerlerden birini numaralandırma:

- `native` yönetilmeyen C/C++ kodu için (yerel sınıflar için varsayılan).

- `com` COM kodu için. Bu değer, aşağıdaki üst bilgi dosyalarını dahil etmeniz gerekir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Yalnızca com için *layout_dependent* belirtin `type` = **com**. *layout_dependent* bir Boole değeri:

- **`true`** olay alıcısındaki temsilcilerin imzasının, olay kaynağında takıldıkları olanlarla tam olarak eşleşmesi gerektiği anlamına gelir. Olay alıcısı işleyici adları, ilgili olay kaynağı arabiriminde belirtilen adlarla eşleşmelidir. `coclass` *Layout_dependent* olduğunda kullanmanız gerekir **`true`** . Belirtmek biraz daha etkilidir **`true`** .

- **`false`** (varsayılan) çağrı kuralının ve depolama sınıfının (sanal, statik ve diğer) olay yöntemiyle ve işleyicilerle eşleşmesi gerekmediği anlamına gelir; ya da işleyici adlarının olay kaynağı arabirim yöntemi adlarıyla eşleşmesi gerekir.

## <a name="remarks"></a>Açıklamalar

**Event_receiver** C++ özniteliği, uygulandığı sınıf veya yapının, Visual C++ birleştirilmiş olay modeli kullanılarak bir olay alıcısı olacağını belirtir.

**event_receiver** , [event_source](event-source.md) özniteliğiyle ve [__hook](../../cpp/hook.md) ve [__unhook](../../cpp/unhook.md) anahtar sözcükleriyle kullanılır. `event_source`Olay kaynakları oluşturmak için kullanın. Olay alıcı **`__hook`** yöntemlerini olay kaynağı olaylarına ilişkilendirmek için bir olay alıcısının yöntemleri içinde kullanın. **`__unhook`** Bunların ilişkilendirmesini kaldırmak için kullanın.

*layout_dependent* yalnızca com olay alıcıları ( `type` = **com**) için belirtilir. *Layout_dependent* için varsayılan değer **`false`** .

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|`coclass`*layout_dependent* olduğunda=**`true`**|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
