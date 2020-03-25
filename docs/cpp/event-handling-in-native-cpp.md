---
title: Yerel C++'da Olay İşleme
ms.date: 05/07/2019
helpviewer_keywords:
- event handling [C++]
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
ms.openlocfilehash: cc9265cd3f9f400e2880405019e4d2c9a934f10a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180088"
---
# <a name="event-handling-in-native-c"></a>Yerel C++'da Olay İşleme

Yerel C++ olay işlemede, sırasıyla [event_source](../windows/attributes/event-source.md) ve [event_receiver](../windows/attributes/event-receiver.md) özniteliklerini kullanarak bir olay kaynağı ve olay alıcısı ayarlarsınız `type`=`native`belirtin. Bu öznitelikler, olayları harekete geçirme ve yerel, COM dışı bağlamdaki olayları işlemek için uygulanan sınıflara izin verir.

## <a name="declaring-events"></a>Olayları Bildirme

Bir olay kaynak sınıfında yöntemi bir olay olarak bildirmek için yöntem bildiriminde [__event](../cpp/event.md) anahtar sözcüğünü kullanın. Yöntemi bildirdiğinizden, ancak tanımlamadığınızdan emin olun; Bunu yapmak için derleyici hatası oluşturur, çünkü derleyici bir olaya yapıldığında yöntemi örtük olarak tanımlar. Yerel olaylar sıfır veya daha fazla parametreye sahip Yöntemler olabilir. Dönüş türü void veya herhangi bir tamsayı türü olabilir.

## <a name="defining-event-handlers"></a>Olay Işleyicilerini tanımlama

Bir olay alıcısı sınıfında, işleyecekleri olayla eşleşen imzalı yöntemler (dönüş türleri, çağrı kuralları ve bağımsız değişkenler) olan olay işleyicilerini tanımlarsınız.

## <a name="hooking-event-handlers-to-events"></a>Olay İşleyicilerini Olaylara Takma

Ayrıca, olay işleyicilerindeki olayların ilişkilendirmesini kaldırmak için olayları olay işleyicileri ve [__unhook](../cpp/unhook.md) ilişkilendirmek üzere [__hook](../cpp/hook.md) iç işlev bir olay alıcısı sınıfında kullanılır. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.

## <a name="firing-events"></a>Olayları Tetikleme

Bir olayı tetiklemesi için olay kaynak sınıfında bir olay olarak belirtilen yöntemi çağırmanız yeterlidir. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.

### <a name="native-c-event-code"></a>Yerel C++ olay kodu

Aşağıdaki örnek, yerel C++olarak bir olayın nasıl tetikleneceği gösterilmektedir. Örneği derlemek ve çalıştırmak için koddaki açıklamalara bakın.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// evh_native.cpp
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

### <a name="output"></a>Çıktı

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../cpp/event-handling.md)
