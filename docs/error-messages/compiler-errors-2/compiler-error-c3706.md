---
title: Derleyici hatası C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: 810ec59a814b04349913648fb49a03eb63912cd9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757988"
---
# <a name="compiler-error-c3706"></a>Derleyici hatası C3706

' function ': COM olaylarını başlatmak için bir COM arabirimi olmalıdır

COM olaylarını başlatmak için kullandığınız olay arabirimi bir COM arabirimi olmalıdır. Bu durumda, arabirim bir görsel C++ özniteliği kullanılarak tanımlanmalıdır ya da #import embedded_idl özniteliğiyle bir tür kitaplığından [#import](../../preprocessor/hash-import-directive-cpp.md) kullanılarak içeri aktarılmalıdır.

Aşağıdaki örnekte gösterilen ATL üstbilgi dosyalarının `#include` satırlarının COM olaylarını kullanmak için gerekli olduğunu unutmayın. Bu hatayı onarmak için aşağıdaki özniteliklerden birini arabirim tanımına uygulayarak bir COM arabirimi `IEvents` (olay arabirimi) yapın: [nesne](../../windows/object-cpp.md), [çift](../../windows/dual.md)veya [dispınterface](../../windows/dispinterface.md).

Bir arabirim MıDL tarafından oluşturulan bir üstbilgi dosyasından ise, derleyici bunu bir COM arabirimi olarak tanımaz.

Aşağıdaki örnek C3706 oluşturur:

```cpp
// C3706.cpp
// compile with: /c
// C3706 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following line to resolve.
// [object, uuid="12341234-1234-1234-1234-123412341237"]
__interface IEvents : IUnknown {
   HRESULT event1(/*[in]*/ int i);   // uncomment [in]
};

[dual, uuid="12341234-1234-1234-1234-123412341235"]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid="12341234-1234-1234-1234-123412341236"]
class CEventSrc : public IBase {
   public:
   __event __interface IEvents;

   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```
