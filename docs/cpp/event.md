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
ms.openlocfilehash: f8935408c6e9b43347d4ad6088505a461e254ae2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366299"
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

__event anahtar **kelimesi** yöntem bildirimine, arabirim bildirimine veya veri üye bildirimine uygulanabilir. Ancak, iç içe bir sınıfın bir üyesini hak kazanmak için **__event** anahtar sözcük kullanamazsınız.

Etkinlik kaynağınızın ve alıcınızın yerel C++, COM veya yönetilen (.NET Framework) olup olmadığına bağlı olarak, aşağıdaki yapıları olay olarak kullanabilirsiniz:

|Yerli C++|COM|Yönetilen (.NET Framework)|
|------------------|---------|--------------------------------|
|Yöntem|—|method|
|—|arabirim|—|
|—|—|veri üyesi|

İşleyici yöntemini olay yöntemiyle ilişkilendirmek için olay alıcısında [__hook](../cpp/hook.md) kullanın. **__event** anahtar sözcüğüyle bir olay oluşturduktan sonra, olay çağrıldığında bu olaya daha sonra bağlanan tüm olay işleyicilerinin çağrılacağını unutmayın.

**__event** yöntemi bildiriminin bir tanımı olamaz; bir tanım örtülü olarak oluşturulur, bu nedenle olay yöntemi sıradan bir yöntem gibi çağrılabilir.

> [!NOTE]
> Şablonlu bir alan veya yapı, olay içeremez.

## <a name="native-events"></a>Yerel Etkinlikler

Yerel olaylar yöntemdir. İade türü genellikle HRESULT veya **geçersizdir,** ancak bir **enum**da dahil olmak üzere herhangi bir integral türü olabilir. Bir olay integral bir iade türü kullandığında, bir olay işleyicisi sıfır olmayan bir değer verdiğinde bir hata koşulu tanımlanır ve bu durumda yükseltilen olay diğer temsilcileri çağırır.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Örnek kod için [Yerel C++'da Olay İşleme'ye](../cpp/event-handling-in-native-cpp.md) bakın.

## <a name="com-events"></a>COM Olayları

COM olayları arabirimlerdir. Olay kaynağı arabirimindeki bir yöntemin parametreleri *parametrelerde* olmalıdır (ancak bu kesinlikle zorlanmaz), çünkü çoklu döküm yaparken *bir çıkış* parametresi yararlı değildir. Bir *çıkış* parametresi kullanırsanız, düzey 1 uyarısı verilir.

İade türü genellikle HRESULT veya **geçersizdir,** ancak **enum**dahil olmak üzere herhangi bir integral türü olabilir. Bir olay integral bir iade türü kullandığında ve bir olay işleyicisi sıfır olmayan bir değer döndürdüğünde, bu bir hata koşuludur ve bu durumda yükseltilen olay diğer temsilcilere çağrıları iptal eder. Derleyicinin oluşturulan IDL'de bir olay kaynağı arabirimini otomatik olarak [kaynak](../windows/attributes/source-cpp.md) olarak işaretlemeyeceğini unutmayın.

[__interface](../cpp/interface.md) anahtar sözcüğü, com olay kaynağı için **__event** sonra her zaman gereklidir.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Örnek kod için [COM'da Olay İşleme'ye](../cpp/event-handling-in-com.md) bakın.

## <a name="managed-events"></a>Yönetilen Etkinlikler

Yeni sözdiziminde kodlama olayları hakkında bilgi için [olaya](../extensions/event-cpp-component-extensions.md)bakın.

Yönetilen olaylar veri üyeleri veya yöntemleridir. Bir olayla kullanıldığında, bir temsilcinin dönüş türü [Ortak Dil Belirtimi](/dotnet/standard/language-independence-and-language-independent-components)ile uyumlu olmalıdır. Olay işleyicisinin dönüş türü, temsilcinin dönüş türüyle eşleşmelidir. Temsilciler hakkında daha fazla bilgi [için, Bkz. Temsilciler ve Etkinlikler.](../dotnet/delegates-and-events.md) Yönetilen bir olay bir veri üyesiise, türü bir temsilci için bir işaretçi olmalıdır.

.NET Framework'de, bir veri üyesine bir yöntemin kendisiymisgibi davranabilirsiniz (diğer bir deyişle, `Invoke` karşılık gelen temsilciyöntemi). Yönetilen bir olay veri üyesini bildirmek için temsilci türünü önceden tanımlamanız gerekir. Buna karşılık, yönetilen bir olay yöntemi, zaten tanımlanmamışsa, ilgili yönetilen temsilciyi dolaylı olarak tanımlar. Örneğin, olay gibi `OnClick` bir olay değerini aşağıdaki gibi bildirebilirsiniz:

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

Yönetilen bir olayı dolaylı olarak bildirirken, olay işleyicileri eklendiğinde veya kaldırıldığında çağrılacak olan eklenti ve kaldır ıcılarını belirtebilirsiniz. Olayı sınıfın dışından çağıran (yükselten) yöntemi de tanımlayabilirsiniz.

## <a name="example-native-events"></a>Örnek: Yerel Olaylar

```cpp
// EventHandling_Native_Event.cpp
// compile with: /c
[event_source(native)]
class CSource {
public:
   __event void MyEvent(int nValue);
};
```

## <a name="example-com-events"></a>Örnek: COM Etkinlikleri

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
[Olay Yönetimi](../cpp/event-handling.md)<br/>
[event_source](../windows/attributes/event-source.md)<br/>
[event_receiver](../windows/attributes/event-receiver.md)<br/>
[__hook](../cpp/hook.md)<br/>
[__unhook](../cpp/unhook.md)<br/>
[__raise](../cpp/raise.md)
