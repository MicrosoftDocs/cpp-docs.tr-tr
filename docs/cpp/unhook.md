---
title: __unhook
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.assetid: 953a14f3-5199-459d-81e5-fcf015a19878
ms.openlocfilehash: 84df5ad0ff27e6b09134b0f92f14f8e9b6fdc817
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233580"
---
# <a name="__unhook"></a>__unhook

Bir olaydan bir işleyici yönteminin ilişkilendirmesini kaldırın.

## <a name="syntax"></a>Söz dizimi

```cpp
long  __unhook(
   &SourceClass::EventMethod,
   source,
   &ReceiverClass::HandlerMethod
   [, receiver = this]
);
long  __unhook(
   interface,
   source
);
long  __unhook(
   source
);
```

#### <a name="parameters"></a>Parametreler

**&***SourceClass* `::` *Eventmethod* Olay işleyicisi yönteminin üstünden geri yüklediğiniz olay yöntemine yönelik bir işaretçi:

- Yerel C++ olayları: *SourceClass* olay kaynak sınıfıdır ve *eventmethod* olaydır.

- COM olayları: *SourceClass* olay kaynağı arabirimidir ve *eventmethod* , yöntemlerinden biridir.

- Yönetilen olaylar: *SourceClass* olay kaynak sınıfıdır ve *eventmethod* olaydır.

*arayüz*<br/>
Arabirim adı *alıcıdan*takılmış olan, yalnızca [event_receiver](../windows/attributes/event-receiver.md) ÖZNITELIĞININ *layout_dependent* parametresinin olduğu com olay alıcıları için **`true`** .

*kaynaktaki*<br/>
Olay kaynağı örneğine yönelik bir işaretçi. `type`' De belirtilen koda bağlı olarak `event_receiver` , *kaynak* aşağıdakilerden biri olabilir:

- Yerel bir olay kaynağı nesne işaretçisi.

- `IUnknown`Tabanlı işaretçi (com kaynağı).

- Yönetilen bir nesne işaretçisi (yönetilen olaylar için).

**&***ReceiverClass* `::` Olay `HandlerMethod` işleyicisi yönteminin bir olaydan kaldırılması için bir işaretçi. İşleyici bir sınıfın yöntemi veya aynı başvuru olarak belirtilir; sınıf adını belirtmezseniz, **`__unhook`** sınıfının çağrıldığı sınıf olduğunu varsayar.

- Yerel C++ olayları: *ReceiverClass* , olay alıcısı sınıfıdır ve `HandlerMethod` işleyicidir.

- COM olayları: *ReceiverClass* olay alıcı arabirimidir ve `HandlerMethod` işleyicilerinden biridir.

- Yönetilen olaylar: *ReceiverClass* , olay alıcı sınıfıdır ve `HandlerMethod` işleyicidir.

*alıcı*(isteğe bağlı) olay alıcısı sınıfının bir örneğine yönelik bir işaretçi. Bir alıcı belirtmezseniz, varsayılan olarak çağrılan alıcı sınıfı veya yapısıdır **`__unhook`** .

## <a name="usage"></a>Kullanım

, Olay alıcı sınıfının dışında, Main dahil herhangi bir işlev kapsamında kullanılabilir.

## <a name="remarks"></a>Açıklamalar

Bir olay yöntemindeki iç işlevi kullanarak **`__unhook`** bir işleyici yönteminin ilişkilendirmesini kaldırın veya bir olay yönteminden "unhook".

Üç biçimi vardır **`__unhook`** . Çoğu durumda ilk (dört bağımsız değişken) formunu kullanabilirsiniz. Yalnızca bir COM olay alıcısı için ikinci (iki bağımsız değişken) biçimini kullanabilirsiniz **`__unhook`** ; Bu, tüm olay arabiriminin kancalarını kaldırır. Belirtilen kaynaktaki tüm temsilcilerin kancasını kaldırmak için üçüncü (bir bağımsız değişken) formu kullanabilirsiniz.

Sıfır olmayan bir dönüş değeri, bir hata oluştuğunu belirtir (yönetilen olaylar bir özel durum oluşturur).

**`__unhook`** Önceden bağlanmayan bir olay ve olay işleyicide çağrı yaparsanız, hiçbir etkisi olmayacaktır.

Derleme zamanında, derleyici olayın varolduğunu doğrular ve belirtilen işleyiciyle parametre türü denetimi yapar.

COM olayları hariç **`__hook`** **`__unhook`** olur ve olay alıcısı dışında çağrılabilir.

Kullanmanın alternatifi **`__unhook`** -= işlecini kullanmaktır.

Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz. [olayı](../extensions/event-cpp-component-extensions.md).

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Örnekler için bkz. [Yerel C++ Içindeki olay işleme](../cpp/event-handling-in-native-cpp.md) ve [com 'da olay işleme](../cpp/event-handling-in-com.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
