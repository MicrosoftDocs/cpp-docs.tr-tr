---
title: event_source (C++ COM özniteliği)
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
ms.openlocfilehash: bea90020c3ec570149e11db95ff6d6f8fd0a5507
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845308"
---
# <a name="event_source"></a>event_source

Bir olay kaynağı oluşturur.

## <a name="syntax"></a>Söz dizimi

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Parametreler

*türüyle*<br/>
Aşağıdaki değerlerden birini numaralandırma:

- `native` yönetilmeyen C/C++ kodu için (yönetilmeyen sınıflar için varsayılan).

- `com` COM kodu için. `coclass`Ne zaman kullanmanız gerekir `type` = `com` . Bu değer, aşağıdaki üst bilgi dosyalarını dahil etmeniz gerekir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*getirileceğini*<br/>
*Tür* olduğunda, `native` `optimize=size` bir sınıftaki tüm olaylar için 4 baytlık depolama (minimum) (en düşük) olduğunu veya `optimize=speed` (varsayılan), 4 * (olay sayısı) depolama baytlarının olduğunu göstermek için belirtebilirsiniz.

*donatmak*<br/>
*Tür* olduğunda, `native` `decorate=false` birleştirilmiş (. MRG) dosyasındaki genişletilmiş adın kapsayan sınıf adını içermemesi gerektiğini göstermek için öğesini belirtebilirsiniz. [/FX](../../build/reference/fx-merge-injected-code.md) . MRG dosyaları oluşturmanıza olanak tanır. `decorate=false`Varsayılan değer olan, birleştirilmiş dosyada tam nitelikli tür adlarıyla sonuçlanır.

## <a name="remarks"></a>Açıklamalar

**Event_source** C++ özniteliği, uygulandığı sınıf veya yapının bir olay kaynağı olacağını belirtir.

**event_source** , [event_receiver](event-receiver.md) özniteliğiyle ve [__event](../../cpp/event.md) anahtar sözcüğüyle birlikte kullanılır. `event_receiver`Olay alıcıları oluşturmak için kullanın. **`__event`** Bu yöntemleri olay olarak belirtmek için olay kaynağı içindeki yöntemleri kullanın.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|**coclass**`type`=`com`|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
