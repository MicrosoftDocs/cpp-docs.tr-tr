---
title: Derleyici Hatası C2764
ms.date: 11/04/2016
f1_keywords:
- C2764
helpviewer_keywords:
- C2764
ms.assetid: 3754f5af-e094-4425-be20-d0c9a9b5baec
ms.openlocfilehash: ba16431fc71a0e594b77dcc6dab62ed6c49c9137
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587114"
---
# <a name="compiler-error-c2764"></a>Derleyici Hatası C2764

'param': şablon parametresi kullanılamıyor veya anlaşılabilir 'özelleştirmesi' kısmı özelleştirmesi içinde değil

Şablon parametresi, bir kısmi özelleştirmede kullanılmaz. Şablon parametresi anlaşılamıyor çünkü bu kısmi özelleştirmesi kullanılamaz hale getirir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2764 oluşturur:

```
// C2764.cpp
#include <stdio.h>
template <class T1, class T2>
struct S  {
   int m_i;
};

template <class T1, class T2>
struct S<int, T2*> {   // C2764
// try the following line instead
// struct S<T1(*)(T2), T2*> {
   char m_c;
};

int main() {
   S<int, char> s1;
   S<void (*)(short), short *> s2;
   s2.m_c = 10;
   s1.m_i = s2.m_c;
   printf_s("%d\n", s1.m_i);
}
```