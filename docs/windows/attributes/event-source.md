---
title: event_source (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.assetid: 0983e36a-6127-4fbb-8a22-8dfec6564c16
ms.openlocfilehash: e187e57f21e9c94068c0b3396b93deed617fef2a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167075"
---
# <a name="event_source"></a>event_source

Bir olay kaynağı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Parametreler

*type*<br/>
Aşağıdaki değerlerden birini numaralandırma:

- yönetilmeyen C/C++ kod için `native` (yönetilmeyen sınıflar için varsayılan).

- COM kodu için `com`. =`com``type``coclass` kullanmanız gerekir. Bu değer, aşağıdaki üst bilgi dosyalarını dahil etmeniz gerekir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
*Tür* `native`olduğunda, bir sınıftaki tüm olaylar için 4 baytlık depolama alanı (minimum) (en düşük) `optimize=speed` ve 4 * (olay sayısı) depolama baytlarının olduğunu göstermek için `optimize=size`belirtebilirsiniz.

*donatmak*<br/>
*Tür* `native`olduğunda, birleştirilmiş (. MRG) dosyasındaki genişletilmiş adın kapsayan sınıf adını içermemesi gerektiğini göstermek için `decorate=false`belirtebilirsiniz. [/FX](../../build/reference/fx-merge-injected-code.md) . MRG dosyaları oluşturmanıza olanak tanır. Varsayılan olan `decorate=false`, birleştirilmiş dosyada tam nitelikli tür adlarıyla sonuçlanır.

## <a name="remarks"></a>Açıklamalar

**Event_source** C++ özniteliği, uygulandığı sınıf veya yapının bir olay kaynağı olacağını belirtir.

**event_source** , [event_receiver](event-receiver.md) özniteliğiyle ve [__event](../../cpp/event.md) anahtar sözcüğüyle birlikte kullanılır. Olay alıcıları oluşturmak için `event_receiver` kullanın. Bu yöntemleri olay olarak belirtmek için olay kaynağı içindeki yöntemlerle **__event** kullanın.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|`type`=için **coclass** `com`|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
