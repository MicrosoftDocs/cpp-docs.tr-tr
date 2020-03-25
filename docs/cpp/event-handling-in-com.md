---
title: COM'da Olay İşleme
ms.date: 11/04/2016
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
ms.openlocfilehash: d54470bdf4b2555b01993582a74f65505858f94b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189240"
---
# <a name="event-handling-in-com"></a>COM'da Olay İşleme

COM olay işlemede, [event_source](../windows/attributes/event-source.md) ve [event_receiver](../windows/attributes/event-receiver.md) özniteliklerini kullanarak, sırasıyla `type`=`com`belirterek bir olay kaynağı ve olay alıcısı ayarlarsınız. Bu öznitelikler uygulandıkları sınıfların olayları tetiklemesine ve olayları COM bağlantı noktalarıyla işlemesine olanak vermek için özel, dağılma ve ikili arabirimler için uygun kodu eklerler.

## <a name="declaring-events"></a>Olayları Bildirme

Bir olay kaynak sınıfında, bu arabirimin yöntemlerini olay olarak bildirmek için arabirim bildiriminde [__event](../cpp/event.md) anahtar sözcüğünü kullanın. Söz konusu arabirimin olayları, siz onları arabirim yöntemleri olarak çağırdığınızda tetiklenir. Olay arabirimlerindeki yöntemlerin sıfır veya daha fazla *parametresi olabilir (bunların hepsi parametrelerde olması* gerekir). Dönüş türü void veya herhangi bir tamsayı türü olabilir.

## <a name="defining-event-handlers"></a>Olay Işleyicilerini tanımlama

Bir olay alıcısı sınıfında, işleyecekleri olayla eşleşen imzalı yöntemler (dönüş türleri, çağrı kuralları ve bağımsız değişkenler) olan olay işleyicilerini tanımlarsınız. COM olayları için çağırma kurallarının eşleşmesi gerekmez; Ayrıntılar için aşağıdaki [Düzen BAĞıMLı com olaylarına](#vcconeventhandlingincomanchorlayoutdependentcomevents) bakın.

## <a name="hooking-event-handlers-to-events"></a>Olay İşleyicilerini Olaylara Takma

Ayrıca, olay işleyicilerindeki olayların ilişkilendirmesini kaldırmak için olayları olay işleyicileri ve [__unhook](../cpp/unhook.md) ilişkilendirmek üzere [__hook](../cpp/hook.md) iç işlev bir olay alıcısı sınıfında kullanılır. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.

> [!NOTE]
>  Genellikle, bir COM olay alıcısının olay kaynağı arabirim tanımlarına erişmesine izin vermek için iki teknik vardır. Birinci olarak, aşağıda gösterildiği gibi genel bir başlık dosyası paylaşmaktır. İkincisi, `embedded_idl` içeri aktarma niteleyicisi ile [#import](../preprocessor/hash-import-directive-cpp.md) kullanmaktır, böylece olay kaynak türü kitaplığı, öznitelik tarafından oluşturulan kodla korunan. tlh dosyasına yazılır.

## <a name="firing-events"></a>Olayları Tetikleme

Bir olayı tetiklemesi için, arabirim kaynak sınıfında **__event** anahtar sözcüğüyle belirtilen arabirimdeki bir yöntemi çağırmanız yeterlidir. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.

### <a name="com-event-code"></a>COM Olay Kodu

Aşağıdaki örnek, COM sınıfında bir olayın nasıl tetikleneceği gösterilmiştir. Örneği derlemek ve çalıştırmak için koddaki açıklamalara bakın.

```cpp
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

```cpp
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

```cpp
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

### <a name="output"></a>Çıktı

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

##  <a name="layout-dependent-com-events"></a><a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a>Düzene bağımlı COM olayları

Düzen bağımlılığı yalnızca COM programlamasında görülen bir sorundur. Yerli ve yönetilen olay işlemede, işleyicilerin imzaları (dönüş türü, çağrı kuralı ve bağımsız değişkenler) olaylarıyla eşleşmelidir, ancak işleyici adlarının olaylarla eşleşmesi gerekmez.

Ancak, COM olay işlemede, `event_receiver` *layout_dependent* parametresi **true**olarak ayarlandığında, ad ve imza eşleştirme zorlanır. Bu, olay alıcısındaki işleyicilerin adlarının ve imzalarının takıldıkları olayların adları ve imzalarıyla tam olarak eşleşmesi gerektiği anlamına gelir.

*Layout_dependent* **false**olarak ayarlandığında, çağırma kuralı ve depolama sınıfı (sanal, statik, vb.), tetikleme olayı yöntemi ile birleştirme yöntemleri (temsilcileri) arasında karışık ve eşleştirilebilir. *Layout_dependent*=**doğru**olması biraz daha etkilidir.

Örneğin, `IEventSource` aşağıdaki yöntemlere sahip olacak şekilde tanımlanır:

```cpp
[id(1)] HRESULT MyEvent1([in] int value);
[id(2)] HRESULT MyEvent2([in] int value);
```

Olay kaynağının aşağıdaki formda olduğunu varsayalım:

```cpp
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

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Olay İşleme](../cpp/event-handling.md)
