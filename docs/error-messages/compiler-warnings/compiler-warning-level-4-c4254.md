---
title: Derleyici Uyarısı (düzey 4) C4254
ms.date: 11/04/2016
f1_keywords:
- c4254
helpviewer_keywords:
- C4254
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
ms.openlocfilehash: a100591d4a59664dd06bd2386942e4c92ffebac5
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991373"
---
# <a name="compiler-warning-level-4-c4254"></a>Derleyici Uyarısı (düzey 4) C4254

' operator ': ' type1 ' değerinden ' type2 ' öğesine dönüştürme, olası veri kaybı

Daha büyük bir bit alanı daha küçük bir bit alanına atandı. Veri kaybı olabilir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4254 oluşturur:

```cpp
// C4254.cpp
// compile with: /W4
#pragma warning(default: 4254)

struct X {
   int a : 20;
   int b : 12;
};

int main() {
   X *x = new X();
   x->b = 10;
   x->a = 4;
   x->a = x->b;    // OK
   x->b = x->a;    // C4254
};
```
