---
title: Derleyici Hatası C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: ec6725472d31b0b2ade0cd73da4440036239fde3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598568"
---
# <a name="compiler-error-c3849"></a>Derleyici Hatası C3849

'type' türündeki bir ifade üzerinde işlev stili çağırma tüm sayı kullanılabilir işleç aşırı yüklemeleri için const ve/veya volatile niteleyicileri kaybeder

Belirtilen bir const-volatile türüne sahip bir değişken, yalnızca üye ile aynı veya daha büyük const-volatile nitelikleri tanımlanan işlevleri çağırabilir.

Bu hatayı düzeltmek için uygun bir üye işlevi sağlar. Dönüştürme nitelik kaybına neden olduğunda bir const veya volatile tam nesne üzerinde bir dönüştürme yürütülemiyor. Niteleyicileri elde edebilir, ancak bir dönüştürme niteleyicileri kaybeder olamaz.

Aşağıdaki örnekler C3849 oluştur:

```
// C3849.cpp
void glbFunc3(int i, char c)
{
   i;
}
typedef void (* pFunc3)(int, char);

void glbFunc2(int i)
{
   i;
}

typedef void (* pFunc2)(int);

void glbFunc1()
{
}
typedef void (* pFunc1)();

struct S4
{
   operator ()(int i)
   {
      i;
   }

   operator pFunc1() const
   {
      return &glbFunc1;
   }

   operator pFunc2() volatile
   {
      return &glbFunc2;
   }

   operator pFunc3()
   {
      return &glbFunc3;
   }

   // operator pFunc1() const volatile
   // {
   //    return &glbFunc1;
   // }
};

int main()
{
   // Cannot call any of the 4 overloads of "operator ()(.....)" and
   // "operator pFunc()" because none is declared as "const volatile"
   const volatile S4 s4;  // can only call cv member functions of S4
   s4();   // C3849 to resolve, uncomment member function
}
```