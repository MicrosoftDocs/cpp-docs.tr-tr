---
title: Derleyici Uyarısı (düzey 1) C4927
ms.date: 11/04/2016
f1_keywords:
- C4927
helpviewer_keywords:
- C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
ms.openlocfilehash: 8e56d185f6f87bc6e381ccec9ed8bd50ba3e2245
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052280"
---
# <a name="compiler-warning-level-1-c4927"></a>Derleyici Uyarısı (düzey 1) C4927

geçersiz dönüştürme; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı

Birden çok kullanıcı tanımlı dönüştürme örtük olarak tek bir değere uygulandı--derleyici açık bir dönüştürme bulamadı, ancak kullandığı bir dönüştürme bulmadı.

Aşağıdaki örnek C4927 oluşturur:

```cpp
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