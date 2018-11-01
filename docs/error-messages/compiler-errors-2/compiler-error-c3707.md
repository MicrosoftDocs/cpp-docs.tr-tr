---
title: Derleyici Hatası C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 8a1525539c84ea427815a03057bb6d2f9213fec7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431121"
---
# <a name="compiler-error-c3707"></a>Derleyici Hatası C3707

'function': dispinterface yöntemi bir dispid içermelidir

Kullanıyorsanız bir `dispinterface` yöntemi atamanız gerekir, bir `dispid`. Bu hatayı düzeltmek için Ata bir `dispid` için `dispinterface` uncommenting tarafından Örneğin, bir yöntem `id` özniteliği aşağıdaki örnekte yöntemi. Daha fazla bilgi için öznitelikleri görmek [dispinterface](../../windows/dispinterface.md) ve [kimliği](../../windows/id.md).

Aşağıdaki örnek, C3707 oluşturur:

```
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```