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
ms.openlocfilehash: 221ffc30a9b8a40c44f8009dfa511b72aa160e01
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337559"
---
# <a name="__unhook"></a>__unhook

Bir olaydan işleyici yöntemini ayırAr.

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

**&***SourceClass* `::` *EventMethod* Olay işleyicisi yöntemini çıkartabileceğiniz olay yöntemine işaretçi:

- Yerel C++ olayları: *SourceClass* olay kaynağı sınıfıdır ve *EventMethod* olaydır.

- COM olayları: *SourceClass* olay kaynak arabirimi ve *EventMethod* onun yöntemlerinden biridir.

- Yönetilen olaylar: *SourceClass* olay kaynak sınıfı ve *EventMethod* olaydır.

*arabirim*<br/>
Arabirim adı *alıcıdan*çözülen, yalnızca [event_receiver](../windows/attributes/event-receiver.md) özniteliğinin *layout_dependent* parametresinin **doğru**olduğu COM olay alıcıları için.

*Kaynak*<br/>
Olay kaynağının bir örneğine işaretçi. Belirtilen koda `type` bağlı `event_receiver`olarak , *kaynak* aşağıdakilerden biri olabilir:

- Yerel olay kaynağı nesne işaretçisi.

- Tabanlı `IUnknown`işaretçi (COM kaynağı).

- Yönetilen nesne işaretçisi (yönetilen olaylar için).

**&***ReceiverClass* `::` `HandlerMethod` A işaretçisi olay işleyicisi yöntemiiçin bir olaydan çözülecek. İşleyici, bir sınıfın yöntemi veya aynı başvuru olarak belirtilir; sınıf adını belirtmezseniz, **__unhook** sınıfın çağrıldığı sınıf olduğunu varsayar.

- Yerel C++ olayları: *ReceiverClass* olay `HandlerMethod` alıcısı sınıfıdır ve işleyicidir.

- COM olayları: *ReceiverClass* olay alıcıarabirimidir ve `HandlerMethod` işleyicilerinden biridir.

- Yönetilen olaylar: *ReceiverClass* olay alıcısı sınıfıdır ve `HandlerMethod` işleyicidir.

*alıcı*(isteğe bağlı) Olay alıcısı sınıfının bir örneğine işaretçi. Bir alıcı belirtmezseniz, varsayılan değer **__unhook** çağrıldığı alıcı sınıfı veya yapısıdır.

## <a name="usage"></a>Kullanım

Olay alıcısı sınıfının dışında, ana da dahil olmak üzere herhangi bir işlev kapsamında kullanılabilir.

## <a name="remarks"></a>Açıklamalar

Olay yöntemini bir işleyici yöntemini dağıtmak veya "kancayı çıkarmak" için olay alıcısında **__unhook** içsel işlevi kullanın.

**__unhook**üç şekli vardır. Çoğu durumda ilk (dört bağımsız değişken) formu kullanabilirsiniz. Yalnızca bir COM olay alıcısı için ikinci (iki bağımsız) **__unhook** biçimini kullanabilirsiniz; bu, tüm olay arabirimini unhooks. Belirtilen kaynaktan tüm temsilcileri çıkarmak için üçüncü (tek bağımsız) formu kullanabilirsiniz.

Sıfır olmayan bir geri dönüş değeri bir hata oluştuğunu gösterir (yönetilen olaylar bir özel durum atar).

Zaten bağımlı olmayan bir olay ve olay işleyicisi üzerinde **__unhook** çağırırsanız, hiçbir etkisi olmayacaktır.

Derleme zamanında derleyici olayın var olduğunu doğrular ve belirtilen işleyiciyle parametre türü denetimi yapar.

COM olayları dışında, **__hook** ve **__unhook** olay alıcısı dışında çağrılabilir.

**__unhook** kullanmanın alternatifi -= işleci kullanmaktır.

Yeni sözdiziminde yönetilen olayların kodlanması hakkında bilgi için [olaya](../extensions/event-cpp-component-extensions.md)bakın.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Örnekler için [Yerel C++'da Olay İşleme](../cpp/event-handling-in-native-cpp.md) ve [COM'da Olay İşleme'ye](../cpp/event-handling-in-com.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__event](../cpp/event.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__raise](../cpp/raise.md)
