---
title: COM'da olay işleme
description: COM olay işleme için Microsoft C++ uzantılarını nasıl kullanacağınızı öğrenin.
ms.date: 11/20/2020
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
ms.openlocfilehash: 0c664f052fe211c88ad097c9d2617ec47f180eff
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483119"
---
# <a name="event-handling-in-com"></a>COM'da olay işleme

COM olay işlemede, [`event_source`](../windows/attributes/event-source.md) ve özniteliklerini kullanarak, sırasıyla belirterek bir olay kaynağı ve olay alıcısı ayarlarsınız [`event_receiver`](../windows/attributes/event-receiver.md) `type` = `com` . Bu öznitelikler özel, dağıtım ve çift arabirimler için uygun kodu ekler. Eklenen kod, öznitelikli sınıfların olayları tetiklemesi ve olayları COM bağlantı noktaları aracılığıyla işlemesini sağlar.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

## <a name="declaring-events"></a>Olayları bildirme

Bir olay kaynak sınıfında, [`__event`](../cpp/event.md) Bu arabirimin yöntemlerini olay olarak bildirmek için arabirim bildiriminde anahtar sözcüğünü kullanın. Söz konusu arabirimin olayları, siz onları arabirim yöntemleri olarak çağırdığınızda tetiklenir. Olay arabirimlerindeki yöntemlerin sıfır veya daha fazla *parametresi olabilir (bunların hepsi parametrelerde olması* gerekir). Dönüş türü void veya herhangi bir tamsayı türü olabilir.

## <a name="defining-event-handlers"></a>Olay işleyicilerini tanımlama

Olay işleyicilerini bir olay alıcısı sınıfında tanımlarsınız. Olay işleyicileri, işleyeceği olayla eşleşen imzalara (dönüş türleri, çağırma kuralları ve bağımsız değişkenler) sahip yöntemlerdir. COM olayları için çağırma kurallarının eşleşmesi gerekmez. Daha fazla bilgi için aşağıdaki [Düzen BAĞıMLı com olayları](#vcconeventhandlingincomanchorlayoutdependentcomevents) bölümüne bakın.

## <a name="hooking-event-handlers-to-events"></a>Olay işleyicilerini olaylara bağlama

Ayrıca bir olay alıcısı sınıfında, [`__hook`](../cpp/hook.md) olayları olay işleyicileriyle ilişkilendirmek ve [`__unhook`](../cpp/unhook.md) olay işleyicilerinden olayların ilişkisini kaldırmak için iç işlevi kullanırsınız. Bir olay işleyicisine birden fazla olay veya bir olaya birden fazla olay işleyicisi takabilirsiniz.

> [!NOTE]
> Genellikle, bir COM olay alıcısının olay kaynağı arabirim tanımlarına erişmesine izin vermek için iki teknik vardır. Birinci olarak, aşağıda gösterildiği gibi genel bir başlık dosyası paylaşmaktır. İkincisi, içeri aktarma niteleyicisi ile [#import](../preprocessor/hash-import-directive-cpp.md) kullanmaktır `embedded_idl` , böylece olay kaynak türü kitaplığı, öznitelik tarafından oluşturulan kodla korunan. tlh dosyasına yazılır.

## <a name="firing-events"></a>Olayları tetikleme

Bir olayı tetiklemesi için, arabirimde **`__event`** olay kaynak sınıfında anahtar sözcüğüyle belirtilen bir yöntemi çağırın. Olaya olay işleyicileri takılmışsa, işleyiciler çağırılır.

### <a name="com-event-code"></a>COM olay kodu

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

### <a name="output"></a>Çıkış

```Output
MyHandler1 was called with value 123.
MyHandler2 was called with value 123.
```

## <a name="layout-dependent-com-events"></a><a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> Düzene bağımlı COM olayları

Düzen bağımlılığı yalnızca COM programlamasında görülen bir sorundur. Yerel ve yönetilen olay işlemede, işleyicilerin imzaları (dönüş türü, çağırma kuralı ve bağımsız değişkenler) etkinlikleriyle eşleşmelidir, ancak işleyici adlarının olaylarıyla eşleşmesi gerekmez.

Ancak, COM olay işlemede, *`layout_dependent`* parametresini `event_receiver` olarak ayarladığınızda **`true`** , ad ve imza eşleştirme zorlanır. Olay alıcısındaki ve yerleşik olaylardaki işleyicilerin adları ve imzaları tam olarak eşleşmelidir.

*`layout_dependent`*, Olarak ayarlandığında **`false`** , çağırma kuralı ve depolama sınıfı (sanal, statik, vb.), tetikleme olayı yöntemi ile birleştirme yöntemleri (temsilcileri) arasında karışık ve eşleştirilebilir. Bu, sahip olmak biraz daha etkilidir *`layout_dependent`* = **`true`** .

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

[Olay işleme](../cpp/event-handling.md)
