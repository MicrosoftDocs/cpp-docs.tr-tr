---
title: __hook
description: Yerel olay işleme için Microsoft C++ uzantısı anahtar sözcüğünü nasıl kullanacağınızı öğrenin `__hook` .
ms.date: 11/20/2020
f1_keywords:
- __hook_cpp
- __hook
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.openlocfilehash: 2a2bde221c53f0e1d420e2ab3a88eb299f6c284c
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483262"
---
# <a name="__hook-keyword"></a>`__hook` sözcükle

Bir işleyici yöntemini bir olayla ilişkilendirir.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

## <a name="syntax"></a>Söz dizimi

```cpp
long __hook(
    &SourceClass::EventMethod,
    source,
    &ReceiverClass::HandlerMethod
    [, receiver = this]
);

long __hook(
    interface,
    source
);
```

### <a name="parameters"></a>Parametreler

*`&SourceClass::EventMethod`*\
Olay işleyicisi yöntemini dağıttığınız olay yöntemine yönelik bir işaretçi:

- Yerel C++ olayları: *`SourceClass`* olay kaynak sınıfıdır ve *`EventMethod`* olaydır.

- COM olayları: *`SourceClass`* olay kaynağı arabirimidir ve *`EventMethod`* yöntemlerinden biridir.

- Yönetilen olaylar: *`SourceClass`* olay kaynak sınıfıdır ve *`EventMethod`* olaydır.

*`interface`*\
' A bağlanmakta olan arabirim adı *`receiver`* , yalnızca özniteliği parametresinin bulunduğu com olay alıcıları içindir *`layout_dependent`* [`event_receiver`](../windows/attributes/event-receiver.md) **`true`** .

*`source`*\
Olay kaynağı örneğine yönelik bir işaretçi. İçinde belirtilen koda bağlı olarak `type` `event_receiver` , *`source`* Şu türlerden biri olabilir:

- Yerel bir olay kaynağı nesne işaretçisi.

- `IUnknown`Tabanlı işaretçi (com kaynağı).

- Yönetilen bir nesne işaretçisi (yönetilen olaylar için).

*`&ReceiverClass::HandlerMethod`*\
Bir olaya bağlamak için olay işleyicisi yöntemine yönelik bir işaretçi. İşleyici bir sınıfın yöntemi veya aynı başvuru olarak belirtilir. Sınıf adını belirtmezseniz, **`__hook`** sınıfın çağrıldığı bir sınıf olduğunu varsayar.

- Yerel C++ olayları: *`ReceiverClass`* olay alıcı sınıfıdır ve `HandlerMethod` işleyicidir.

- COM olayları: *`ReceiverClass`* olay alıcı arabirimidir ve *`HandlerMethod`* işleyicilerinden biridir.

- Yönetilen olaylar: *`ReceiverClass`* olay alıcı sınıfıdır ve *`HandlerMethod`* işleyicidir.

*`receiver`*\
Seçim Olay alıcısı sınıfının bir örneğine yönelik işaretçi. Alıcı belirtmezseniz, varsayılan olarak çağrılan alıcı sınıfı veya yapısıdır **`__hook`** .

## <a name="usage"></a>Kullanım

, Olay alıcı sınıfının dışında, Main dahil herhangi bir işlev kapsamında kullanılabilir.

## <a name="remarks"></a>Açıklamalar

Bir olay alıcısındaki iç işlevi kullanarak **`__hook`** bir işleyici metodunu bir olay yöntemiyle ilişkilendirir veya kanca. Belirtilen işleyici daha sonra kaynak belirtilen olayı harekete geçirirse çağrılır. Birkaç işleyiciyi tek bir olaya veya birkaç olayı tek bir işleyiciye bağlayabilirsiniz.

Öğesinin iki biçimi vardır **`__hook`** . Genellikle özniteliğin *layout_dependent* PARAMETRESININ olduğu com olay alıcıları için, çoğu durumda, örneğin ilk (dört bağımsız değişken) formunu kullanabilirsiniz [`event_receiver`](../windows/attributes/event-receiver.md) **`false`** .

Bu durumlarda, metotlardan birindeki bir olayı tetiketmeden önce bir arabirimdeki tüm yöntemleri bir arada bir bağlama gerekmez. Yalnızca olayı işleyen yöntemi bir bağlama yapmanız gerekir. **`__hook`** Yalnızca BIR com olay alıcısı için ikinci (iki bağımsız değişken) biçimini kullanabilirsiniz *`layout_dependent`* **`= true`** .

**`__hook`** uzun bir değer döndürür. Sıfır olmayan dönüş değeri bir hata oluştuğunu belirtir (yönetilen olaylar bir özel durum oluşturur).

Derleyici bir olayın varlığını denetler ve olay imzasının temsilci imzasıyla kabul eder.

**`__hook`** **`__unhook`** Com olayları dışında, olay alıcısını çağırabilir ve dışında bırakabilirsiniz.

Kullanmanın alternatifi **`__hook`** + = işlecini kullanmaktır.

Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz [`event`](../extensions/event-cpp-component-extensions.md) ..

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Örnekler için bkz. [Yerel C++ Içindeki olay işleme](../cpp/event-handling-in-native-cpp.md) ve [com 'da olay işleme](../cpp/event-handling-in-com.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Lerimi](../cpp/keywords-cpp.md)\
[Olay işleme](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
