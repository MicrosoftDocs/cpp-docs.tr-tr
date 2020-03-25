---
title: Derleyici Uyarısı (düzey 1) C4925
ms.date: 11/04/2016
f1_keywords:
- C4925
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
ms.openlocfilehash: defd60d02a8725b114b3901f8d70af87e27445c4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174641"
---
# <a name="compiler-warning-level-1-c4925"></a>Derleyici Uyarısı (düzey 1) C4925

' Method ': dispınterface yöntemi betikten çağrılamaz

Betik dilleri VT_BYREF ' ın ' parametresi oluşturamaz, yalnızca VT_BYREF ' Out ' parametreleri oluşturabilir.

Bu uyarıyı çözmek için bir diğer yol, parametreyi (tanım ve uygulamada) bir işaretçi türü haline getirir.

Aşağıdaki örnek C4925 oluşturur:

```cpp
// C4925.cpp
// compile with: /LD /W1
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[ module(name="Test")];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IDisp {
   [id(9)] void f([in] int*);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]
struct CDisp : IDisp {   // C4925
   void f(int*) {}
};
```
