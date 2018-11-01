---
title: Derleyici Hatası C3705
ms.date: 11/04/2016
f1_keywords:
- C3705
helpviewer_keywords:
- C3705
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
ms.openlocfilehash: 8a1a5a7c3c54742f6952f6885a70fd5c1dcf6e0f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571164"
---
# <a name="compiler-error-c3705"></a>Derleyici Hatası C3705

'function': olay arabirimi bulunamıyor

COM olayları kullanmak için bir olay arabirimi tanımlamanız gerekir. Unutmayın `#include` aşağıdaki örnekte gösterilen ATL üstbilgi dosyalarını satırlarını COM olayları kullanmak için gereklidir. Bu hatayı düzeltmek için tanımına ilişkin açıklamayı kaldırır `IEvents` örnek kodda arabirimi.

Aşağıdaki örnek, C3705 oluşturur:

```
// C3705.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(dll, name="idid", uuid="12341234-1234-1234-1234-123412341234")];

// Uncomment the following 4 lines to resolve.
// [object, uuid("00000000-0000-0000-0000-000000000003")]
// __interface IEvents : IUnknown {
//    HRESULT event1([in] int i);
// };

[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IBase {
   HRESULT fireEvents();
};

[coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000002")]
class CEventSrc : public IBase {
public:
   __event __interface IEvents;   // C3705 uncomment IEvents to resolve
   HRESULT fireEvents() {
      HRESULT hr = IEvents_event1(123);
      return hr;
   }
};
```