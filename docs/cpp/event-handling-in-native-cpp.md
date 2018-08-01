---
title: Yerel C++ dilinde olay işleme | Microsoft Docs
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
ms.openlocfilehash: b58bf010be4b05d8c9f024954b51e8cdb176cd4d
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405788"
---
# <a name="event-handling-in-native-c"></a>Yerel C++'da Olay İşleme

Yerel C++ olay işlemede, ayarladığınız kullanarak bir olay kaynağı ve olay alıcı [event_source](../windows/event-source.md) ve [event_receiver](../windows/event-receiver.md) sırasıyla belirten öznitelikleri `type` = `native`. Bu öznitelikler, sınıfların olayları tetiklemesine ve olayları yerel, COM olmayan bir bağlamda işlemek için uygulanmadan izin verin.

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