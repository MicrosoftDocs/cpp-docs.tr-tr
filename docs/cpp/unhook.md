---
title: __unhook
description: Yerel olay işleme için Microsoft C++ uzantısı anahtar sözcüğünü nasıl kullanacağınızı öğrenin `__unhook` .
ms.date: 11/04/2016
f1_keywords:
- __unhook
- __unhook_cpp
helpviewer_keywords:
- event handlers [C++], dissociating events
- __unhook keyword [C++]
ms.openlocfilehash: 74f8b814ea23c5513b7b73bf90ef59984742a266
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483327"
---
# <a name="__unhook-keyword"></a>`__unhook` sözcükle

Bir işleyici yönteminin bir olaydan ilişkilendirmesini kaldırır.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

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

### <a name="parameters"></a>Parametreler

*`&SourceClass::EventMethod`*\
Olay işleyicisi yönteminin üstünden geri yüklediğiniz olay yöntemine yönelik bir işaretçi:

- Yerel C++ olayları: *`SourceClass`* olay kaynak sınıfıdır ve *`EventMethod`* olaydır.

- COM olayları: *`SourceClass`* olay kaynağı arabirimidir ve *`EventMethod`* yöntemlerinden biridir.

- Yönetilen olaylar: *`SourceClass`* olay kaynak sınıfıdır ve *`EventMethod`* olaydır.

*`interface`*\
Arabirim adı, yalnızca özniteliğin *layout_dependent* PARAMETRESININ olduğu com olay alıcıları için *alıcısından* takılmıyor [`event_receiver`](../windows/attributes/event-receiver.md) **`true`** .

*`source`*\
Olay kaynağı örneğine yönelik bir işaretçi. `type`' De belirtilen koda bağlı olarak `event_receiver` , *kaynak* şu türlerden biri olabilir:

- Yerel bir olay kaynağı nesne işaretçisi.

- `IUnknown`Tabanlı işaretçi (com kaynağı).

- Yönetilen bir nesne işaretçisi (yönetilen olaylar için).

*`&ReceiverClass::HandlerMethod`* Olay işleyicisi yönteminin bir olaydan kaldırılması için bir işaretçi. İşleyici bir sınıfın yöntemi veya aynı başvuru olarak belirtilir; sınıf adını belirtmezseniz, **`__unhook`** sınıfının çağrıldığı bir sınıf olduğunu varsayar.

- Yerel C++ olayları: *`ReceiverClass`* olay alıcı sınıfıdır ve `HandlerMethod` işleyicidir.

- COM olayları: *`ReceiverClass`* olay alıcı arabirimidir ve *`HandlerMethod`* işleyicilerinden biridir.

- Yönetilen olaylar: *`ReceiverClass`* olay alıcı sınıfıdır ve *`HandlerMethod`* işleyicidir.

*`receiver`* seçim Olay alıcısı sınıfının bir örneğine yönelik işaretçi. Alıcı belirtmezseniz, varsayılan olarak çağrılan alıcı sınıfı veya yapısıdır **`__unhook`** .

## <a name="usage"></a>Kullanım

`main`, Olay alıcısı sınıfının dışında, herhangi bir işlev kapsamında kullanılabilir.

## <a name="remarks"></a>Açıklamalar

Bir olay **`__unhook`** dosyasındaki bir işleyici yönteminin ilişkisini kaldırmak veya "geri almak" için bir olay alıcısında iç işlevi kullanın.

Üç biçimi vardır **`__unhook`** . Çoğu durumda ilk (dört bağımsız değişken) formunu kullanabilirsiniz. Yalnızca bir COM olay alıcısı için ikinci (iki bağımsız değişken) biçimini kullanabilirsiniz **`__unhook`** ; tüm olay arabiriminin kancalarını kaldırır. Belirtilen kaynaktaki tüm temsilcilerin kancasını kaldırmak için üçüncü (bir bağımsız değişken) formu kullanabilirsiniz.

Sıfır olmayan bir dönüş değeri, bir hata oluştuğunu belirtir (yönetilen olaylar bir özel durum oluşturur).

**`__unhook`** Zaten kullanıma alınmış olmayan bir olay ve olay işleyicide çağrı yaparsanız, hiçbir etkisi olmayacaktır.

Derleme zamanında, derleyici olayın varolduğunu doğrular ve belirtilen işleyiciyle parametre türü denetimi yapar.

**`__hook`** **`__unhook`** Com olayları dışında, olay alıcısını çağırabilir ve dışında bırakabilirsiniz.

Kullanmanın alternatifi **`__unhook`** -= işlecini kullanmaktır.

Yeni sözdiziminde yönetilen olayları kodlama hakkında daha fazla bilgi için bkz. [olayı](../extensions/event-cpp-component-extensions.md).

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="example"></a>Örnek

Örnekler için bkz. [Yerel C++ Içindeki olay işleme](../cpp/event-handling-in-native-cpp.md) ve [com 'da olay işleme](../cpp/event-handling-in-com.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Lerimi](../cpp/keywords-cpp.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__event`](../cpp/event.md)\
[`__hook`](../cpp/hook.md)\
[`__raise`](../cpp/raise.md)
