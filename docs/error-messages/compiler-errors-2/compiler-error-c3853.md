---
title: Derleyici Hatası C3853
ms.date: 11/04/2016
f1_keywords:
- C3853
helpviewer_keywords:
- C3853
ms.assetid: 5b71805d-52b4-44ec-80ae-37c68d876f6a
ms.openlocfilehash: c2282196d045ffd88696149f7d22d4ed7f9603ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265483"
---
# <a name="compiler-error-c3853"></a>Derleyici Hatası C3853

'=': bir başvurusu veya bir başvuru işlev aracılığıyla atamayı yeniden başlatmak geçersizdir

Bir işlev aracılığıyla bir başvuru işlevleri lvalues olmadığından atayamazsınız.

Aşağıdaki örnekler C3853 oluştur:

```
// C3853.cpp
// compile with: /EHsc
#include <iostream>
int afunc(int i)
{
   return i;
}

typedef int (& rFunc_t)(int);

int main()
{
   rFunc_t rf = afunc;   // OK binding a reference to function
   rf = afunc;   // C3853, can't reassign to a ref that's an lvalue
   int i = 99;
   int & ri = i;
   std::cout << i << std::endl;
   ri = 0;   // OK, i = 88;
   std::cout << i << std::endl;
}
```