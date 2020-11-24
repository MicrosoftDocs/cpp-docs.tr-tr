---
title: Yerel C++'da olay işleme
description: Yerel C++ olay işleme için Microsoft C++ uzantılarını nasıl kullanacağınızı öğrenin.
ms.date: 11/20/2020
helpviewer_keywords:
- event handling [C++]
ms.openlocfilehash: 5ad9128b7ff596674c3b08687b722c81b7a10aa8
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483184"
---
# <a name="event-handling-in-native-c"></a>Yerel C++'da olay işleme

Yerel C++ olay işlemede, sırasıyla [event_source](../windows/attributes/event-source.md) ve [event_receiver](../windows/attributes/event-receiver.md) özniteliklerini kullanarak bir olay kaynağı ve olay alıcısı ayarlarsınız `type` = `native` . Bu öznitelikler, üzerinde uygulandıkları sınıfların olayları harekete geçirme ve yerel, COM dışı bağlamdaki olayları işlemesini sağlar.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

## <a name="declaring-events"></a>Olayları bildirme

Bir olay kaynak sınıfında yöntemi bir [`__event`](../cpp/event.md) olay olarak bildirmek için yöntem bildiriminde anahtar sözcüğünü kullanın. Yöntemi bildirdiğinizden, ancak tanımlamadığınızdan emin olun. Bunu yaparsanız derleyici bir hata oluşturur, çünkü derleyici bir olaya yapıldığında yöntemi örtük olarak tanımlar. Yerel olaylar sıfır veya daha fazla parametreye sahip Yöntemler olabilir. Dönüş türü **`void`** veya herhangi bir tamsayı türü olabilir.

## <a name="defining-event-handlers"></a>Olay işleyicilerini tanımlama

Bir olay alıcısı sınıfında olay işleyicilerini tanımlarsınız. Olay işleyicileri, işleyeceği olayla eşleşen imzalara (dönüş türleri, çağırma kuralları ve bağımsız değişkenler) sahip yöntemlerdir.

## <a name="hooking-event-handlers-to-events"></a>Olay işleyicilerini olaylara bağlama

Ayrıca bir olay alıcısı sınıfında, [`__hook`](../cpp/hook.md) olayları olay işleyicileriyle ilişkilendirmek ve [`__unhook`](../cpp/unhook.md) olay işleyicilerinden olayların ilişkisini kaldırmak için iç işlevi kullanırsınız. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.

## <a name="firing-events"></a>Olayları tetikleme

Bir olayı tetiklemesi için olay kaynak sınıfında bir olay olarak belirtilen yöntemi çağırın. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.

### <a name="native-c-event-code"></a>Yerel C++ olay kodu

Aşağıdaki örnek, yerel C++ ' da bir olayın nasıl tetikleneceği gösterilmektedir. Örneği derlemek ve çalıştırmak için koddaki açıklamalara bakın. Visual Studio IDE 'de kodu derlemek için, seçeneğinin kapalı olduğunu doğrulayın **`/permissive-`** .

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// evh_native.cpp
// compile by using: cl /EHsc /W3 evh_native.cpp
#include <stdio.h>

[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};

[event_receiver(native)]
class CReceiver {
public:
   void MyHandler1(int nValue) {
      printf_s("MyHandler1 was called with value %d.\n", nValue);
   }

   void MyHandler2(int nValue) {
      printf_s("MyHandler2 was called with value %d.\n", nValue);
   }

   void hookEvent(CSource* pSource) {
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }

   void unhookEvent(CSource* pSource) {
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);
   }
};

int main() {
   CSource source;
   CReceiver receiver;

   receiver.hookEvent(&source);
   __raise source.MyEvent(123);
   receiver.unhookEvent(&source);
}
```

### <a name="output"></a>Çıkış

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>Ayrıca bkz.

[Olay işleme](../cpp/event-handling.md)
