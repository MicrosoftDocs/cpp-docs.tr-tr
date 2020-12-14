---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3849'
title: Derleyici hatası C3849
ms.date: 11/04/2016
f1_keywords:
- C3849
helpviewer_keywords:
- C3849
ms.assetid: 5347140e-1a81-4841-98c0-b63d98264b64
ms.openlocfilehash: 6dbe4656eea2691c1c77c1afa389be80ab76af18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255359"
---
# <a name="compiler-error-c3849"></a>Derleyici hatası C3849

' Type ' türündeki bir ifade üzerinde işlev stili çağrı, kullanılabilir tüm işleç aşırı yüklemeleri için const ve/veya volatile niteleyicileri kaybeder

Belirtilen const-volatile türüne sahip bir değişken, yalnızca aynı veya daha fazla const-volatile niteliğine sahip üye işlevlerini çağırabilir.

Bu hatayı onarmak için uygun bir üye işlevi sağlayın. Dönüştürme, niteliğin kaybedilmesine neden olduğunda const veya volatile nitelikli bir nesne üzerinde dönüştürme yürütemezsiniz. Niteleyiciler kazanabilirsiniz, ancak bir dönüştürmede niteleyicileri kaybedebilirsiniz.

Aşağıdaki örnekler C3849 oluşturur:

```cpp
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
