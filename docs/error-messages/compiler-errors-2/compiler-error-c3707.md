---
title: Derleyici hatası C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 6faf035c0f4f68b10b187c56bea4cafc776998cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757962"
---
# <a name="compiler-error-c3707"></a>Derleyici hatası C3707

' function ': dispınterface yöntemi bir DISPID içermelidir

`dispinterface` yöntemi kullanıyorsanız, bunu bir `dispid`atamanız gerekir. Bu hatayı onarmak için, `dispinterface` yöntemine `dispid` atayın, örneğin, aşağıdaki örnekteki yöntemde `id` özniteliğini açıklama ekleyerek. Daha fazla bilgi için bkz. [dispınterface](../../windows/dispinterface.md) ve [ID](../../windows/id.md)özniteliklerini inceleyin.

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
