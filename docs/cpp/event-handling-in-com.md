---
title: "COM'da olay işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c57b8429a05ab3989dce318f4c16a58475560a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-in-com"></a>COM'da Olay İşleme
COM olay işlemede kullanarak bir olay kaynağı ve olay alıcıyı ayarlamak [event_source](../windows/event-source.md) ve [event_receiver](../windows/event-receiver.md) sırasıyla belirten öznitelikleri `type` = **com**. Bu öznitelikler uygulandıkları sınıfların olayları tetiklemesine ve olayları COM bağlantı noktalarıyla işlemesine olanak vermek için özel, dağılma ve ikili arabirimler için uygun kodu eklerler.  
  
## <a name="declaring-events"></a>Olayları Bildirme  
 Bir olay kaynağı sınıfında kullanın [__event](../cpp/event.md) bu arabirimin yöntemleri olayları olarak bildirmek için bir arabirim bildiriminde on anahtar sözcüğü. Söz konusu arabirimin olayları, siz onları arabirim yöntemleri olarak çağırdığınızda tetiklenir. Olay arabirimlerindeki yöntemleri, sıfır veya daha fazla parametre olabilir (tüm olacağı **içinde** parametreleri). Dönüş türü void veya herhangi bir tamsayı türü olabilir.  
  
## <a name="defining-event-handlers"></a>Olay işleyicileri tanımlama  
 Bir olay alıcısı sınıfında, işleyecekleri olayla eşleşen imzalı yöntemler (dönüş türleri, çağrı kuralları ve bağımsız değişkenler) olan olay işleyicilerini tanımlarsınız. COM olaylar için arama kuralları eşleşmesi gerekmez; bkz: [düzeni bağımlı COM olayları](#vcconeventhandlingincomanchorlayoutdependentcomevents) aşağıda Ayrıntılar için.  
  
## <a name="hooking-event-handlers-to-events"></a>Olay İşleyicilerini Olaylara Takma  
 Ayrıca bir olay alıcı sınıfta iç işlevini [__hook](../cpp/hook.md) olayları olay işleyicileri ile ilişkilendirilecek ve [__unhook](../cpp/unhook.md) olay işleyicileri olayların ilişkilendirmesini kaldırmak. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.  
  
> [!NOTE]
>  Genellikle, bir COM olay alıcısının olay kaynağı arabirim tanımlarına erişmesine izin vermek için iki teknik vardır. Birinci olarak, aşağıda gösterildiği gibi genel bir başlık dosyası paylaşmaktır. İkinci kullanmaktır [#import](../preprocessor/hash-import-directive-cpp.md) ile `embedded_idl` Niteleyici, böylece olay kaynağı tür kitaplığı, öznitelik oluşturulan kod korunur .tlh dosyasına yazılır alın.  
  
## <a name="firing-events"></a>Olayları Tetikleme  
 Bir olayı tetiklemek için yapmanız gereken yalnızca olay kaynağı sınıfında `__event` anahtar sözcüğü ile bildirilen arabirimde bir yöntemi çağırmaktır. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.  
  
### <a name="com-event-code"></a>COM Olay Kodu  
 Aşağıdaki örnek, COM sınıfında bir olayın nasıl tetikleneceği gösterilmiştir. Örneği derlemek ve çalıştırmak için koddaki açıklamalara bakın.  
  
```  
// evh_server.h  
#pragma once  
  
[ dual, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IEvents {  
   [id(1)] HRESULT MyEvent([in] int value);  
};  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT FireEvent();  
};  
  
class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;  
```  
  
 Ve ardından sunucu:  
  
```  
// evh_server.cpp  
// compile with: /LD  
// post-build command: Regsvr32.exe /s evh_server.dll  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include "evh_server.h"  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;   
  
   HRESULT FireEvent() {  
      __raise MyEvent(123);  
      return S_OK;  
   }  
};  
```  
  
 Sonra istemci:  
  
```  
// evh_client.cpp  
// compile with: /link /OPT:NOREF  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <stdio.h>  
#include "evh_server.h"  
  
[ module(name="EventReceiver") ];  
  
[ event_receiver(com) ]  
class CReceiver {  
public:  
   HRESULT MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   HRESULT MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   void HookEvent(IEventSource* pSource) {  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void UnhookEvent(IEventSource* pSource) {  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   // Create COM object  
   CoInitialize(NULL);  
   {  
      IEventSource* pSource = 0;  
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);  
      if (FAILED(hr)) {  
         return -1;  
      }  
  
      // Create receiver and fire event  
      CReceiver receiver;  
      receiver.HookEvent(pSource);  
      pSource->FireEvent();  
      receiver.UnhookEvent(pSource);  
   }  
   CoUninitialize();  
   return 0;  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
MyHandler1 was called with value 123.  
MyHandler2 was called with value 123.  
```  
  
##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a>Düzen bağımlı COM olayları  
 Düzen bağımlılığı yalnızca COM programlamasında görülen bir sorundur. Yerli ve yönetilen olay işlemede, işleyicilerin imzaları (dönüş türü, çağrı kuralı ve bağımsız değişkenler) olaylarıyla eşleşmelidir, ancak işleyici adlarının olaylarla eşleşmesi gerekmez.  
  
 Ayarladığınız zaman ancak COM olay işlemede, *layout_dependent* parametresinin **event_receiver** için **doğru**, ad ve imza eşleştirme zorlanır. Bu, olay alıcısındaki işleyicilerin adlarının ve imzalarının takıldıkları olayların adları ve imzalarıyla tam olarak eşleşmesi gerektiği anlamına gelir.  
  
 Zaman *layout_dependent* ayarlanır **yanlış**, arama kuralı ve depolama sınıfı (sanal, statik vb.) karışık ve tetikleme arasında eşleşen bir olay yöntemi ve hooking yöntemleri (kendi Temsilcileri). Sağlamak için biraz daha verimlidir *layout_dependent*=**doğru**.  
  
 Örneğin, `IEventSource` aşağıdaki yöntemlere sahip olacak şekilde tanımlanır:  
  
```  
[id(1)] HRESULT MyEvent1([in] int value);  
[id(2)] HRESULT MyEvent2([in] int value);  
```  
  
 Olay kaynağının aşağıdaki formda olduğunu varsayalım:  
  
```  
[coclass, event_source(com)]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;  
  
   HRESULT FireEvent() {  
      MyEvent1(123);  
      MyEvent2(123);  
      return S_OK;  
   }  
};  
```  
  
 Daha sonra, olay alıcısında, `IEventSource` içinde bir yönteme takılmış işleyicinin, onun adı ve imzasıyla eşleşmesi gerekir (aşağıdaki gibi):  
  
```  
[coclass, event_receiver(com, true)]  
class CReceiver {  
public:  
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1  
      ...  
   }  
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2  
      ...  
   }  
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)  
      ...  
   }  
   void HookEvent(IEventSource* pSource) {  
      __hook(IFace, pSource);  // Hooks up all name-matched events   
                               // under layout_dependent = true  
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid  
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid  
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Olay İşleme](../cpp/event-handling.md)