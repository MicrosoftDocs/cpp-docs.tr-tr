---
title: Yerel C++'da Olay İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- event handling [C++], Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
ms.openlocfilehash: 93bfcc93c680618ea3a51eabd145548a4f47563a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58772338"
---
# <a name="event-handling-in-native-c"></a>Yerel C++'da Olay İşleme

Yerel C++ olay işleme, kullanarak bir olay kaynağı ve olay alıcı [event_source](../windows/attributes/event-source.md) ve [event_receiver](../windows/attributes/event-receiver.md) sırasıyla belirten öznitelikleri `type` =`native`. Bu öznitelikler, sınıfların olayları tetiklemesine ve olayları yerel, COM olmayan bir bağlamda işlemek için uygulanmadan izin verin.

## <a name="declaring-events"></a>Olayları Bildirme

Bir olay kaynağı sınıfında kullanın [__event](../cpp/event.md) yöntem bildiriminde yöntemi bir olay olarak bildirmek için anahtar sözcüğü. Yöntem bildirdiğinizden emin olun, ancak bunu tanımlamaz; Bunu yapmak için bir olayı yapıldığında derleyici yöntemi örtük olarak tanımlıyor çünkü bir derleyici hatası oluşturur. Yerel olayları, sıfır veya daha fazla parametrelere sahip yöntemleri olabilir. Dönüş türü void veya herhangi bir tamsayı türü olabilir.

## <a name="defining-event-handlers"></a>Olay işleyicisi tanımlama

Bir olay alıcısı sınıfında, işleyecekleri olayla eşleşen imzalı yöntemler (dönüş türleri, çağrı kuralları ve bağımsız değişkenler) olan olay işleyicilerini tanımlarsınız.

## <a name="hooking-event-handlers-to-events"></a>Olay İşleyicilerini Olaylara Takma

Ayrıca bir olay alıcısı sınıfında, iç işlevini [__hook](../cpp/hook.md) olayları olay işleyicileriyle ilişkilendirmek için ve [__unhook](../cpp/unhook.md) olayları olay işleyicileri'öğesinin ilişkilendirmesini kaldırmak. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.

## <a name="firing-events"></a>Olayları Tetikleme

Bir olay harekete geçirmek için yalnızca bir olay olarak olay kaynağı sınıfı bildirilen yöntemi çağırın. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.

### <a name="native-c-event-code"></a>Yerel C++ olay kodu

Aşağıdaki örnek, yerel C++'ta bir olay harekete gösterilmektedir. Örneği derlemek ve çalıştırmak için koddaki açıklamalara bakın.

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

### <a name="output"></a>Çıkış

```Output
MyHandler2 was called with value 123.
MyHandler1 was called with value 123.
```

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../cpp/event-handling.md)