---
title: Olay işleme yerel C++ | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b233c8329119753e5753e19fd641c6bea5d8e42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="event-handling-in-native-c"></a>Yerel C++'da Olay İşleme

Yerel C++ olay işlemede kullanarak bir olay kaynağı ve olay alıcıyı ayarlamak [event_source](../windows/event-source.md) ve [event_receiver](../windows/event-receiver.md) sırasıyla belirten öznitelikleri `type` = `native`. Bu öznitelikler bunlar olayları yangın ve yerel, COM olmayan bağlamda olayları işlemek için uygulanır sınıfları sağlar.

## <a name="declaring-events"></a>Olayları Bildirme

Bir olay kaynağı sınıfında kullanın [__event](../cpp/event.md) yöntemi bir olay olarak bildirmek için bir yöntem bildirimi on anahtar sözcüğü. Yöntem bildirin emin olun, ancak bunu tanımlamaz; Bunu yapmak için bir olay yapıldığında derleyici yöntemi örtük olarak tanımladığından derleyici hatası oluşturur. Yerel olayları sıfır veya daha fazla parametre yöntemleriyle olabilir. Dönüş türü void veya herhangi bir tamsayı türü olabilir.  
  
## <a name="defining-event-handlers"></a>Olay işleyicileri tanımlama

Bir olay alıcısı sınıfında, işleyecekleri olayla eşleşen imzalı yöntemler (dönüş türleri, çağrı kuralları ve bağımsız değişkenler) olan olay işleyicilerini tanımlarsınız.  
  
## <a name="hooking-event-handlers-to-events"></a>Olay İşleyicilerini Olaylara Takma  

Ayrıca bir olay alıcı sınıfta iç işlevini [__hook](../cpp/hook.md) olayları olay işleyicileri ile ilişkilendirilecek ve [__unhook](../cpp/unhook.md) olay işleyicileri olayların ilişkilendirmesini kaldırmak. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.  
  
## <a name="firing-events"></a>Olayları Tetikleme  

Bir olay tetikleyin için yalnızca bir olay Olay kaynağı sınıf bildirilen yöntemini çağırın. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.  
  
### <a name="native-c-event-code"></a>Yerel C++ olay kodu  

Aşağıdaki örnek, yerel C++'ta bir olay tetikleyin gösterilmektedir. Örneği derlemek ve çalıştırmak için koddaki açıklamalara bakın.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.

[Olay İşleme](../cpp/event-handling.md)  

