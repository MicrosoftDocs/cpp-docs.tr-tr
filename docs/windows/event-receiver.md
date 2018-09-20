---
title: event_receiver | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.event_receiver
dev_langs:
- C++
helpviewer_keywords:
- event_receiver attribute
- event receivers
- events [C++], event receivers (sinks)
- event handling [C++], attributes
- event handling [C++], creating receiver
- event sinks, creating
- event sinks
ms.assetid: bf8fe770-3ea2-4128-b46b-166222ee4097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d30ac0d2e1d18b22c6130212503576f5fe343a8d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407555"
---
# <a name="eventreceiver"></a>event_receiver

Bir olay alıcısı (havuz) oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
[ event_receiver(
   type
   [, layout_dependent=false]
) ]
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
Sabit listesi aşağıdaki değerlerden biri:

- `native` Yönetilmeyen C/C++ kodu için (varsayılan yerel sınıflar için).

- `com` COM kodu için. Bu değer, aşağıdaki üst bilgi dosyaları eklemenizi gerektirir:

    ```cpp
    #define _ATL_ATTRIBUTES
    #include <atlbase.h>
    #include <atlcom.h>
    ```

*layout_dependent*<br/>
Belirtin *layout_dependent* yalnızca `type` = **com**. *layout_dependent* bir Boole değeri:

- **doğru** alıcı olanlar için bunlar kancalandı olay kaynağı tam olarak eşleşmelidir olay temsilci imzası anlamına gelir. Olay alıcısı işleyici adları, ilgili olay kaynak arabiriminde belirtilen adlarının eşleşmesi gerekmektedir. Kullanmalısınız `coclass` olduğunda *layout_dependent* olduğu **true**. Belirtmek için biraz daha verimlidir **true**.

- **false** (varsayılan) anlamına çağırma kuralı ve depolama sınıfı (sanal, statik ve diğerleri) işleyici adlarının olay kaynağı arabirim yöntemi adları eşleşmesi gerekir ya da olay yöntemi ve işleyicileri; eşleşmesi gerekmez.

## <a name="remarks"></a>Açıklamalar

**Event_receiver** C++ özniteliği, sınıf veya yapı, uygulandığı Visual C++ birleştirilmiş olay modeli kullanarak bir olay alıcısı olacağını belirtir.

**event_receiver** ile kullanılan [event_source](../windows/event-source.md) özniteliği ve [__hook](../cpp/hook.md) ve [__unhook](../cpp/unhook.md) anahtar sözcükleri. Kullanım `event_source` olay kaynakları oluşturmak için. Kullanım **__hook** olayları olay kaynağı ("kanca") olay alıcı yöntemlere ilişkilendirilecek olay alıcısı'nın yöntemler içindeki. Kullanım **__unhook** bunları ilişkilendirmesini kaldırmak.

*layout_dependent* COM Olay alıcıları için yalnızca belirtilen (`type`=**com**). İçin varsayılan *layout_dependent* olduğu **false**.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|`coclass` zaman *layout_dependent*=**true**|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)<br/>
[event_source](../windows/event-source.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[Sınıf Öznitelikleri](../windows/class-attributes.md)  