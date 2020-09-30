---
title: Derleyici hatası C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: a09bf080c72e154a37cec5cdb75e714c12dd7150
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507976"
---
# <a name="compiler-error-c3707"></a>Derleyici hatası C3707

' function ': dispınterface yöntemi bir DISPID içermelidir

Bir `dispinterface` yöntemi kullanırsanız, bunu atamanız gerekir `dispid` . Bu hatayı onarmak için, bir `dispid` `dispinterface` yöntemine atayın, örneğin, `id` Aşağıdaki örnekte bulunan yöntemine ait özniteliğin açıklamasını kaldırın. Daha fazla bilgi için bkz. [dispınterface](../../windows/attributes/dispinterface.md) ve [ID](../../windows/attributes/id.md)özniteliklerini inceleyin.

Aşağıdaki örnek C3707 oluşturur:

```cpp
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
