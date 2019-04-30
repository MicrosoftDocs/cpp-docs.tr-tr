---
title: Derleyici Uyarısı (düzey 1) C4927
ms.date: 11/04/2016
f1_keywords:
- C4927
helpviewer_keywords:
- C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
ms.openlocfilehash: 59a39e4e695fdd161135cd70a74e1f3f6518e361
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393460"
---
# <a name="compiler-warning-level-1-c4927"></a>Derleyici Uyarısı (düzey 1) C4927

hatalı dönüştürme; birden fazla kullanıcı tanımlı dönüştürme örtük olarak uygulandı

Birden fazla kullanıcı tanımlı dönüştürme örtük olarak tek bir değere--uygulanan derleyici açık bir dönüştürme bulunamadı, ancak kullanılan bir dönüşüm bulunamadı.

Aşağıdaki örnek, C4927 oluşturur:

```
// C4927.cpp
// compile with: /W1
struct B
{
   operator int ()
   {
      return 0;
   }
};

struct A
{
   A(int i)
   {
   }

   /*
   // uncomment this constructor to resolve
   A(B b)
   {
   }
   */
};

A f1( B& b)
{
   return A(b);
}

B& f2( B& b)
{
   return b;
}

A f()
{
   B b;
   return A(b);   // ok
   return f1(b);  // ok
   return b;      // C4927
   return B(b);   // C4927
   return f2(b);  // C4927
}

int main()
{
   B b;
   A a = b;
   A a2(b);
}
```