---
title: event_receiver (C++ com özniteliği)
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
ms.openlocfilehash: 9653a0b5c756857d92914496b9c5c6f8aee56ebb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167088"
---
# <a name="event_receiver"></a>event_receiver

Bir olay alıcısı (havuz) oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ event_receiver(type
   [, layout_dependent=false]) ]
```

### <a name="parameters"></a>Parametreler

*type*<br/>
Aşağıdaki değerlerden birini numaralandırma:

- yönetilmeyen C/C++ kod için `native` (yerel sınıflar için varsayılan).

- COM kodu için `com`. Bu değer, aşağıdaki üst bilgi dosyalarını dahil etmeniz gerekir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Yalnızca **com**=`type`*layout_dependent* belirtin. *layout_dependent* bir Boole değeri:

- **doğru** , olay alıcısındaki temsilcilerin imzasının, olay kaynağında bağlandıkları olanlarla tam olarak eşleşmesi gerektiği anlamına gelir. Olay alıcısı işleyici adları, ilgili olay kaynağı arabiriminde belirtilen adlarla eşleşmelidir. *Layout_dependent* **true**olduğunda `coclass` kullanmanız gerekir. **Doğru**belirtmek biraz daha etkilidir.

- **false** (varsayılan), çağırma kuralı ve depolama sınıfının (sanal, statik ve diğer) olay yöntemiyle ve işleyicilerle eşleşmesi gerekmediği anlamına gelir; ya da işleyici adlarının olay kaynağı arabirim yöntemi adlarıyla eşleşmesi gerekir.

## <a name="remarks"></a>Açıklamalar

**Event_receiver** C++ özniteliği, uygulanacağı sınıf veya yapının, görsel C++ birleştirilmiş olay modeli kullanılarak bir olay alıcısı olacağını belirtir.

**event_receiver** , [event_source](event-source.md) özniteliğiyle ve [__hook](../../cpp/hook.md) ve [__unhook](../../cpp/unhook.md) anahtar sözcükleriyle kullanılır. Olay kaynakları oluşturmak için `event_source` kullanın. Olay alıcı yöntemlerini bir olay kaynağının olaylarına ("kanca") ilişkilendirmek için bir olay alıcısının yöntemleri içinde **__hook** kullanın. **__Unhook** , bunların ilişkilendirmesini kaldırmak için kullanın.

*layout_dependent* yalnızca com olay alıcıları (`type`=**com**) için belirtilir. *Layout_dependent* için varsayılan değer **false**'dur.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|*layout_dependent*=**true** `coclass`|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[event_source](event-source.md)<br/>
[__event](../../cpp/event.md)<br/>
[__hook](../../cpp/hook.md)<br/>
[__unhook](../../cpp/unhook.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
