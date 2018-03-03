---
title: __Event | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __event_cpp
- __event
dev_langs:
- C++
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4750d156ef4f0f817e1eecec1f4a0842fc229046
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="event"></a>__event
Bir olayı bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Anahtar sözcüğü `__event` bir yöntem bildirimi, bir arabirim bildiriminde ya da bir veri üyesi bildiriminde uygulanabilir. Ancak, kullanamazsınız `__event` iç içe geçmiş sınıf üyesi nitelemek için anahtar sözcüğü.  
  
 Olay kaynağı ve alıcı yerel C++, COM ya da yönetilen (.NET Framework) olmanıza bağlı olarak, olaylar olarak aşağıdaki yapıları kullanabilirsiniz:  
  
|Yerel C++|COM|Yönetilen (.NET Framework)|  
|------------------|---------|--------------------------------|  
|Yöntem|—|yöntemi|  
|—|arabirim|—|  
|—|—|veri üyesi|  
  
 Kullanım [__hook](../cpp/hook.md) bir işleyici yöntemi bir olay yöntemi ile ilişkilendirmek için olay alıcı içinde. Bir olay oluşturduktan sonra unutmayın `__event` anahtar sözcüğü, daha sonra bu olaya sayfaya tüm olay işleyicileri çağrılır olay çağrıldığında.  
  
 Bir `__event` yöntem bildirimi tanımı olamaz; herhangi bir sıradan yöntemi değilmiş gibi olay yöntemi çağrılabilir için bir tanım örtük olarak, oluşturulur.  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="native-events"></a>Yerel olayları  
 Yöntemleri yerel olaylardır. Dönüş türü genellikle `HRESULT` veya `void`, ancak herhangi bir tam sayı türü de dahil olmak üzere bir `enum`. Bir olay ayrılmaz bir dönüş türü kullandığında, olay işleyici diğer temsilcileri durumda gerçekleştirilen olay numarayı arayacaktır sıfır olmayan bir değer döndürdüğünde bir hata koşulu tanımlanır.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 Bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md) örnek kod için.  
  
## <a name="com-events"></a>COM Olayları  
 COM arabirimleri olaylardır. Olay kaynağı arabirimdeki bir yöntem parametrelerini olmalıdır **içinde** parametreleri (ancak bu titizlikle zorunlu değildir), çünkü bir **çıkışı** parametresi yararlı çok noktaya yayın değil. Kullanırsanız, bir düzey 1 uyarı veren bir **çıkışı** parametresi.  
  
 Dönüş türü genellikle `HRESULT` veya `void`, ancak herhangi bir tam sayı türü de dahil olmak üzere `enum`. Bir olay ayrılmaz bir dönüş türü kullanır ve bir olay işleyicisi sıfır olmayan bir değer döndürür durumda gerçekleştirilen olay diğer temsilcileri çağrıları durdurur bir hata koşulu olur. Derleyici bir olay kaynağı arabirimi olarak otomatik olarak işaretleyecektir Not bir [kaynak](../windows/source-cpp.md) oluşturulan IDL içinde.  
  
 [__İnterface](../cpp/interface.md) anahtar sözcüğü gereklidir her zaman sonra `__event` COM olay kaynağı için.  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 Bkz: [olay işleme COM içinde](../cpp/event-handling-in-com.md) örnek kod için.  
  
## <a name="managed-events"></a>Yönetilen olayları  
 Yeni sözdiziminde olayları kodlama hakkında daha fazla bilgi için bkz: [olay](../windows/event-cpp-component-extensions.md).  
  
 Veri üyeleri veya yöntemlerini bunun yönetilen olaylardır. Bir olay ile kullanıldığında, bir temsilci dönüş türü ile uyumlu olmalıdır [ortak dil belirtimi](/dotnet/standard/language-independence-and-language-independent-components). Olay işleyicisinin dönüş türü temsilci dönüş türü eşleşmelidir. Temsilciler üzerinde daha fazla bilgi için bkz: [Temsilciler ve olaylar](../dotnet/delegates-and-events.md). Yönetilen bir olay veri üyesi ise, bir temsilci için bir işaretçi türü olmalıdır.  
  
 .NET Framework'teki bir yöntem değilmiş gibi bir veri üyesi davranabilirsiniz (diğer bir deyişle, `Invoke` karşılık gelen temsilci yöntemi). Yönetilen olay veri üyesi bildirmek için temsilci türü önceden gerekir. Buna karşılık, zaten tanımlanmazsa, bir yönetilen olay yöntemi karşılık gelen yönetilen temsilci örtük olarak tanımlar. Örneğin, bir olay değeri gibi bildirebilir `OnClick` aşağıdaki gibi bir olay olarak:  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 Örtük olarak yönetilen bir olay bildirirken belirtebilirsiniz ekleyin ve olay işleyicileri eklendiğinde veya kaldırıldığında yükleyen çağrılacağı erişimciler kaldırın. (Başlatır) çağıran yöntemi de tanımlayabilirsiniz etkinlikten sınıfı dışında.  
  
## <a name="example-native-events"></a>Örnek: Yerel olayları  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## <a name="example-com-events"></a>Örnek: COM olayları  
  
```  
// EventHandling_COM_Event.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT MyEvent();  
};  
 [ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]  
class CSource : public IEventSource {  
public:  
   __event __interface IEventSource;  
   HRESULT FireEvent() {  
      __raise MyEvent();  
      return S_OK;  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Olay işleme](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)