---
title: __hook
ms.date: 11/04/2016
f1_keywords:
- __hook_cpp
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
ms.openlocfilehash: 5a0eaf0a3bc0617dbcd1f43805af8a95291e7e47
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87188173"
---
# <a name="__hook"></a>__hook

Bir işleyici yöntemini bir olayla ilişkilendirir.

## <a name="syntax"></a>Söz dizimi

```
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

*&SourceClass:: EventMethod*<br/>
Olay işleyicisi yöntemini dağıttığınız olay yöntemine yönelik bir işaretçi:

- Yerel C++ olayları: *SourceClass* olay kaynak sınıfıdır ve *eventmethod* olaydır.

- COM olayları: *SourceClass* olay kaynağı arabirimidir ve *eventmethod* , yöntemlerinden biridir.

- Yönetilen olaylar: *SourceClass* olay kaynak sınıfıdır ve *eventmethod* olaydır.

*arayüz*<br/>
Yalnızca [event_receiver](../windows/attributes/event-receiver.md) özniteliğinin *layout_dependent* parametresine sahip olan com olay alıcıları için, *alıcıya*eklenmekte olan arabirim adı **`true`** .

*kaynaktaki*<br/>
Olay kaynağı örneğine yönelik bir işaretçi. `type`' De belirtilen koda bağlı olarak `event_receiver` , *kaynak* aşağıdakilerden biri olabilir:

- Yerel bir olay kaynağı nesne işaretçisi.

- `IUnknown`Tabanlı işaretçi (com kaynağı).

- Yönetilen bir nesne işaretçisi (yönetilen olaylar için).

*&ReceiverClass:: Handleryöntemi*<br/>
Bir olaya bağlamak için olay işleyicisi yöntemine yönelik bir işaretçi. İşleyici bir sınıfın yöntemi veya aynı başvuru olarak belirtilir; sınıf adını belirtmezseniz, **`__hook`** sınıfının çağrıldığı sınıf olduğunu varsayar.

- Yerel C++ olayları: *ReceiverClass* , olay alıcısı sınıfıdır ve `HandlerMethod` işleyicidir.

- COM olayları: *ReceiverClass* olay alıcı arabirimidir ve `HandlerMethod` işleyicilerinden biridir.

- Yönetilen olaylar: *ReceiverClass* , olay alıcı sınıfıdır ve `HandlerMethod` işleyicidir.

*bildiği*<br/>
Seçim Olay alıcısı sınıfının bir örneğine yönelik işaretçi. Bir alıcı belirtmezseniz, varsayılan olarak çağrılan alıcı sınıfı veya yapısıdır **`__hook`** .

## <a name="usage"></a>Kullanım

, Olay alıcı sınıfının dışında, Main dahil herhangi bir işlev kapsamında kullanılabilir.

## <a name="remarks"></a>Açıklamalar

Bir olay alıcısındaki iç işlevi kullanarak **`__hook`** bir işleyici metodunu bir olay yöntemiyle ilişkilendirir veya kanca. Belirtilen işleyici daha sonra kaynak belirtilen olayı harekete geçirirse çağrılır. Birkaç işleyiciyi tek bir olaya veya birkaç olayı tek bir işleyiciye bağlayabilirsiniz.

Öğesinin iki biçimi vardır **`__hook`** . Genellikle [event_receiver](../windows/attributes/event-receiver.md) özniteliğinin *LAYOUT_DEPENDENT* parametresinin olduğu com olay alıcıları için, çoğu durumda, örneğin ilk (dört bağımsız değişken) formunu kullanabilirsiniz **`false`** .

Bu gibi durumlarda, metotlardan birinde bir olayı tetiketmeden önce bir arabirimdeki tüm yöntemleri bir arada bir bağlama gerekmez; Yalnızca olayı işleyen yöntemin takılması gerekir. **`__hook`** Yalnızca *layout_dependent* **= true**olan bir com olay alıcısı için ikinci (iki bağımsız değişken) biçimini kullanabilirsiniz.

**`__hook`** uzun bir değer döndürür. Sıfır olmayan dönüş değeri bir hata oluştuğunu belirtir (yönetilen olaylar bir özel durum oluşturur).

Derleyici bir olayın varlığını denetler ve olay imzasının temsilci imzasıyla kabul eder.

COM olayları hariç **`__hook`** **`__unhook`** olur ve olay alıcısı dışında çağrılabilir.

Kullanmanın alternatifi **`__hook`** + = işlecini kullanmaktır.

Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz. [olayı](../extensions/event-cpp-component-extensions.md).

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Örnekler için bkz. [Yerel C++ Içindeki olay işleme](../cpp/event-handling-in-native-cpp.md) ve [com 'da olay işleme](../cpp/event-handling-in-com.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Olay Işleme](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)<br/>
