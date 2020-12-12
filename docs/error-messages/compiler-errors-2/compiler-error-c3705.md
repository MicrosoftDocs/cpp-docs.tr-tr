---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3705'
title: Derleyici hatası C3705
ms.date: 11/04/2016
f1_keywords:
- C3705
helpviewer_keywords:
- C3705
ms.assetid: 8361017d-5782-4214-a9d7-e9825fd29bc8
ms.openlocfilehash: 50030c47ae629607110c6820d863f5aa1358e8f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168377"
---
# <a name="compiler-error-c3705"></a>Derleyici hatası C3705

' function ': olay arabirimi bulunamıyor

COM olaylarını kullanmak için bir olay arabirimi tanımlamanız gerekir. `#include`Aşağıdaki örnekte GÖSTERILEN ATL üstbilgi dosyalarının SATıRLARıNıN com olaylarını kullanmak için gerekli olduğunu unutmayın. Bu hatayı düzeltemedi, `IEvents` örnek kodda arabirim tanımının açıklamasını kaldırın.

Aşağıdaki örnek C3705 oluşturur:

```cpp
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
