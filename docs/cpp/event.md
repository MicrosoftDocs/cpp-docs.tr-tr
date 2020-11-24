---
title: __event
description: Yerel olay işleme için Microsoft C++ uzantısı anahtar sözcüğünü nasıl kullanacağınızı öğrenin `__event` .
ms.date: 11/20/2020
f1_keywords:
- __event_cpp
- __event
helpviewer_keywords:
- __event keyword [C++]
- events [C++], __event
ms.openlocfilehash: 1678699d9b66c1a49dd5ca2bb019a6229c37a031
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483157"
---
# <a name="__event-keyword"></a>`__event` sözcükle

Bir olayı bildirir.

> [!NOTE]
> Yerel C++ içindeki olay öznitelikleri standart C++ ile uyumsuzdur. Uyumluluk modunu belirttiğinizde derlenirler [`/permissive-`](../build/reference/permissive-standards-conformance.md) .

## <a name="syntax"></a>Syntax

> **`__event`** *`member-function-declarator`* **`;`**\
> **`__event`** **`__interface`** *`interface-specifier`* **`;`**\
> **`__event`** *`data-member-declarator`* **`;`**

## <a name="remarks"></a>Açıklamalar

Microsoft 'a özgü anahtar sözcüğü **`__event`** bir üye işlevi bildirimine, bir arabirim bildirimine veya bir veri üyesi bildirimine uygulanabilir. Ancak, **`__event`** iç içe bir sınıfın bir üyesini nitelemek için anahtar sözcüğünü kullanamazsınız.

Olay kaynağınız ve alıcılarınızın yerel C++, COM veya yönetilen (.NET Framework) olmasına bağlı olarak, aşağıdaki yapıları olay olarak kullanabilirsiniz:

| Yerel C++ | COM | Yönetilen (.NET Framework) |
|--|--|--|
| üye işlevi | - | method |
| - | arabirim | - |
| - | - | veri üyesi |

Bir [`__hook`](../cpp/hook.md) işleyici üye işlevini bir olay üyesi işleviyle ilişkilendirmek için bir olay alıcısında kullanın. Anahtar sözcüğüyle bir olay oluşturduktan sonra **`__event`** , olay çağrıldığında daha sonra bu olaya yapılan tüm olay işleyicileri çağırılır.

**`__event`** Üye işlev bildiriminde bir tanım olamaz; bir tanım örtülü olarak oluşturulur, bu nedenle olay üyesi işlevi herhangi bir normal üye işlevmiş gibi çağrılabilir.

> [!NOTE]
> Şablonlu bir sınıf veya yapı olay içeremez.

## <a name="native-events"></a>Yerel olaylar

Yerel olaylar üye işlevleridir. Dönüş türü genellikle `HRESULT` veya **`void`** dahil olmak üzere herhangi bir tamsayı türü olabilir **`enum`** . Bir olay integral dönüş türü kullandığında, bir olay işleyicisi sıfır dışında bir değer döndürdüğünde bir hata koşulu tanımlanır. Bu durumda, oluşturulan olay diğer temsilcileri çağırır.

```cpp
// Examples of native C++ events:
__event void OnDblClick();
__event HRESULT OnClick(int* b, char* s);
```

Örnek kod için bkz. [Yerel C++ Içindeki olay işleme](../cpp/event-handling-in-native-cpp.md) .

## <a name="com-events"></a>COM olayları

COM olayları arayüzlerdir. Bir olay kaynağı arabirimindeki üye işlevin *parametreleri parametrelerde olmalıdır* , ancak dikkatli bir şekilde zorlanmamalıdır. Bunun nedeni, çok noktaya yayın sırasında bir *Out* parametresinin yararlı olmaması olabilir. Bir *Out* parametresi kullanırsanız düzey 1 uyarısı verilir.

Dönüş türü genellikle `HRESULT` veya **`void`** dahil olmak üzere herhangi bir integral türü olabilir **`enum`** . Bir olay integral dönüş türü kullandığında ve olay işleyicisi sıfır dışında bir değer döndürdüğünde, bu bir hata durumudur. Oluşturulan olay, diğer temsilcilere yapılan çağrıları iptal eder. Derleyici, otomatik olarak bir olay kaynağı arabirimini [`source`](../windows/attributes/source-cpp.md) oluşturulan IDL içindeki bir olarak işaretler.

[`__interface`](../cpp/interface.md)Anahtar sözcüğü **`__event`** bir com olay kaynağı için her zaman gereklidir.

```cpp
// Example of a COM event:
__event __interface IEvent1;
```

Örnek kod için bkz. [com 'Da olay işleme](../cpp/event-handling-in-com.md) .

## <a name="managed-events"></a>Yönetilen olaylar

Yeni sözdiziminde olayları kodlama hakkında daha fazla bilgi için bkz. [olayı](../extensions/event-cpp-component-extensions.md).

Yönetilen olaylar veri üyeleri veya üye işlevleridir. Bir olayla birlikte kullanıldığında, bir temsilcinin dönüş türü [ortak dil belirtimiyle](/dotnet/standard/language-independence-and-language-independent-components)uyumlu olmalıdır. Olay işleyicisinin dönüş türü, temsilcinin dönüş türüyle aynı olmalıdır. Temsilciler hakkında daha fazla bilgi için bkz. [Temsilciler ve olaylar](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md). Yönetilen bir olay bir veri üyesiyse, türü bir temsilciye yönelik bir işaretçi olmalıdır.

.NET Framework, bir veri üyesini bir yöntemin kendisi (yani, `Invoke` karşılık gelen temsilcinin yöntemi) gibi kabul edebilirsiniz. Bunu yapmak için, yönetilen bir olay veri üyesini bildirmek üzere temsilci türünü önceden tanımlayın. Bunun aksine, yönetilen bir olay yöntemi zaten tanımlı değilse karşılık gelen yönetilen temsilciyi örtülü olarak tanımlar. Örneğin, aşağıdaki gibi bir olay gibi bir olay değeri bildirebilirsiniz `OnClick` :

```cpp
// Examples of managed events:
__event ClickEventHandler* OnClick;  // data member as event
__event void OnClick(String* s);  // method as event
```

Yönetilen bir olayı örtük olarak bildirirken, `add` `remove` olay işleyicileri eklendiğinde veya kaldırıldığında çağrılan erişimcileri belirtebilirsiniz. Ayrıca, olayı sınıfın dışından çağıran (Başlatan) üye işlevini de tanımlayabilirsiniz.

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

[Lerimi](../cpp/keywords-cpp.md)\
[Olay işleme](../cpp/event-handling.md)\
[`event_source`](../windows/attributes/event-source.md)\
[`event_receiver`](../windows/attributes/event-receiver.md)\
[`__hook`](../cpp/hook.md)\
[`__unhook`](../cpp/unhook.md)\
[`__raise`](../cpp/raise.md)
