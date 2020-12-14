---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3706'
title: Derleyici hatası C3706
ms.date: 11/04/2016
f1_keywords:
- C3706
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
ms.openlocfilehash: e4dcb65d29e24ae40bc311f1d4229edca173e916
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241865"
---
# <a name="compiler-error-c3706"></a>Derleyici hatası C3706

' function ': COM olaylarını başlatmak için bir COM arabirimi olmalıdır

COM olaylarını başlatmak için kullandığınız olay arabirimi bir COM arabirimi olmalıdır. Bu durumda, arabirim bir Visual C++ özniteliği kullanılarak tanımlanmalıdır veya #import embedded_idl özniteliğiyle bir tür kitaplığından [#import](../../preprocessor/hash-import-directive-cpp.md) kullanılarak içeri aktarılmalıdır.

`#include`Aşağıdaki örnekte GÖSTERILEN ATL üstbilgi dosyalarının SATıRLARıNıN com olaylarını kullanmak için gerekli olduğunu unutmayın. Bu hatayı onarmak için, `IEvents` arabirim tanımına aşağıdaki özniteliklerden birini uygulayarak BIR com arabirimi oluşturun (olay arabirimi): [nesne](../../windows/attributes/object-cpp.md), [çift](../../windows/attributes/dual.md)veya [dispınterface](../../windows/attributes/dispinterface.md).

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
