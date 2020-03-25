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
ms.openlocfilehash: 2a259b80b941e37e0c3040ad55894c114fe4bc82
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160534"
---
# <a name="__unhook"></a>__unhook

Bir olaydan bir işleyici yönteminin ilişkilendirmesini kaldırın.

## <a name="syntax"></a>Sözdizimi

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

**&** *SourceClass* `::` *eventmethod* olay işleyicisi yönteminin üstünden geri yüklediğiniz olay yöntemine yönelik bir işaretçi:

- Yerel C++ olaylar: *SourceClass* olay kaynak sınıfıdır ve *eventmethod* olaydır.

- COM olayları: *SourceClass* olay kaynağı arabirimidir ve *eventmethod* , yöntemlerinden biridir.

- Yönetilen olaylar: *SourceClass* olay kaynak sınıfıdır ve *eventmethod* olaydır.

*interface*<br/>
Arabirim adı *alıcıdan*takılmış olan, yalnızca [event_receiver](../windows/attributes/event-receiver.md) özniteliğinin *layout_dependent* parametresinin **true**olduğu com olay alıcıları için.

*source*<br/>
Olay kaynağı örneğine yönelik bir işaretçi. `event_receiver`belirtilen kod `type` bağlı olarak, *kaynak* aşağıdakilerden biri olabilir:

- Yerel bir olay kaynağı nesne işaretçisi.

- `IUnknown`tabanlı işaretçi (COM kaynağı).

- Yönetilen bir nesne işaretçisi (yönetilen olaylar için).

**&** *ReceiverClass* `::`, bir olaydan geri dönmek için olay işleyicisi yöntemine yönelik bir işaretçi `HandlerMethod`. İşleyici bir sınıfın yöntemi veya aynı başvuru olarak belirtilir; sınıf adını belirtmezseniz **__unhook** , sınıfın çağrıldığı sınıfı kabul eder.

- Yerel C++ olaylar: *ReceiverClass* , olay alıcı sınıfıdır ve `HandlerMethod` işleyicidir.

- COM olayları: *ReceiverClass* olay alıcı arabirimidir ve `HandlerMethod` işleyicilerinden biridir.

- Yönetilen olaylar: *ReceiverClass* , olay alıcı sınıfıdır ve `HandlerMethod` işleyicidir.

*alıcı*(isteğe bağlı) olay alıcısı sınıfının bir örneğine yönelik bir işaretçi. Alıcı belirtmezseniz, varsayılan olarak **__unhook** çağrıldığı alıcı sınıfı veya yapısıdır.

## <a name="usage"></a>Kullanım

, Olay alıcı sınıfının dışında, Main dahil herhangi bir işlev kapsamında kullanılabilir.

## <a name="remarks"></a>Açıklamalar

Bir olay yöntemindeki bir işleyici yönteminin ilişkilendirmesini kaldırmak veya "unhook" için bir olay alıcısında iç işlev **__unhook** kullanın.

Üç **__unhook**biçimi vardır. Çoğu durumda ilk (dört bağımsız değişken) formunu kullanabilirsiniz. Yalnızca bir COM olay alıcısı için **__unhook** ikinci (iki bağımsız değişken) biçimini kullanabilirsiniz; Bu, tüm olay arabiriminin kancalarını kaldırır. Belirtilen kaynaktaki tüm temsilcilerin kancasını kaldırmak için üçüncü (bir bağımsız değişken) formu kullanabilirsiniz.

Sıfır olmayan bir dönüş değeri, bir hata oluştuğunu belirtir (yönetilen olaylar bir özel durum oluşturur).

Önceden bağlanmayan bir olay ve olay işleyicide **__unhook** çağırırsanız, hiçbir etkisi olmayacaktır.

Derleme zamanında, derleyici olayın varolduğunu doğrular ve belirtilen işleyiciyle parametre türü denetimi yapar.

COM olaylarının dışında, **__hook** ve **__unhook** olay alıcısının dışında çağrılabilir.

**__Unhook** kullanmanın alternatifi-= işlecini kullanmaktır.

Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz. [olayı](../extensions/event-cpp-component-extensions.md).

> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Örnekler için bkz. [com 'da](../cpp/event-handling-in-com.md) [yerel C++ ](../cpp/event-handling-in-native-cpp.md) ve olay İşlemede olay işleme.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
