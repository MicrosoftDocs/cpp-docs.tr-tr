---
title: __Event | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abfda38c6c35c3e7172b187c89fa78bed5ee7616
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948125"
---
# <a name="event"></a>__event
Bir olayı bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
__event method-declarator;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Anahtar sözcüğü **__event** yöntem bildiriminde, arabirim bildirimiyle veya bir veri üyesi bildirimi uygulanabilir. Ancak, kullanamazsınız **__event** iç içe geçmiş bir sınıf üyesi nitelemek için anahtar sözcüğü.  
  
 Olay kaynağı ve alıcı yerel C++, COM veya yönetilen (.NET Framework) olup bağlı olarak, olaylar olarak aşağıdaki yapıları kullanabilirsiniz:  
  
|Yerel C++|COM|Yönetilen (.NET Framework)|  
|------------------|---------|--------------------------------|  
|Yöntem|—|yöntemi|  
|—|arabirim|—|  
|—|—|veri üyesi|  
  
 Kullanım [__hook](../cpp/hook.md) işleyicisi yöntemi olay yöntemi ile ilişkilendirmek için bir olay alıcısı'nda. Bir olayla oluşturduktan sonra unutmayın **__event** anahtar sözcüğü, daha sonra o olaya kancalandı tüm olay işleyicileri çağrılacağı olay çağrıldığında.  
  
 Bir **__event** yöntem bildiriminde bir tanıma sahip olamaz; olay yöntemi herhangi bir sıradan yöntemi gibi çağrılabilen için bir tanım örtük olarak, oluşturulur.  
  
> [!NOTE]
>  Şablonlu bir alan veya yapı, olay içeremez.  
  
## <a name="native-events"></a>Yerel olayları  
 Yerel olayları yöntemlerdir. Dönüş türü genellikle HRESULT olduğu veya **void**, ancak herhangi bir tamsayı türü olabilir dahil olmak üzere bir **enum**. Bir olay bir integral dönüş türü kullandığında, bir hata durumu bir olay işleyicisi diğer temsilcileri çalışması gerçekleştirilen olayı çağırır sıfır olmayan bir değer döndürdüğünde tanımlanır.  
  
```cpp 
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 Bkz: [olay işleme yerel C++'ta](../cpp/event-handling-in-native-cpp.md) örnek kod için.  
  
## <a name="com-events"></a>COM Olayları  
 COM olayları arabirimdir. Olay kaynağı arabirim içindeki bir yönteminin parametreleri olmalıdır `in` parametreleri (ancak bu titizlikle zorunlu değildir), çünkü bir `out` parametresi, çok noktaya yayın olduğunda kullanışlı değildir. Düzey 1 uyarısı kullanırsanız verilecek bir `out` parametresi.  
  
 Dönüş türü genellikle HRESULT olduğu veya **void**, ancak herhangi bir tamsayı türü olabilir dahil olmak üzere **enum**. Bir olay bir integral dönüş türü kullanır ve bir olay işleyicisi sıfır olmayan bir değer döndürür çalışması gerçekleştirilen olay diğer temsilcileri çağrıları iptal ettiğinde, bir hata koşulu olur. Derleyicinin otomatik olarak bir olay kaynağı arabirim olarak işaretlemek Not bir [kaynak](../windows/source-cpp.md) oluşturulan IDL içinde.  
  
 [__İnterface](../cpp/interface.md) anahtar sözcüğü sonra gerekli her zaman **__event** bir COM olay kaynağı.  
  
```cpp 
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 Bkz: [com'da olay işleme](../cpp/event-handling-in-com.md) örnek kod için.  
  
## <a name="managed-events"></a>Yönetilen olaylar  
 Yeni sözdiziminde olayları kodlama hakkında daha fazla bilgi için bkz: [olay](../windows/event-cpp-component-extensions.md).  
  
 Yönetilen olaylar, veri üyeleri veya yöntemleri şunlardır. Bir olay ile kullanıldığında, bir temsilcinin dönüş türü ile uyumlu olmalıdır [ortak dil belirtimi](/dotnet/standard/language-independence-and-language-independent-components). Olay işleyicisi dönüş türünü temsilcinin dönüş türü eşleşmelidir. Temsilciler hakkında daha fazla bilgi için bkz. [Temsilciler ve olaylar](../dotnet/delegates-and-events.md). Yönetilen bir olay bir veri üyesi ise, bir temsilci için bir işaretçi türü olmalıdır.  
  
 .NET Framework, bir yöntemi gibi bir veri üyesi davranabilir (diğer bir deyişle, `Invoke` , karşılık gelen bir temsilci yöntemi). Yönetilen bir olay veri üyesi bildirmek için temsilci türüyle önceden gerekir. Buna karşılık, yönetilen bir olay yöntemi, örtük olarak zaten tanımlı değilse karşılık gelen yönetilen temsilci tanımlar. Örneğin, bir olay değeri gibi bildirebilirsiniz `OnClick` aşağıdaki gibi bir olay olarak:  
  
```cpp 
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 Örtük olarak yönetilen bir olay bildirirken belirtebileceğiniz ekleme ve kaldırma olay işleyicileri eklendiğinde veya kaldırıldığında çağrılır erişimcileri. De (başlatır) çağıran yöntemi tanımlayabilirsiniz olay kaynağından bir sınıfın dışında.  
  
## <a name="example-native-events"></a>Örnek: Yerel olayları  
  
```cpp 
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## <a name="example-com-events"></a>Örnek: COM olayları  
  
```cpp 
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
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Olay işleme](../cpp/event-handling.md)   
 [event_source](../windows/event-source.md)   
 [event_receiver](../windows/event-receiver.md)   
 [__hook](../cpp/hook.md)   
 [__unhook](../cpp/unhook.md)   
 [__raise](../cpp/raise.md)