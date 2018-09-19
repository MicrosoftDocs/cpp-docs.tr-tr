---
title: Derleyici Hatası C3706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3706
dev_langs:
- C++
helpviewer_keywords:
- C3706
ms.assetid: d20a33eb-d625-46c5-ac87-32075a590d07
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbebf5752a9ed42ea4af8d3a13e45c78fc1753ec
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110516"
---
# <a name="compiler-error-c3706"></a>Derleyici Hatası C3706

'function': COM olaylarını başlatmak için bir COM arabirimi olması gerekir

COM olaylarını başlatmak için kullandığınız olay arabirim bir COM arabirimi olması gerekir. Bu durumda, arabirim ya da Visual C++ özniteliği kullanılarak tanımlanmalıdır veya kullanılarak içe [#import](../../preprocessor/hash-import-directive-cpp.md) gelen bir tür kitaplığı #import's embedded_idl özniteliğine sahip.

Unutmayın `#include` aşağıdaki örnekte gösterilen ATL üstbilgi dosyalarını satırlarını COM olayları kullanmak için gereklidir. Bu hatayı düzeltmek için olun `IEvents` (olay arabirimi) aşağıdakilerden birini uygulayarak bir COM arabirimi öznitelikleri için arabirim tanımı: [nesne](../../windows/object-cpp.md), [çift](../../windows/dual.md), veya [ dispinterface](../../windows/dispinterface.md).

Bir arabirim MIDL tarafından oluşturulan üstbilgi dosyası ise, derleyici bir COM arabirimi olarak bunu tanımaz.

Aşağıdaki örnek, C3706 oluşturur:

```
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