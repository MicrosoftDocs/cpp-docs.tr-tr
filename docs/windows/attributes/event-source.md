---
title: event_source (C++ COM özniteliği)
description: Microsoft C++ uzantısı com özniteliğini nasıl kullanacağınızı öğrenin `event_source` .
ms.date: 11/20/2020
f1_keywords:
- vc-attr.event_source
helpviewer_keywords:
- event handling, attributes
- event logs, event source
- event sources, creating
- event_source attribute
- event sources
- event handling, creating event source
ms.openlocfilehash: 3cdfaaa86f8fc36bf0dc90d7961077546362a662
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483275"
---
# <a name="event_source-attribute"></a>`event_source` özniteliği

Bir olay kaynağı oluşturur.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../../build/reference/permissive-standards-conformance.md) .

## <a name="syntax"></a>Söz dizimi

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Parametreler

*`type`*\
Aşağıdaki değerlerden birini numaralandırma:

- `native` yönetilmeyen C/C++ kodu için (yönetilmeyen sınıflar için varsayılan).

- `com` COM kodu için. `coclass`Ne zaman kullanın *`type`* = `com` . Bu değer, aşağıdaki üst bilgi dosyalarını dahil etmeniz gerekir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*`optimize`*\
*Tür* olduğunda, `native` `optimize=size` bir sınıftaki tüm olaylar için 4 baytlık depolama (minimum) (en düşük) olduğunu ve `optimize=speed` 4 * (olay sayısı) depolama baytlarının olduğunu belirtmek için (varsayılan) ' ı belirtebilirsiniz.

*`decorate`*\
*Tür* olduğunda, `native` `decorate=false` birleştirilmiş ( *`.mrg`* ) dosyasında genişletilmiş adın kapsayan sınıf adını dahil lemeyeceğini göstermek için öğesini belirtebilirsiniz. [`/Fx`](../../build/reference/fx-merge-injected-code.md) dosya oluşturmanıza olanak sağlar *`.mrg`* . `decorate=false`Varsayılan değer olan, birleştirilmiş dosyada tam nitelikli tür adlarıyla sonuçlanır.

## <a name="remarks"></a>Açıklamalar

**`event_source`** C++ özniteliği, uygulandığı sınıf veya yapının bir olay kaynağı olacağını belirtir.

**`event_source`**[`event_receiver`](event-receiver.md)özniteliği ve anahtar sözcüğü ile birlikte kullanılır [`__event`](../../cpp/event.md) . `event_receiver`Olay alıcıları oluşturmak için kullanın. **`__event`** Bu yöntemleri olay olarak belirtmek için olay kaynağı içindeki yöntemleri kullanın.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|--|--|
| **Şunlara uygulanır** | **`class`**, **`struct`** |
| **Yinelenebilir** | Hayır |
| **Gerekli öznitelikler** | **`coclass`** oluşturulurken `type`=`com` |
| **Geçersiz öznitelikler** | Yok |

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)\
[`event_receiver`](event-receiver.md)\
[`__event`](../../cpp/event.md)\
[`__hook`](../../cpp/hook.md)\
[`__unhook`](../../cpp/unhook.md)\
[Class öznitelikleri](class-attributes.md)
