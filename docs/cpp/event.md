---
title: __event
ms.date: 11/04/2016
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
ms.openlocfilehash: c1c9fa5a6df4cbb1c18e5d5406bdde0197d155b2
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91498830"
---
# <a name="__event"></a>__event

Bir olayı bildirir.

## <a name="syntax"></a>Sözdizimi

```
__event method-declarator;
__event __interface interface-specifier;
__event member-declarator;
```

## <a name="remarks"></a>Açıklamalar

Anahtar sözcüğü **`__event`** bir yöntem bildirimine, bir arabirim bildirimine veya bir veri üyesi bildirimine uygulanabilir. Ancak, **`__event`** iç içe bir sınıfın bir üyesini nitelemek için anahtar sözcüğünü kullanamazsınız.

Olay kaynağınız ve alıcılarınızın yerel C++, COM veya yönetilen (.NET Framework) olmasına bağlı olarak, aşağıdaki yapıları olay olarak kullanabilirsiniz:

|Yerel C++|COM|Yönetilen (.NET Framework)|
|------------------|---------|--------------------------------|
|Yöntem|—|method|
|—|arabirim|—|
|—|—|veri üyesi|

Bir işleyici yöntemini bir olay yöntemiyle ilişkilendirmek için bir olay alıcısında [__hook](../cpp/hook.md) kullanın. Anahtar sözcüğüyle bir olay oluşturduktan sonra **`__event`** , olay çağrıldığında daha sonra bu olaya yönelik tüm olay işleyicileri çağırılır.

**`__event`** Yöntem bildiriminde bir tanım olamaz; bir tanım örtülü olarak oluşturulur, bu nedenle olay yöntemi sıradan bir yöntem gibi çağrılabilir.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="native-events"></a>Yerel olaylar

Yerel olaylar yöntemlerdir. Dönüş türü genellikle HRESULT veya **`void`** , dahil olmak üzere herhangi bir tamsayı türü olabilir **`enum`** . Bir olay bir integral dönüş türü kullandığında, bir olay işleyicisi sıfır dışında bir değer döndürdüğünde bir hata koşulu tanımlanır, bu durumda, yükseltilen olay diğer temsilcileri çağıracaktır.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Örnek kod için bkz. [Yerel C++ Içindeki olay işleme](../cpp/event-handling-in-native-cpp.md) .

## <a name="com-events"></a>COM Olayları

COM olayları arayüzlerdir. Bir olay kaynak arabirimindeki bir yöntemin parametreleri, çok noktaya yayın sırasında yararlı olmadığından, parametreler içinde olmalıdır (ancak bu, daha *iyi* bir *şekilde* zorlanmaz). Bir *Out* parametresi kullanırsanız düzey 1 uyarısı verilir.

Dönüş türü genellikle HRESULT veya **`void`** , dahil olmak üzere herhangi bir integral türü olabilir **`enum`** . Bir olay integral dönüş türü kullandığında ve olay işleyicisi sıfır dışında bir değer döndürdüğünde bir hata durumudur, bu durumda, yapılmakta olan olay diğer temsilcilere çağrı durdurur. Derleyicinin otomatik olarak bir olay kaynağı arabirimini oluşturulan IDL 'de [kaynak](../windows/attributes/source-cpp.md) olarak işaretyacağını unutmayın.

[__İnterface](../cpp/interface.md) anahtar sözcüğü **`__event`** bir com olay kaynağı için her zaman gereklidir.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Örnek kod için bkz. [com 'Da olay işleme](../cpp/event-handling-in-com.md) .

## <a name="managed-events"></a>Yönetilen olaylar

Yeni sözdiziminde olayları kodlama hakkında daha fazla bilgi için bkz. [olayı](../extensions/event-cpp-component-extensions.md).

Yönetilen olaylar veri üyeleri veya yöntemlerdir. Bir olayla birlikte kullanıldığında, bir temsilcinin dönüş türü [ortak dil belirtimiyle](/dotnet/standard/language-independence-and-language-independent-components)uyumlu olmalıdır. Olay işleyicisinin dönüş türü, temsilcinin dönüş türüyle aynı olmalıdır. Temsilciler hakkında daha fazla bilgi için bkz. [Temsilciler ve olaylar](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md). Yönetilen bir olay bir veri üyesiyse, türü bir temsilciye yönelik bir işaretçi olmalıdır.

.NET Framework, bir veri üyesini bir yöntemin kendisi (yani, `Invoke` karşılık gelen temsilcinin yöntemi) gibi kabul edebilirsiniz. Yönetilen bir olay veri üyesini bildirmek için temsilci türünü önceden tanımlamanız gerekir. Bunun aksine, yönetilen bir olay yöntemi zaten tanımlı değilse karşılık gelen yönetilen temsilciyi örtülü olarak tanımlar. Örneğin, aşağıdaki gibi bir olay gibi bir olay değeri bildirebilirsiniz `OnClick` :

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

Yönetilen bir olayı örtük olarak bildirirken, olay işleyicileri eklendiğinde veya kaldırıldığında çağrılabilecek ekleme ve kaldırma erişimcileri belirtebilirsiniz. Ayrıca, olayı sınıfın dışından çağıran (Başlatan) yöntemi tanımlayabilirsiniz.

## <a name="example-native-events"></a>Örnek: yerel olaylar

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

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[Olay Işleme](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)
