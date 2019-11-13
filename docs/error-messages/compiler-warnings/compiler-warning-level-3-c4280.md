---
title: Derleyici Uyarısı (düzey 3) C4280
ms.date: 11/04/2016
f1_keywords:
- C4280
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
ms.openlocfilehash: 9936aa7b6baf0c1f94186aa4785490897d8606e2
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051719"
---
# <a name="compiler-warning-level-3-c4280"></a>Derleyici Uyarısı (düzey 3) C4280

' operator-> ', ' Type ' türü aracılığıyla kendinden özyinelemeli

Kodunuz, **operator->** kendisini çağırmak için yanlış izin veriyor.

Aşağıdaki örnek C4280 oluşturur:

```cpp
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```