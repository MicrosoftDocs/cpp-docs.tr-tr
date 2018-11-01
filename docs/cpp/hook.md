---
title: __hook
ms.date: 11/04/2016
f1_keywords:
- __hook_cpp
helpviewer_keywords:
- __hook keyword [C++]
- event handlers [C++], connecting events to
ms.assetid: f4cabb10-d293-4c0e-a1d2-4745ef9cc22c
ms.openlocfilehash: a8a7fb6a88fb22fee5f5f8ec8c0dc215479c62fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489745"
---
# <a name="hook"></a>__hook

İle bir olay işleyicisi yöntemi ilişkilendirir.

## <a name="syntax"></a>Sözdizimi

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

*& SourceClass::EventMethod*<br/>
Olay işleyicisi yöntemine bağlama olay yöntemi için bir işaretçi:

- Yerel C++ olayları: *SourceClass* olay kaynak sınıfı ve *oluşur* etkinliğidir.

- COM olayları: *SourceClass* olay kaynağı arabirim ve *oluşur* yöntemlerinden biridir.

- Yönetilen olaylar: *SourceClass* olay kaynak sınıfı ve *oluşur* etkinliğidir.

*interface*<br/>
İçin kancalandı arabirim adı *alıcı*, yalnızca, COM Olay alıcıları için *layout_dependent* parametresinin [event_receiver](../windows/event-receiver.md) özniteliktir **true**.

*source*<br/>
Olay kaynağının bir örneği için bir işaretçi. Kod bağlı olarak `type` belirtilen `event_receiver`, *kaynak* aşağıdakilerden biri olabilir:

- Yerel olay kaynak nesne işaretçisi.

- Bir `IUnknown`-işaretçi (COM kaynak) bağlı.

- Bir yönetilen nesne işaretçisi (yönetilen olaylar).

*& ReceiverClass::HandlerMethod*<br/>
Olay işleyicisi yöntemi, bir olay kancalandı için bir işaretçi. İşleyici, bir sınıf ya da aynı başvuru yöntemi olarak belirtilir; sınıf adı belirtmezseniz, **__hook** sınıfı, bunu çağrılır olmasını varsayar.

- Yerel C++ olayları: *ReceiverClass* olay alıcısı sınıfına olduğu ve `HandlerMethod` işleyicidir.

- COM olayları: *ReceiverClass* olay alıcısı arabirim ve `HandlerMethod` ona ait işleyiciyi biridir.

- Yönetilen olaylar: *ReceiverClass* olay alıcısı sınıfına olduğu ve `HandlerMethod` işleyicidir.

*Alıcı*<br/>
(İsteğe bağlı) Olay alıcısı sınıfına örneğine bir işaretçi. Bir alıcı belirtmezseniz, alıcı sınıfın veya yapının, varsayılan değer **__hook** çağrılır.

## <a name="usage"></a>Kullanım

Ana olay alıcısı sınıfına dışında da dahil olmak üzere, herhangi bir işlev kapsamı kullanımda olabilir.

## <a name="remarks"></a>Açıklamalar

İç işlevini **__hook** içinde veya bir olay yöntemi ile bir işleyici yöntemi kanca ilişkilendirmek için bir olay alıcısı. Belirtilen olay kaynağı çektiğinde belirtilen işleyici sonra çağrılır. Birden çok tek bir olay işleyicilere bağlayın veya tek bir işleyici çeşitli olaylara bağlama.

İki tür vardır **__hook**. Çoğu durumda, ilk (dört bağımsız değişken) form özellikle, COM Olay alıcıları için kullanabileceğiniz *layout_dependent* parametresinin [event_receiver](../windows/event-receiver.md) özniteliği **false** .

Bu gibi durumlarda yöntemlerinden biri olan bir olayı tetiklemeden önce tüm bir arabirimdeki yöntemlerde kanca gerekmez; Olay işleme yöntemi yalnızca yayılmış gerekir. İkinci (iki bağımsız) biçiminde kullanabileceğiniz **__hook** yalnızca, bir COM olay alıcısının için *layout_dependent* **= true**.

**__hook** bir long değeri döndürür. Sıfır dışında bir dönüş değeri (yönetilen olaylar throw bir özel durum) bir hata oluştuğunu gösterir.

Derleyici bir olay varlığını denetler ve olay imza temsilcinin imzasıyla kabul eder.

COM olayları hariç **__hook** ve **__unhook** olay alıcısı çağrılabilir.

Kullanmaya alternatif **__hook** += işlecini kullanmaktır.

Yeni sözdiziminde yönetilen olaylar kodlama hakkında daha fazla bilgi için bkz: [olay](../windows/event-cpp-component-extensions.md).

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md) ve [com'da olay işleme](../cpp/event-handling-in-com.md) örnekleri için.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[Olay İşleme](../cpp/event-handling.md)<br/>
[event_source](../windows/event-source.md)<br/>
[event_receiver](../windows/event-receiver.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)<br/>
