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
ms.openlocfilehash: 81eba3c032a3556d1c69ad02652455ebc07ab6be
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409648"
---
# <a name="eventsource"></a>event_source

Olay kaynağı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ event_source(type, optimize=[speed | size], decorate=[true | false]) ]
```

### <a name="parameters"></a>Parametreler

*type*<br/>
Sabit listesi aşağıdaki değerlerden biri:

- `native` Yönetilmeyen C/C++ kodu için (yönetilmeyen sınıflar için varsayılan).

- `com` COM kodu için. Kullanmalısınız `coclass` olduğunda `type` = `com`. Bu değer, aşağıdaki üst bilgi dosyaları eklemenizi gerektirir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*optimize*<br/>
Zaman *türü* olduğu `native`, belirtebilirsiniz `optimize=size`olduğunu depolamanın 4 bayt (en az) için tüm olayları bir sınıfta belirtmek için veya `optimize=speed` (4 olduğunu göstermek için varsayılan) * (olay sayısı) depolama baytı.

*İşaretleme*<br/>
Zaman *türü* olduğu `native`, belirtebileceğiniz `decorate=false`, birleştirilmiş (.mrg) dosyasında genişletilmiş adının kapsayan sınıf adını içermemelidir belirtmek için. [/FX](../../build/reference/fx-merge-injected-code.md) .mrg dosyaları oluşturmanıza olanak tanır. `decorate=false`, varsayılan değer, tam olarak nitelenmiş tür adlarını birleştirilmiş dosya sonuçlanıyor.

## <a name="remarks"></a>Açıklamalar

**Event_source** C++ özniteliği, sınıf veya yapı, uygulandığı bir olay kaynağı olacağını belirtir.

**event_source** ile birlikte kullanılan [event_receiver](event-receiver.md) özniteliği ve [__event](../../cpp/event.md) anahtar sözcüğü. Kullanım `event_receiver` Olay alıcıları oluşturmak için. Kullanım **__event** olaylar olarak söz konusu yöntemleri belirtmek için olay kaynağı içindeki yöntemlerde.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|**coclass'ı** olduğunda `type`=`com`|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[event_receiver](event-receiver.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)